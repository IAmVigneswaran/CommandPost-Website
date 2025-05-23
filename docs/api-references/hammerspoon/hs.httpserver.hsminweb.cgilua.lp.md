# hs.httpserver.hsminweb.cgilua.lp

Support functions for the CGILua compatibility module for including and translating Lua template pages into Lua code for execution within the Hammerspoon environment to provide dynamic content for http requests.

The most commonly used function is likely to be [cgilua.lp.include](#include), which allows including a template driven file during rendering so that common code can be reused more easily.  While passing in your own environment table for upvalues is possible, this is not recommended for general use because the default environment passed to each included file ensures that all server variables and the CGILua compatibility functions are available with the same names, and any new non-local (i.e. "global") variable defined are shared with the calling environment and not shared with the Hammerspoon global environment.

If your template file requires the ability to create variables in the Hammerspoon global environment, access the global environment directly through `_G`.

Note that the above considerations only apply to creating new "global" variables.  Any currently defined global variables (for example, the `hs` table where Hammerspoon module functions are stored) are available within the template file as long as no local or CGILua environment variable shares the same name (e.g. `_G["hs"]` and `hs` refer to the same table.

See the documentation for the [cgilua.lp.include](#include) for more information.

---

## API Overview
**Functions** - _API calls offered directly by the extension_
 * [compile](#compile)
 * [include](#include)
 * [translate](#translate)


---

## API Documentation

#### Functions


### [compile](#compile)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.httpserver.hsminweb.cgilua.lp.compile(source, name, [env]) -> function`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Converts the specified Lua template source into a Lua function.                                                                     |
| **Parameters**                              | <ul><li>source - a string containing the contents of a Lua/HTML template to be converted into a function</li><li>name   - a label used in an error message if execution of the returned function results in a run-time error</li><li>env    - an optional table specifying the environment to be used by the lua builtin function `load` when converting the source into a function.  By default, the function will inherit its caller's environment.</li></ul> |
| **Returns**                                 | <ul><li>A lua function which should take no arguments.</li></ul>          |
| **Notes**                                   | <ul><li>The source provided is first compared to a stored cache of previously translated templates and will re-use an existing translation if the template has been seen before.  If the source is unique, [cgilua.lp.translate](#translate) is called on the template source.</li><li>This function is used internally by [cgilua.lp.include](#include), and probably won't be useful unless you want to translate a dynamically generated template -- which has security implications, depending upon what inputs you use to generate this template, because the resulting Lua code will execute within your Hammerspoon environment.  Be very careful about your inputs if you choose to ignore this warning.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/httpserver/cgilua_compatibility_functions.lua line 612](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/httpserver/cgilua_compatibility_functions.lua#L612) |

---


### [include](#include)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.httpserver.hsminweb.cgilua.lp.include(file, [env]) -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Includes the template specified by the `file` parameter.                                                                     |
| **Parameters**                              | <ul><li>file - a string containing the file system path to the template to include.</li><li>env  - an optional table specifying the environment to be used by the included template.  By default, the template will inherit its caller's environment.</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul><li>* This function is called by the web server to process the template specified by the requested URL.  Subsequent invocations of this function can be used to include common or re-used code from other template files and will be included in-line where the `cgilua.lp.include` function is invoked in the originating template.</li><li>During the processing of a web request, the local directory is temporarily changed to match the local directory of the path of the file being served, as determined by the URL of the request.  This is usually different than the Hammerspoon default directory which corresponds to the directory which contains the `init.lua` file for Hammerspoon.</li><li></li><li>* The default template environment provides the following:</li><li> the `__index` metamethod points to the `_G` environment variable in the Hammerspoon Lua instance; this means that any global variable in the Hammerspoon environment is available to the lua code in a template file.</li><li> the `__newindex` metamethod points to a function which creates new "global" variables in the template files environment; this means that if a template includes another template file, and that second template file creates a "global" variable, that new variable will be available in the environment of the calling template, but will not be shared with the Hammerspoon global variable space;  "global" variables created in this manner will be released when the HTTP request is completed.</li><li></li><li> `print` is overridden so that its output is streamed into the response body to be returned when the web request completes.  It follows the traditional pattern of the `print` builtin function: multiple arguments are separated by a tab character, the output is terminated with a new-line character, non-string arguments are converted to strings via the `tostring` builtin function.</li><li> `write` is defined as an alternative to `print` and differs in the following ways from the `print` function described above:  no intermediate tabs or newline are included in the output streamed to the response body.</li><li> `cgilua` is defined as a table containing all of the functions included in this support sub-module.</li><li> `hsminweb` is defined as a table which contains the following tables which may be of use:</li><li>   CGIVariables - a table containing key-value pairs of the same data available through the [cgilua.servervariable](#servervariable) function.</li><li>   id           - a string, generated via `hs.host.globallyUniqueString`, unique to this specific HTTP request.</li><li>   log          - a table/object representing the `hs.httpserver.hsminweb` instance of `hs.logger`.  This can be used to log messages to the Hammerspoon console as described in the documentation for `hs.logger`.</li><li>   request      - a table containing data representing the details of the HTTP request as it was made by the web client to the server.  The following keys are commonly found:</li><li>     headers - a table containing key-value pairs representing the headers included in the HTTP request; unlike the values available through [cgilua.servervariable](#servervariable) or found in `CGIVariables`, these are available in their raw form.</li><li>       this table also contains a table with the key "_".  This table contains functions and data used internally, and is described more fully in a supporting document (TBD).  It is targeted primarily at custom error functions designed for use with `hs.httpserver.hsminweb` and should not generally be necessary for Lua template files.</li><li>     method  - the method of the HTTP request, most commonly "GET" or "POST"</li><li>     path    - the path portion of the requested URL.</li><li>   response     - a table containing data representing the response being formed for the response to the HTTP request.  This is generally handled for you by the `cgilua` support functions, but for special cases, you can modify it directly; this should contain only the following keys:</li><li>     body    - a string containing the response body.  As the lua template outputs content, this string is appended to.</li><li>     code    - an integer representing the currently expected response code for the HTTP request.</li><li>     headers - a table containing key-value pairs of the currently defined response headers</li><li>   _tmpfiles    - used internally to track temporary files used in the completion of this HTTP request; do not modify directly.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/httpserver/cgilua_compatibility_functions.lua line 638](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/httpserver/cgilua_compatibility_functions.lua#L638) |

---


### [translate](#translate)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.httpserver.hsminweb.cgilua.lp.translate(source) -> luaCode`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Converts the specified Lua template source into Lua code executable within the Hammerspoon environment.                                                                     |
| **Parameters**                              | <ul><li>source - a string containing the contents of a Lua/HTML template to be converted into true Lua code</li></ul> |
| **Returns**                                 | <ul><li>The lua code corresponding to the provided source which can be fed into the `load` lua builtin to generate a Lua function.</li></ul>          |
| **Notes**                                   | <ul><li>This function is used internally by [cgilua.lp.include](#include), and probably won't be useful unless you want to translate a dynamically generated template -- which has security implications, depending upon what inputs you use to generate this template, because the resulting Lua code will execute within your Hammerspoon environment.  Be very careful about your inputs if you choose to ignore this warning.</li><li>To ensure that the translated code has access to the `cgilua` support functions, pass `_ENV` as the environment argument to the `load` lua builtin; otherwise any output generated by the resulting function will be sent to the Hammerspoon console and not included in the HTTP response sent back to the client.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/httpserver/cgilua_compatibility_functions.lua line 565](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/httpserver/cgilua_compatibility_functions.lua#L565) |

---

