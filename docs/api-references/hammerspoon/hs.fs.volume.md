# hs.fs.volume

Interact with OS X filesystem volumes

This is distinct from hs.fs in that hs.fs deals with UNIX filesystem operations, while hs.fs.volume interacts with the higher level OS X concept of volumes

---

## API Overview
**Constants** - _Useful values which cannot be changed_
 * [didMount](#didmount)
 * [didRename](#didrename)
 * [didUnmount](#didunmount)
 * [willUnmount](#willunmount)

**Functions** - _API calls offered directly by the extension_
 * [allVolumes](#allvolumes)
 * [eject](#eject)

**Constructors** - _API calls which return an object, typically one that offers API methods_
 * [new](#new)

**Methods** - _API calls which can only be made on an object returned by a constructor_
 * [start](#start)
 * [stop](#stop)


---

## API Documentation

#### Constants


### [didMount](#didmount)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.fs.volume.didMount`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | A volume was mounted                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [extensions/fs/libfs_volume.m line 12](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/fs/libfs_volume.m#L12) |

---


### [didRename](#didrename)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.fs.volume.didRename`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | A volume changed either its name or mountpoint (or more likely, both)                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [extensions/fs/libfs_volume.m line 24](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/fs/libfs_volume.m#L24) |

---


### [didUnmount](#didunmount)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.fs.volume.didUnmount`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | A volume was unmounted                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [extensions/fs/libfs_volume.m line 16](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/fs/libfs_volume.m#L16) |

---


### [willUnmount](#willunmount)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.fs.volume.willUnmount`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | A volume is about to be unmounted                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [extensions/fs/libfs_volume.m line 20](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/fs/libfs_volume.m#L20) |

---

#### Functions


### [allVolumes](#allvolumes)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.fs.volume.allVolumes([showHidden]) -> table`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns a table of information about disk volumes attached to the system                                                                     |
| **Parameters**                              | <ul><li>showHidden - An optional boolean, true to show hidden volumes, false to not show hidden volumes. Defaults to false.</li></ul> |
| **Returns**                                 | <ul><li>A table of information, where the keys are the paths of disk volumes</li></ul>          |
| **Notes**                                   | <ul><li>This is an alias for `hs.host.volumeInformation()`</li><li>The possible keys in the table are:</li><li> NSURLVolumeTotalCapacityKey - Size of the volume in bytes</li><li> NSURLVolumeAvailableCapacityKey - Available space on the volume in bytes</li><li> NSURLVolumeIsAutomountedKey - Boolean indicating if the volume was automounted</li><li> NSURLVolumeIsBrowsableKey - Boolean indicating if the volume can be browsed</li><li> NSURLVolumeIsEjectableKey - Boolean indicating if the volume should be ejected before its media is removed</li><li> NSURLVolumeIsInternalKey - Boolean indicating if the volume is an internal drive or an external drive</li><li> NSURLVolumeIsLocalKey - Boolean indicating if the volume is a local or remote drive</li><li> NSURLVolumeIsReadOnlyKey - Boolean indicating if the volume is read only</li><li> NSURLVolumeIsRemovableKey - Boolean indicating if the volume's media can be physically ejected from the drive (e.g. a DVD)</li><li> NSURLVolumeMaximumFileSizeKey - Maximum file size the volume can support, in bytes</li><li> NSURLVolumeUUIDStringKey - The UUID of volume's filesystem</li><li> NSURLVolumeURLForRemountingKey - For remote volumes, the network URL of the volume</li><li> NSURLVolumeLocalizedNameKey - Localized version of the volume's name</li><li> NSURLVolumeNameKey - The volume's name</li><li> NSURLVolumeLocalizedFormatDescriptionKey - Localized description of the volume</li><li>* Not all keys will be present for all volumes</li><li>* The meanings of NSURLVolumeIsEjectableKey and NSURLVolumeIsRemovableKey are not generally useful for determining if a drive is removable in the modern sense (e.g. a USB drive) as much of this terminology dates back to when USB didn't exist and removable drives were things like Floppy/DVD drives. If you're trying to determine if a drive is not fixed into the computer, you may need to use a combination of these keys, but which exact combination you should use, is not consistent across macOS versions.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/fs/fs.lua line 35](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/fs/fs.lua#L35) |

---


### [eject](#eject)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.fs.volume.eject(path) -> boolean,string`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Unmounts and ejects a volume                                                                     |
| **Parameters**                              | <ul><li>path - An absolute path to the volume you wish to eject</li></ul> |
| **Returns**                                 | <ul><li>A boolean, true if the volume was ejected, otherwise false</li><li>A string, empty if the volume was ejected, otherwise it will contain the error message</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/fs/libfs_volume.m line 120](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/fs/libfs_volume.m#L120) |

---

#### Constructors


### [new](#new)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.fs.volume.new(fn) -> watcher`                                                                    |
| **Type**                                    | Constructor                                                                     |
| **Description**                             | Creates a watcher object for volume events                                                                     |
| **Parameters**                              | <ul><li>fn - A function that will be called when volume events happen. It should accept two parameters:
  An event type (see the constants defined above)
  A table that will contain relevant information</li></ul> |
| **Returns**                                 | <ul><li>An `hs.fs.volume` object</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/fs/libfs_volume.m line 148](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/fs/libfs_volume.m#L148) |

---

#### Methods


### [start](#start)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.fs.volume:start()`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Starts the volume watcher                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>An `hs.fs.volume` object</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/fs/libfs_volume.m line 208](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/fs/libfs_volume.m#L208) |

---


### [stop](#stop)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.fs.volume:stop()`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Stops the volume watcher                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>An `hs.fs.volume` object</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/fs/libfs_volume.m line 232](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/fs/libfs_volume.m#L232) |

---

