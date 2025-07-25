# Release Notes

### CommandPost 1.5.2

**🎉 Released:**
- Wednesday 18th December 2024

#### 🔨 Improvements

- Added a Set Speed Rate to 2000% action for Final Cut Pro. Thanks for suggesting Aad Straathof!

#### 🐞 Bug Fixes

- Fixed Color Board Actions in Final Cut Pro 11. Thanks for reporting Eric Badura!
- Fixed a bug where we were incorrectly detecting the Viewer Control Bar when in Timecode Entry Mode in macOS Sequoia.
- Fixed a bug where we weren't able to watch for file-system level Preferences changes in Final Cut Pro 11.
- Fixed a bug in Loupedeck's button LED colour controls where you weren't able to adjust the brightness correctly. Thanks for reporting Eric Badura!
- Fixed a bug in the Loupedeck Preferences UI where the LED colour Examples button wasn't visible on macOS Sequoia.
- Fixed a bug in the Final Cut Pro Inspector where incorrect buttons were being triggered. For example, the action to add a keyframe for the Rotation property, would incorrectly select the Position property in Final Cut Pro 11. Thanks for reporting Dani Ditu!
- Fixed a bug where Audio Inspector actions were no longer working - such as pan mode - in Final Cut Pro 11. Thanks for reporting Dani Ditu!

---

### CommandPost 1.5.1

**🎉 Released:**
- Friday 6th December 2024

#### 🐞 Bug Fixes

- Fixed a bug in the **Modify Project** action for Final Cut Pro. Thanks for reporting Adam Schoales!
- Fixed how CommandPost reads and writes Final Cut Pro 11's sandboxed preferences. This fixes features such as **Enable Rendering During Playback**.
- Fixed how CommandPost reads Final Cut Pro 11's sandboxed User Destinations.
- Fixed a bug which prevented CommandPost from sending FCPXMLs back to Final Cut Pro. Thanks for reporting Martin Turner!

---

### CommandPost 1.5.0

**🎉 Released:**
- Thursday 21st November 2024

#### 🔨 Improvements

- Updated to Lua v5.4.7.
- Added support for FCPXML v1.13 used by Final Cut Pro 11.
- Increased the number of banks from 30 to 50. Thanks for suggesting Todd Hallam!
- We now force the Sony Timecode Repair Toolbox to use FCPXML v1.11, so that it can be more easily imported into older versions of DaVinci Resolve.

#### 🐞 Bug Fixes

- Added support for Clear Key in Final Cut Pro Command Sets. Thanks for reporting Iain Anderson!
- Fixed an error on macOS Sequoia, where macOS would return no frontmost windows (which shouldn't technically be possible). Thanks for reporting Iain Anderson!
- Fixed a bug where **Insert Action** in the Scripting panel would fail to import some actions. Thanks for reporting Ermal Rexhepi!
- Fixed a bug in Final Cut Pro 11 and macOS Sequoia where CommandPost could fail to apply Effects, Transitions, Titles and Generators. Thanks for reporting Kurt Farr!
- We now correctly trigger **Final Cut Pro Trial** menubar items when running the trial version of Final Cut Pro.

---

### CommandPost 1.4.27

**🎉 Released:**
- Saturday 22nd June 2024

#### 🔨 Improvements

- Added support for FCPXML v1.12 used by Final Cut Pro 10.8. Thanks for reporting Sam Pluemacher!
- Updated from CSV2Notion v1.2.1 to v1.3.1.

---

### CommandPost 1.4.26

**🎉 Released:**
- Monday 22nd January 2024

#### 🐞 Bug Fix

- In Final Cut Pro 10.6.6, Apple merged the **Masks** and **Keying** Effects Categories into a single **Masks and Keying** Effects Category, which we never accounted for. CommandPost now correctly applies the **Masks and Keying** effects in Final Cut Pro 10.6.6 and later. However, if you already have a shortcut key or control surface button for any of these actions (such as **Draw Mask**), you may have to select the **Scan Motion Templates** button in the **Final Cut Pro** panel in CommandPost Preferences to re-scan all your effects, then reapply the action to your keyboard shortcut or button. Thanks for reporting Димитър Маратилов!

---

### CommandPost 1.4.25

**🎉 Released:**
- Friday 20th January 2024

#### 🔨 Improvements

- Increased the default number of banks from 15 to 30. Thanks for suggesting Daniel Rejowski!
- Updated from csv2notion v0.3.9 to CSV2Notion Neo v1.2.1. Thanks Vigneswaran Rajkumar!
- Added a new "Notion Workspace" field in the Notion & Shot Data Toolboxes. Thanks Vigneswaran Rajkumar!

---

### CommandPost 1.4.24

**🎉 Released:**
- Friday 19th January 2024

#### 🐞 Bug Fixes
- Fixed a regression which prevented "Open File or Folder" dialog boxes from opening. Thanks for reporting Jason Sheldon!
- We've rolled back from CSV2Notion Neo v1.2.0 to csv2notion v0.3.9 for the time being due to some changes in CSV2Notion Neo. Thanks for reporting Vigneswaran Rajkumar!

---

### CommandPost 1.4.23

**🎉 Released:**
- Thursday 18th January 2024

#### 🎉 New Features

- Added actions for the Video Inspector Orientation controls. Thanks for suggesting Holger Kartes!
- Added support for the latest Stream Deck XL hardware.

#### 🔨 Improvements

- Added an explanation as to why CommandPost needs to access data from others apps on macOS Sonoma. CommandPost needs to be able to read files contained in other applications containers. For example, CommandPost's reads the files within Keyboard Maestro's folder to get a list of macros, and within Final Cut Pro's folders to get a list of Share Destinations. You can click 'Allow' to approve permission for this session, or alternatively grant CommandPost 'Full Disk Access' in System Settings to avoid getting this request each time CommandPost restarts.
- Renamed the "Execute Code" button in the Scripting panel to "Test Snippet" to make it easier to understand what it does.
- Added a "Open Control Surfaces" button to the Scripting panel. Thanks for suggesting Florian Duffe!
- Updated from csv2notion v0.3.8 to CSV2Notion Neo v1.2.0. Thanks Vigneswaran Rajkumar!

#### 🐞 Bug Fixes

- Fixed a bug where "Titles to Keywords" could fail on some clips from Sync-N-Link. Thanks for reporting Rainer Nigrelli!

---

### CommandPost 1.4.22

**🎉 Released:**
- Thursday 31st August 2023

#### 🎉 New Features
- Added actions to Toggle Individual Video Inspector Keyframes. Thanks for suggesting Tony Tang, Ernesto Garza & Dani Ditu!
- Added actions to Monogram Creator to Toggle Individual Video Inspector Keyframes.
- Added actions to Monogram Creator to control the Video Inspector Distort Controls. Thanks for suggesting Jason McNamara!
- Added an action to toggle the MotionVFX Title Animation Amount Keyframe.
- Added an action to Monogram Creator to toggle the MotionVFX Title Animation Amount Keyframe.

---

### CommandPost 1.4.21

**🎉 Released:**
- Wednesday 30th August 2023

#### 🎉 New Features

- Monogram Favourites has been improved, and there are now seperate actions for Press, Turn Left and Turn Right. This makes it a lot easier to assign whatever you want to a Monogram knob or slider. Thanks for suggesting Jason McNamara!
- Increased the amount of Monogram Favourites from 20 to 50.
- Added actions for "MotionVFX Title - Animation Amount". This can be used to control the "Animation Amount" for a lot of MotionVFX's mMusic Video 2 titles. Thanks for suggesting Jason McNamara!
- Added "Title Inspector > MotionVFX Title > Animation Amount" to Monogram Creator. This can be used to control the "Animation Amount" for a lot of MotionVFX's mMusic Video 2 titles. Thanks for suggesting Jason McNamara!

#### 🐞 Bug Fixes

- The Colour Adjustments actions now only load if you're running Final Cut Pro 10.6.6 or later. This prevents a potential error message from displaying in the Debug Console.
- Fixed a bug in the "Distort Bottom Right Y" and "Distort Top Right Y" actions. Thanks for reporting Jason McNamara!
- Updated various website links in CommandPost to point to the new centralised CommandPost website.

---

### CommandPost 1.4.20

**🎉 Released:**
- Wednesday 12th July 2023

#### 🔨 Improvements

- Added support for the latest Loupedeck CT hardware. Thanks for reporting Marshall Fife!

---

### CommandPost 1.4.19

**🎉 Released:**
- Monday 3rd July 2023

#### 🔨 Improvements

- Added actions to control all the parameters for a **Colourlab Ai** Effect in the Final Cut Pro Video Inspector. Thanks for suggesting Jackson Strafford!
- Added support for Spotlight's `fileName` and `displayName` in Final Cut Pro Info Inspector API. Thanks for suggesting pravdomil!

---

### CommandPost 1.4.18

**🎉 Released:**
- Thursday 15th June 2023

#### 🔨 Improvements

- Added support for FCPXML v1.11.
- Added actions for Scale X and Scale Y. Thanks for suggesting Undertaker01!
- Added actions for Color Adjustments.
- Added a **Search Console** menu item to the top of the menubar for easy access.
- Updated csv2notion to v0.3.8. Thanks for your amazing work Vladilen Zhdanov!

#### 💪 Changes

- Removed the Vimeo Toolbox. This functionality is now included in Marker Toolbox on the Mac App Store.
- Updated all the website links to point to the newly designed CommandPost website.

#### 🐞 Bug Fixes

- Fixed the **Set Camera LUT to None** action on macOS Ventura. Thanks for reporting Oli Frost!
- Fixed the **Player Background** actions. Thanks for reporting Kes Akalaonu!
- Fixed how we save items to the Pasteboard Buffer. Previously you had to save something to buffer two, before you could save to buffer three, etc. This is now fixed, and you can save and recall from any buffer slot. Thanks for reporting Dimitar Maratilov!
- Added missing Search Console labels for **Shift Anchor** actions.
- It seems that version 2 models of the Loupedeck Live, when running the latest firmware, now work the same as a Razer Stream Controller. We now determine which display method to use based on the firmware version. Thanks for reporting Alexander Przemysław Kamiński!

---

### CommandPost 1.4.17

#### 🔨 Improvements

- Increase Pasteboard Buffer Actions from 9 to 50. Thanks for suggesting Dimitar Maratilov!

#### 🐞 Bug Fixes

- Take 3! It seems we've been playing cat and mouse with Apple. "Save Timeline Index to CSV" should now work on both macOS Monterey and all versions of macOS Ventura. Thanks for reporting Larry Jordan!

---

### CommandPost 1.4.16

#### 🔨 Improvements

- Updated from Lua v5.4.3 to v5.4.4. Thanks Chris Jones & Lua Team!
- The Debug Console is now limited to 100,000 characters by default. Thanks Chris Jones!

#### 🐞 Bug Fixes

- Fixed bug in "Select Clip at Lane" actions. Thanks for reporting Christopher Tasti!

---

### CommandPost 1.4.15

#### 🎉 New Features

- Added support for the Stream Deck Plus.
- Added support for the latest Stream Deck Mini.
- Added actions for controlling the Loupedeck Screen and LED brightness. Thanks for suggesting anarchy!

#### 🔨 Improvements

- Updated csv2notion from v0.3.5 to v0.3.7. Thanks for your amazing work Vladilen Zhdanov!
- In the Shot Data Toolbox, we now save and restore the "Export Destination" with the settings. Thanks for suggesting Vigneswaran Rajkumar!

#### 🐞 Bug Fixes

- Fixed a bug where the clip duration was incorrect when using the Vimeo Toolbox. Thanks for reporting Noah Leon!
- Fixed a bug which prevented "Reveal in Keyword Collection" actions from working. Thanks for reporting Eric Lami!
- Fixed a bug in the Titles to Keywords Toolbox where we never considered that a sync-clip might actually contain a spine, if there's a gap clip at the start of the sync-clip. Thanks Olivier Galliano & Sam Pluemacher!
- Fixed Logic bug in Stream Deck Banks. Thanks aj752!
- Fixed logic bug in Resolve Control Surface Banks. Thanks KotzendesEinhorn-rgb!
- Reverted changes we made in v1.4.14 to fix macOS Ventura bugs, as Apple has seemed to fix them in a later Ventura update.
- Fixed a nil error in the Keywords action within the Loupedeck Plugin if no existing Keyword Shortcuts are allocated.

---

### CommandPost 1.4.14

#### ⚠️ Important Changes

- With the release of macOS Ventura, CommandPost v1.4.14 now requires macOS Big Sur or later. You can still use **CommandPost v1.4.13** on macOS Catalina.

#### 🔨 Improvements

- Sony Timecode Toolbox now supports 100fps Non-Drop Frame clips. Thanks for reporting Valerio D'Andrassi!
- Sony Timecode Toolbox now supports clips with Drop Frame (29.97fps, 59.94fps and 119.88fps) timecode. MASSIVE thank you to George Elias for supplying a huge amount of test clips!
- Added additional actions for triggering shortcut keys, using a slightly different method that works better with macOS applications using non-native frameworks, such as Blender. Thanks for reporting Alex Petrov!
- Updated csv2notion to v0.3.6. Thanks for your amazing work Vladilen Zhdanov!

#### 🐞 Bug Fixes


- Fixed a bug in our Timeline Index API, which caused the "Save Timeline Index to CSV" to fail on macOS Ventura, due to changes to the Accessibility API on macOS Ventura. Thanks for reporting Dale Ryan and Phil Swallow!
- Fixed a bug in our MenuButton API, which caused triggering certain menu buttons to fail on macOS Ventura, due to changes to the Accessibility API on macOS Ventura. Thanks for reporting Oli Frost!
- Fixed a potential error message in our AppleScript handler. Thanks for reporting Daniel Latimer!
- Fixed a bug with the “Copy Application” function in the Control Surfaces panels. If you copied a built-in application to a user-added application, it would incorrectly replace the display name of the destination application with that of the source application. Thanks for reporting John McAfee!

---

### CommandPost 1.4.13


#### 🔨 Improvements


- Titles to Keywords Toolbox now supports audio clips on the primary storyline. Also, now if you have a title that spans across multiple clips, keywords will be applied to all the clips that intersect that title. Thanks Sam Pluemacher!
- We've updated the CommandPost Workflow Extension icon so that it's greyscale, matching the look of other Workflow Extension icons. This will look much better if CommandPost is the only Workflow Extension you have installed. Thanks for suggesting Byk Valkonen! Designed by the amazing Matthew Skiles!

#### 🐞 Bug Fixes

- Final Cut Pro v10.6.5 fixes a regression (introduced in v10.6.2) which prevented CommandPost from detecting selected clips within a secondary storyline. This meant, for example, if you had a clip selected in a secondary storyline and triggered Timeline Batch Export, CommandPost would think no clips are selected in the timeline. This is now fixed! Woohoo! Thanks Apple!
- Fixed a bug in "Select Middle of Next/Previous Clip in the same storyline" actions. This now works again thanks to the above mentioned fix in Final Cut Pro v10.6.5. Thanks for reporting Nathen McEvoy!

---

### CommandPost 1.4.12


#### 🐞 Bug Fix

- Fixed an issue in the "Auto Sequence" Toolbox where audio clips were not processed correctly. Thanks for reporting Florian Duffe!

---

### CommandPost 1.4.11

#### 🎉 New Features

- Added support for the Razer Stream Controller.
- Added support for the Loupedeck Live-S.

#### 🔨 Improvements

- Added support for titles in secondary storylines to the Titles to Keywords Toolbox. Thanks for suggesting Knut Hake!
- Added a second text-box to the Titles to Keywords Toolbox, to be used for "common" keywords.
- Added a preference to "Add Space After Sequence" in the Titles to Keywords Toolbox. We also now add a "KEYWORD" role to every title.
- Added an option to "Treat FAVORITE and REJECT as Ratings instead of Keywords" in the Titles to Keywords Toolbox. When "Treat FAVORITE and REJECT as Ratings instead of Keywords" is enabled it will automatically create a "REJECT" and "FAVORITE" title when using "Create Titles from Text" (which also has a "REJECT" or "FAVORITE" role). We also now put the "Create Titles from Text" titles on a secondary storyline to make copying easier.
- When using "Create Titles from Text" in the Titles to Keywords Toolbox, we now alternate the positioning of the titles, so that you can more easily see them in the Final Cut Pro Viewer.
- Updated csv2notion to v0.3.5. Thanks for your amazing work Vladilen Zhdanov!

#### 🐞 Bug Fixes

- Fixed a bug where "Screens Backlight Level" wouldn't update correctly on Loupedeck devices.
- The warning popup that appears when using the reset buttons on the Loupedeck control surfaces panels now shows the correct control surface name (i.e. if you want to reset a Loupedeck Live, it now says Loupedeck Live instead of Loupedeck CT).

---

### CommandPost 1.4.10

#### 🎉 New Features

- Added a new "Auto Sequence" Toolbox. When you drag a Final Cut Pro Project to this Toolbox, we'll send a new Project back to Final Cut Pro with the clips sorted by timecode (with or without gaps). Thanks for suggesting Knut Hake & Sam Pluemacher!
- Added a new "Sony Timecode Repair" Toolbox. Final Cut Pro currently doesn't always correctly interpret timecode from certain Sony Cameras that are recording into an MP4 wrapper. This Toolbox will update a Project's FCPXML to use the correct timecode values from the XML sidecar file (or the MP4 itself if no sidecar file exists), so that you can more easily send timelines from Final Cut Pro to DaVinci Resolve, Baselight or Adobe Premiere (with XtoCC). Thanks Alister Robbie & Jamie LeJeune!

#### 🔨 Improvement

- The "Titles to Keywords" Toolbox now supports connected clips above the Primary Storyline. This means that you can have a single title over the top of multiple clips, and all of those clips will get the same keyword from this title. Thanks for suggesting Knut Hake & Sam Pluemacher!

---

### CommandPost 1.4.9

#### 🐞 Bug Fix

- Added some workarounds for macOS 13 Ventura Beta 22A5321da. Currently the Final Cut Pro "Edit > Start Dictation…" and "Edit > Emoji & Symbols" menu item actions will only work in English due to changes in macOS - we will try to search for a proper fix for this in the future for non-English users. Thanks for reporting Jeff Asher!

---

### CommandPost 1.4.8

#### 🔨 Improvement

- The `projectTimecode` token that can be used in Timeline Batch Export custom naming no longer uses dashes as separators (i.e. "00000000" instead of "00-00-00-00") so you more easily copy and paste into Final Cut Pro. Thanks for suggesting Jiří Fiala!

#### 🐞 Bug Fix

- Added missing action group labels for Razer Tartarus Chroma Applications & Banks. Thanks for reporting Frozner Videography!

---

### CommandPost 1.4.7

#### 🎉 New Features

- Added support for the Razer Tartarus Chroma. Thanks for suggesting Frozner Videography!
- Added a `projectTimecode` token to the Timeline Batch Export custom naming feature, allowing you to insert the project timecode of where the clip starts to the filename. Thanks for suggesting Jiří Fiala!
- Added action for "Toggle Zoom to Fit", allowing you to toggle between "Zoom to Fit" and your last zoom value. Thanks for suggesting Jiří Fiala!
- Added action for "Toggle Zoom to Selection", allowing you to toggle between "Zoom to Selection" and your last zoom value. Thanks for suggesting Richard Taylor!
- Added individual actions for specific timeline zoom values (1 to 10 in 0.5 increments).

#### 🐞 Bug Fix

- Fixed a bug in the "Mouse Left Double Click" action.

---

### CommandPost 1.4.6

#### 🐞 Bug Fix

- Disabling "Open Debug Console on Dock Icon Click" in the General Preferences still opened the Debug Console when clicking the dock icon. Thanks for reporting Vigneswaran Rajkumar!

---

### CommandPost 1.4.5


#### 🔨 Improvements

- Added an option to "Replace Commas With Alternative Commas" in the "Titles to Keywords" Toolbox. This is to workaround a bug in Final Cut Pro where it will split up a single keyword into multiple keywords when it detects a comma in the keyword name, when imported via a FCPXML. Thanks Knut Hake, Sam Pluemacher, Iain Anderson and Alex Gollner!

#### 🐞 Bug Fixes

- The contextual menu will now appear when you right-click on the "Create Titles from Text" text editor in the "Titles to Keywords" Toolbox.
- Fixed a bug that could cause a "nil" error in the Debug Console related to "topToBottomBaseAligned" sorting.

---

### CommandPost 1.4.4

#### 🎉 New Features

- Added a new "Titles to Keywords" Toolbox. When you drag a Final Cut Pro Event to this Toolbox (which must only contain a single Project), we will look through all the Titles connected to the clips in the Primary Storyline, read the name of those clips, then create new Keyword Ranges for each of those Titles. We then send that data back into Final Cut Pro automagically.
- We've also included a "Create Titles from Text" feature in this same Toolbox, that allows you to create a new Final Cut Pro Project which contains a new Title for every line in the Toolbox's text box - along with some additional formatting features, such as adding a prefix, suffix or sequential numbering. This allows you to easily copy and paste text from things like a PDF Script, convert them into Titles, adjust as required, then convert those Titles into Keywords. You can also setup the CommandPost Dock icon so that it automatically sends any dragged Events or FCPXML files directly to this new Toolbox. Thanks for suggesting Knut Hake & Sam Pluemacher! Thanks for testing Vigneswaran Rajkumar!

#### 🔨 Improvements

- The "Shot Data" Toolbox icon has been updated. Thanks Vigneswaran Rajkumar!

#### 🐞 Bug Fixes

- In Final Cut Pro 10.6.2, Apple renamed the "Photos and Audio" menubar item to "Photos, Videos and Audio", which broke some automation features, like inserting specific Titles & Generators. This is now fixed. Thanks for reporting Trace Dominguez!
- Fixed a bug that could cause a "invalid order function for sorting" error in the Debug Console.

---

### CommandPost 1.4.3

#### 🎉 New Features

- Added the ability to upload directly to Notion from the Shot Data Toolbox. Thanks Vigneswaran Rajkumar!
- Added a new Notion Toolbox allowing you to upload the Final Cut Pro Timeline Index and Browser Contents directly to Notion.
- Added two new drop-boxes in the General section of CommandPost’s preferences allowing you to set a “Drag & Drop Text Action” and a “Drag & Drop File Action”. This allows you to, for example, drag a Final Cut Pro project directly to the CommandPost dock icon to trigger the Vimeo Toolbox.
- Added a preference for “Key Repeat” and “Delay Until Repeat” in the Razer Control Surfaces panel. Thanks for suggesting Ross Batten!
- Added button that allows you to copy profiles between Razer devices in the Razer Control Surfaces panel. Thanks for suggesting Ross Batten!
- Added additional “Press & Hold” modifier actions. Thanks for suggesting Valerio D'Andrassi and Noé Molnár!
- Added actions to control Spotify. We’ve also added a new “Spotify” section in the CommandPost Loupedeck Plugin for easy access.
- Added actions to "Increment/Decrement User Interface Element Under Mouse”. This allows you to hover your mouse over a slider, knob or text-box in Final Cut Pro or DaVinci Resolve (for example), and use a control surface to control its value. We’ve also added a new “macOS: Accessibility” section in the CommandPost Loupedeck Plugin for easy access.

#### 🐞 Bug Fixes

- Added missing labels to some Razer Action Groups.
- Fixed a bug in the Color Board Angles actions. Thanks for reporting Noé Molnár!

---

### CommandPost 1.4.2

#### 🔨 Improvement

- The Loupedeck Plugin now requires Loupedeck 5.2 or later. The CommandPost Loupedeck Plugin has been updated so that unnecessary "reset" actions are no longer displayed in the LoupedeckConfig application - for example, the Cinematic Focus Point action, no longer has a "press" action associated with it (as it previously did nothing). This was a bug in the Loupedeck Plugin API that has now been addressed in version 5.2 of their software. Thanks Loupedeck Team!

#### 🐞 Bug Fix

- Fixed a regression that broke the "Unmount external drives when switching to battery power" and "Mount external drives when switching to AC power" features in the previous release.

---

### CommandPost 1.4.1

#### 🎉 New Features

- Added support for the Razer Tartarus, Tartarus Pro, Nostromo & Orbweaver Chroma. We'd love to add support for the Tartarus Chroma too, but have been unable to get our hands on this older device as of yet - if you have one that you can donate, let us know!

#### 🔨 Improvements

- You can now "drag and drop" to re-arrange buttons in the Razer Control Surfaces panel. You can also right-click on buttons to copy, cut and paste buttons.
- We've also added a preference to "Prevent Excessive Thumb Taps", to workaround issues with the thumb button on older Razer devices where the thumb button becomes too sensitive over time. Thanks for suggesting Ross Batten!
- We now cache the Razer devices brightness to improve performance.
- Added preference to "Scan Running Application Menubars on Startup" and "Scan the Menubars of the Active Application", which are now off by default to improve CommandPost's startup time.
- We no longer load various Final Cut Pro plugins when Final Cut Pro isn't installed, to improve startup performance.
- The CommandPost Workflow Extension for Final Cut Pro is no longer installed if Final Cut Pro is not installed.
- The Skype Shortcuts plugin no longer loads if Skype isn't installed.
- The Zoom Shortcuts plugin no longer loads if Zoom isn't installed.
- We've changed the way the "Press & Hold" modifier key actions works for better performance.
- CommandPost now defaults to controlling the Final Cut Pro Trial, if the trial is already running when CommandPost starts, even if the full version is also installed. Thanks for suggesting Nathen McEvoy!
- Changed the wording from "Unknown" to "Not Installed" in the Debug Console if the Final Cut Pro version and/or path can't be detected.
- Improved the German translation in the Loupedeck Plugin. Thanks Jenny!

#### 🐞 Bug Fixes

- Fixed bugs related to the "Copy Control to All Banks" and "Reset Control" buttons in the Razer Preferences.
- Fixed a bug where "Unlisted & Ignored Applications" wouldn't work as intended on Razer devices.
- Fixed a bug where deleting a Custom User Application in Razer Preferences wouldn't update the user interface correctly.

---

### CommandPost 1.4.0

#### 🎉 New Features

- We've added a new "Loupedeck Plugin" that acts as an alternative to our native/direct Loupedeck support - allowing you to access all of CommandPost's Final Cut Pro actions within the LoupedeckConfig application. This is really handy for users that have to jump between Adobe Premiere and Final Cut Pro, for example. All of your macOS Shortcuts macros and Keyboard Maestro macros will also appear in the LoupedeckConfig application automagically. There are also some macOS Spaces actions. Big thanks to the Loupedeck Team for their support - especially Jenny!
- Added support for the Razer Orbweaver. Big thanks to Ross Batten for giving us access to the hardware! We hope to add more Razer keyboards in the near future.
- We've added a new Final Cut Pro Workflow Extension, which allows us to better control the playhead (which works great with control surfaces - such as the Loupedeck CT wheel). The Workflow Extension will only load when you trigger an action that requires it. When you first load the Workflow Extension it will try and make itself as small as possible and get out of the way - however you can move it to wherever you want, and like all Workflow Extensions its position is saved with your Workspace. There are new actions for "Move Playhead Forward/Backward" at different increments. There's no buttons on the Workflow Extension - it's currently simply an interface for us to control the playhead.

#### 🐞 Bug Fixes

- Improved the colour accuracy of the Razer Tartarus V2 LEDs.
- Fixed a bug in the Resolve Control Surfaces where the "RELATIVE FINE CONTROL" jog mode wouldn't trigger the correct jog mode on the hardware.

---

### CommandPost 1.3.13

#### 🔨 Improvements

- We've added a new "Relative (Fine Control)" Jog Wheel Mode for the Blackmagic Resolve Keyboards, which uses a different algorithm for more precise control, as some users found the jog wheel too sensitive and hard to navigate when in relative mode. We’ve also added some additional sensitivity values, so you can further fine tune it to your liking. Thanks for your valuable feedback David Manganelli!
- We now forcefully update the LED lights on the Blackmagic Resolve Keyboards every 5 minutes to attempt to prevent the device from falling asleep. Thanks for reporting David Manganelli!

#### 🐞 Bug Fix

- Fixed a regression introduced in the previous release which caused applying individual effects, transitions, titles and generators to clips in Final Cut Pro via a CommandPost action to fail unexpectedly. Thanks for reporting Fernando Piñero & Andrew Griffiths!

---

### CommandPost 1.3.12

#### 🔨 Improvements

- CommandPost now remembers the menubar position if you change it by holding down COMMAND and dragging it to a new location.
- In the previous release of CommandPost if you tried to trigger a Final Cut Pro shortcut key that didn't actually have any keys assigned to it with the Final Cut Pro Command Editor, you'd be presented with an error message. This would sometime confuse users - for example, those using a Speed Editor which has the "Play Rate" shortcut keys assigned to the jog wheel - but Final Cut Pro doesn't assign anything to the "Play Rate" shortcuts by default. To improve this, if CommandPost tries to trigger a shortcut key that you haven't set up in Final Cut Pro, we'll now present you with a macOS Notification, which when clicked, takes you to the relevant Command within the Final Cut Pro Command Editor.
- CommandPost now disables support for displaying macOS Shortcut app shortcuts within the Search Console by default. To enable this functionality you must now manually enable it within the Shortcuts preferences panel within CommandPost. We have also added a new setup screen for new users, that allows you to enable shortcuts there. This is to prevent the shortcuts permission box from popping up the first time new users opened the Search Console.
- When you add a custom application to the Resolve Keyboards, it now automatically selects that application once added. Thanks for reporting Dávid Szentmiklósi!
- We've improved how we cache the Jog Wheel mode on the DaVinci Resolve Keyboards.
- Improved the load times of the Resolve, Razer and TourBox Control Surface Panels.
- The Speed Editor battery status is now displayed in the preferences panel.
- Updated the default Resolve Keyboard layouts so that the JOG banks use menubar actions instead of shortcut key actions to improve performance. This will only change for new users, or if you reset your layout to "factory default".

#### 🐞 Bug Fixes

- If you delete an application, device or everything on the Resolve Keyboard panel, it now resets the "last application" if that custom application no longer exists in the preferences file.
- CommandPost now correctly determines the Final Cut Pro language when you change it via System Preferences within the Language & Region > Apps section. Thanks for reporting Sam Pluemacher - we had no idea this feature was added to macOS!
- System Preferences no longer quits when CommandPost starts up.
- CommandPost can now better detect when the Command Set is changed within Final Cut Pro.
- Fixed a bug which prevented the Search Console from pre-populating the last action title in the Resolve Keyboard panel.

---

### CommandPost 1.3.11

#### 🐞 Bug Fixes

- Fixed a bug where Effects that contained special symbols in English would not be listed correctly in the Search Console when Final Cut Pro was not in English (i.e. the "Black & White" colour effect for Spanish users). Thanks for reporting Javier Beldamu!
- Fixed a bug where CommandPost would fail to select the Effects Category when Final Cut Pro was in Spanish, so that when you tried to insert an Effect from the Search Console, it would always use the "All Video & Audio" category, making it slightly slower.
- Fixed a bug where actions saved in English (i.e. all the default control surface layouts) would fail to trigger when Final Cut Pro was not in English. Thanks for reporting Peter Schroeder!
- Fixed a bug where the Search Console would fail to populate properly if Final Cut Pro was in Korean.

---

### CommandPost 1.3.10

#### 🔨 Improvements

- CommandPost now has the ability to read Final Cut Pro's Main Menu Structure directly (i.e. we can read the MainMenu.nib). MASSIVE THANK YOU to my partner-in-crime behind CommandPost, the incredible David Peterson. Whilst this won't really change anything for end users, it means that next time Apple pushes out an update - CommandPost will automatically read the new menubar structure without us having to push out an update. It also means "Show Duplicate Ranges" now appears in the "Menu Items" action group, not just the "Menu Items (Scanned)" action group.
- The Search HUD now shows options for "Original Codecs" and "Proxy Codecs".

#### 🐞 Bug Fixes

- We can now detect whether or not the timeline is in focus again - fixing various actions, such as "Set Spatial Conform Type".
- The "Set Spatial Conform Type" actions now work correctly when triggered from the Search Console.
- The "Show Horizon" action now works correctly when Final Cut Pro is in Korean.
- We've removed the Touch Bar debugging messages from the Debug Console.

---

### CommandPost 1.3.9

#### 🐞 Bug Fix

- In Final Cut Pro 10.6.2, Apple has changed the file format where they store the main menu structure for Final Cut Pro (from a binary property list to a NIBArchive), and we're currently trying to work out how to read the new format - as it's undocumented, we're not sure how long it'll take us to solve. In the meantime, we've added a temporary workaround where we use the menu main structure from 10.6.1, so that you can continue to use CommandPost with this new release. New menu items (such as "Show Duplicate Ranges") will still be available in the Search Console as Command Editor Shortcuts and scanned menu items.

#### 😭 Known Issues

- Currently we can't detect whether or not the Timeline is focussed in Final Cut Pro 10.6.2. This breaks some features such as "Set Spatial Conform Type", because we need to determine if you're selecting clips in the Browser or the Timeline - so CommandPost currently just assumes you're working in the browser. We'll investigate a workaround ASAP. If you spot any other Final Cut Pro 10.6.2 issues or bugs, please let us know!

---

### CommandPost 1.3.8

#### 🐞 Bug Fix

- Fixed a regression where CommandPost would error on startup if Final Cut Pro wasn't installed. Apologies to all our users that aren't using Final Cut Pro! Thanks for reporting Matt Dial!

---

### CommandPost 1.3.7

#### 🔨 Improvements

- We now scan the "additional" commands in Final Cut Pro. This means there are now keyboard command set actions for "Next Focus Point", "Previous Focus Point", "Cinematic Tool" and "Cinematic Editor" (and any future "additional" commands Apple adds in the future).

#### 🐞 Bug Fixes

- Fixed a rare bug where sometimes CommandPost shortcuts for Final Cut Pro would not activate if you started CommandPost with Final Cut Pro already running.
- The "Insert Action" button in the Snippets Editor now correctly formats code with non-standard characters, like the command icon you see on your keyboard. Previously inserted actions still work - they just look a bit weird. Thanks for reporting Marc Bach!
- You can now use the full range of LED colours on the Razer Tartarus V2 when using custom colours. Thanks for reporting Leonardo Franke!
- Fixed a bug which prevented CommandPost from detecting when Final Cut Pro was playing or stopped. We're hopeful this might fix the Scrolling Timeline Feature for some users. Thanks for reporting Martin Lohmann, Wizi Roy Shmueli and Javier Olvedo!

---

### CommandPost 1.3.6

#### 🐞 Bug Fix

- If you add a Custom Application in the Blackmagic Resolve Speed Editor or Editor Keyboard panel, the Custom Applications menubar items will now correctly appear in the Search Console. For example, if you add Hedge as a custom application, all of its menubar items will now appear in the CommandPost Search Console (assuming Hedge is running), so that you can trigger them from the Speed Editor or Editor Keyboard. Thanks for reporting Scott Simmons!

---

### CommandPost 1.3.5

#### 🐞 Bug Fix

- Fixed a bug where the "Insert Action" button in the Snippets Preferences panel could fail if the action code contained certain characters. Thanks for reporting Marc Bach!

---

### CommandPost 1.3.4

#### 🔨 Improvements

- The "Long Press" action on the Blackmagic Keyboards now happens after X number of seconds, rather than on the release of the button. Thanks for suggesting Marc Bach!
- If you do a "Long Press" action on the Blackmagic Keyboards, a seperate release action can now trigger when you release the button.
- You can now customise the "Long Press" duration for the Blackmagic Keyboards. It defaults to 0.4 seconds.
- We've added a new preference to the Blackmagic Keyboards panel called "Change Bank on Hardware When Changing Here". When enabled, if you change the bank in the preferences dropdown, it will change on the hardware too, so you can preview LED changes.
- The "Last Bank" action now takes into account any bank changes causes by changing the bank via the Preferences dropbox (assuming "Change Bank on Hardware When Changing Here" is enabled).
- Added a new preference to Blackmagic Keyboards panel called "Display Message When Changing Banks" to turn off the overlay that's displayed when changing banks.

---

### CommandPost 1.3.3

#### 🎉 New Features

- Added support for the DaVinci Resolve Editor Keyboard.
- Added "absolute" Jog Wheel support to the DaVinci Resolve Speed Editor.
- Added "long press" actions to the DaVinci Resolve Speed Editor.
- Added actions to scroll the Final Cut Pro timeline contents horizontally.
- Added actions to "Jump to Next/Previous Frame", which also takes into account a SHIFT key modifier to jump 10 frames instead of 1.
- Add actions to trigger Search Console specifically for Final Cut Pro Effects, Titles, Transitions and Generators. Thanks for suggesting Marc Bach!
- Added an action to go back to the "last" DaVinci Resolve Keyboard bank.

#### 🔨 Improvements

- We've updated the DaVinci Resolve Speed Editor layout to better demonstrate CommandPost's functionality. If you're already using CommandPost, you'll need to reset your layout to see these changes.
- Improved the reliability of virtual keyboard presses on macOS Monterey & Final Cut Pro 10.6.1.
- Improved the image quality of the Speed Editor image in the interface. Thanks for reporting Archetyped!
- Improved how we handle LEDs on the Speed Editor. LEDs are now all turned off when your computer is put to sleep, Speed Editor support is disabled, or you quit CommandPost.
- CommandPost now ignores button presses and jog wheel movements if DaVinci Resolve is running. DaVinci Resolve is now greyed out in the Speed Editor & Editor Keyboard drop-downs.
- Increased Tangent Favourites from 50 to 200. Thanks for suggesting Marc Bach!
- Added a Search Console toolbar icon for DaVinci Resolve keyboard banks.
- Added ability to reset to either completely empty or factory default for all the reset buttons on the DaVinci Resolve Keyboard panel.
- The "Insert Action" button in the Snippets Preferences now inserts more simplified code, and handles slashes better. Thanks for reporting Marc Bach!
- We added a new global Lua function to more easily trigger actions: cp.triggerAction(handler, action).

#### 🐞 Bug Fixes

- Fixed a bug in the DaVinci Resolve Keyboard panel where resetting an action would reset the entire button. Thanks for reporting Marc Bach!
- Changing Speed Editor banks now correctly shows any custom bank labels on the on-screen message.
- Fixed a bug where Final Cut Pro commands didn't show an icon in the Search Console.
- Fixed bugs in Distort Y actions. Thanks for reporting Flavio Saramin!
- Fixed a bug where the Snippets window never remembered the last Snippet.

---

### CommandPost 1.3.2

#### 🔨 Improvements

- "Automatically Switch Applications" for the Blackmagic Control Surfaces is now enabled by default on fresh installs.
- We've changed the default Speed Editor layout to turn all the LEDs on in the "Unlisted & Ignored Applications" layout so you can more easily see it's working. The Jog Wheel now acts as a mouse scroll wheel in this layout by default too.
- We've changed the wording on the DaVinci Resolve Control Surface panel to make it clear that "DaVinci Resolve will override CommandPost when running" and "we recommend using a wired connection".

#### 🐞 Bug Fixes

- Fixed a bug where the Speed Editor, Razer and TourBox preferences pages could appear incorrect if certain Safari Extensions are installed. Thanks for reporting!
- You can now change the LEDs for the CAM buttons on the Speed Editor.

---

### CommandPost 1.3.1

#### 🐞 Bug Fix

- Another attempt to fix an uncommon Touch Bar related crash that affects a very small number of users.

---

### CommandPost 1.3.0


#### ⚠️ Important Changes

- CommandPost has dropped Mojave support in this release. We now only support macOS Catalina, Big Sur & Monterey. If you're stuck on Mojave you can still use **CommandPost v1.2.16**.

#### 🎉 New Features

- Added support for the Blackmagic Resolve Speed Editor. This wouldn't be possible without the genius work from Sylvain Munaut. Special thanks to Morten Bentsen, Håvard Njåstad and Sondre Tungesvik Njåstad.
- Added actions to Prevent Mac from Sleeping (this was previously only available via the menubar). Thanks for suggesting Undertaker01!
- Added option to invert the timeline mouse zoom feature in Final Cut Pro, as well as adjust the sensitivity. Thanks for suggesting dutchct!
- Added actions to control the volume slider in the Final Cut Pro Inspector. Thanks for suggesting Olm Ek!
- Added Timeline Scroll presets to Monogram Creator.

#### 🔨 Improvements

- The Stream Deck preferences panel has been completely re-designed to more closely match our Loupedeck panels - allowing for better Drag & Drop support, and right-click contextual menus. You can now programatically generate icons. Thanks for suggesting James Peach!
- The Preferences and Control Surfaces toolbars now look much better on macOS Monterey.
- You can now assign shortcut keys without a modifier key. This is useful is you want to assign an action to the F1 key for example. Thanks for suggesting Florian Duffe!
- You can now assign any CommandPost action within the "All Applications" Keyboard section.
- The various Loupedeck Control Surfaces panels are now accessible from a single Loupedeck icon, which triggers a popup menu.
- We've added an option to the Loupedeck CT and Live to "Preview Selected Application & Bank on Hardware", so that you can visually check how a layout looks without leaving the CommandPost interface.
- Loupedeck devices running the older firmware, now more reliably wake form sleep. Thanks for reporting Knut Hake!
- Added Catalan translation. Thanks for suggesting Lluís Bartra!

#### ❌ Removed

- The Compressor Watch Folders feature has been removed, as this can now be achieved natively in Compressor.

#### 🐞 Bug Fixes

- Fixed a bug that broken any actions that used Final Cut Pro Audio Components. Thanks for reporting Daniel Stiefelhagen!
- Fixed a bug where Timeline Batch Export would fail to close the "Go to the folder" prompt on macOS Monterey. Thanks for reporting Kevin Luk!
- Skimming is now disabled when doing a Timeline Batch Export to improve reliability. Thanks for reporting Kevin Luk!
- "Enable Loupedeck Support" now appears correctly in the Search Console.
- The Vimeo Toolbox now correctly handles both the "Username" and "Name" headers in the CSV. Thanks for reporting Ché Baker!
- The "Report Final Cut Pro Bug to Apple" feature now works on Apple Silicon.
- We now check that the default Timeline Batch Export destination exists in the menubar before commencing. This fixes a bug where the Default Destination name changed between Final Cut Pro versions.
- Fixed a bug which prevented CommandPost from detecting the correct Timeline Title in 10.5.4 and above.
- Fixed a potential Lua error in the "Ignore Card" feature. Thanks for reporting Jack Ohrman!
- Fixed a potential Lua error in our Snapshot code.
- Allow copying to "Unlisted & Ignored Applications" in Control Surfaces panels. Thanks for reporting danielsti!
- If you added a custom application to the Loupedeck Preferences (i.e. Logic Pro X) and turned off "Automatically Switch Applications", there was no actions for switching to Logic Pro X. This has now been fixed. Thanks for reporting Eric Badura!
- You can now right-click on text boxes in the CommandPost Preferences panels, Control Surface panels and Final Cut Pro HUD.
- TourBox Devices now work correctly on macOS Big Sur & Monterey. Thanks for reporting Brett Sherman!
- Fixed a bug related to the Final Cut Pro Libraries List View that prevented the HUD Batch Rename tool from working. Thanks for reporting Florian Duffe!
- We've added a bandaid solution to HOPEFULLY solve crashes related to the Touch Bar.

---

### CommandPost 1.2.16

#### 🎉 New Features

- Added action to "Edit New Title" and "Edit New Lower Thirds" which adds a new title in Final Cut Pro, and highlights the text field so that you can instantly start typing. Thanks for suggesting Hugh Nagle!
- Added a Contrast control for the Color Wheels in Final Cut Pro for Monogram users. Thanks for suggesting Rob Mervin!
- Added Timeline Zoom in Final Cut Pro for Monogram users. Thanks for suggesting Sven Pape!
- Added clip Volume control in Final Cut Pro for Monogram Users. Thanks for suggesting Drew Boyd!
- Added Timeline Clip Height in Final Cut Pro for Monogram users.
- Added actions to change Razer Backlight Mode & Brightness, so you can trigger these from any control surface, HUD or Search Console.
- Added action to "Send Vimeo CSV to Final Cut Pro", so you can trigger this from any control surface, HUD or Search Console.
- macOS Shortcuts are now available on the Search Console for macOS Monterey users.

#### 🔨 Improvements

- The Chinese (Simplified) translations have been improved. Thanks Charles Liu!

---

### CommandPost 1.2.15

#### 🐞 Bug Fixes

- The Vimeo Toolbox can now handle CSV files where notes span over multiple lines. We also now ignore any lines in the CSV that don't have any notes. The error messages have also been improved. Thanks for reporting Scott Simmons!
- Fixed a bug which prevented backlight effects from working on a Razer device. Thanks for reporting Marwan Bakr!
- Fixed a bug which could cause the mouse scroll wheel or Trackpad to stop working after using the scroll wheel on a Razer device. Thanks for reporting Marwan Bakr!
- Fixed bug in the FCPXML Titles Toolbox and Frame.io to Markers action where CSV files would fail to load.
- Fixed bug where CommandPost would incorrectly expect all FCPXML files to be the latest v1.10 format.

#### 🔨 Improvements

- CommandPost now loads slightly faster when a Monogram device is connected.

---

### CommandPost 1.2.14

#### 🎉 New Feature

- Added a new Toolbox which converts Vimeo Review CSV files into markers in Final Cut Pro X. Thanks for suggesting Gary Roll, Adam Olivero & Scott Simmons!

#### 🐞 Bug Fix

- Prevented an error that could occur if you open the Tangent Control Surfaces panel without Tangent Hub/Mapper installed.

---

### CommandPost 1.2.13

#### 🐞 Bug Fix

- Fixed a bug which prevented the Search Console from showing on macOS Monterey 12.0.1. Thanks for reporting Mikhael Pacheco!

#### 🔨 Improvements

- Added support for FCPXML v1.10 and FCPXML Bundles.

---

### CommandPost 1.2.12

#### 🐞 Bug Fix

- The user interfaces in CommandPost (Preferences, Control Surfaces, Watch Folders & Toolbox) now show vertical scrollbars to allow you to scroll the panels, if your screen resolution is too small for the panel, such as on the Apple Silicon 13-inch MacBook Pro. Thanks for reporting Jocke Selin!

---

### CommandPost 1.2.11

#### 🎉 New Features

- Added support for the Razer Tartarus V2. You have full control over the LED backlights, and can assign the buttons and scroll wheels to any CommandPost actions. This all happens in the user space - no need for administrator privileges or kernel extensions.
- Added action to "Mark All Clips" in Final Cut Pro. Adds a marker to all selected clips under the playhead, or all clips if only one clip is selected.
- Added action to "Select All Even/Odd Clips In Timeline" in Final Cut Pro. Thanks for suggesting Rafael Gamboa!
- Added action to "Copy Selected Clip Duration to Pasteboard" in Final Cut Pro. Thanks for suggesting Vigneswaran Rajkumar & Rizvi Haider Rabby!

#### 🔨 Improvement

- You can now access all the individual Preference, Control Surface, Toolbox & Watch Folder panels directly from the menubar. This is a workaround for Big Sur users, where all the Control Surfaces don't fit on the toolbar, and sometimes the toolbar doesn't display a "more" button.

#### 🐞 Bug Fix

- The "Select" button for "Use Snippet to Set LED Color" in the Loupedeck CT and Live Preferences panel now opens a Search Console which only displays Snippets.

---

### CommandPost 1.2.10

#### 🐞 Bug Fix

- Fixed a bug which caused Transitions actions within Final Cut Pro to fail to apply if they didn't have a theme name. Thanks for reporting Dimitar Maratilov!

---

### CommandPost 1.2.9

#### 🔨 Improvements

- The "Shot Data" Toolbox has been improved. The duration is now always in the hh:mm:ss format. Fixed a bug where the CSV output would be broken if a field is blank/empty in the Motion Template. Added a column in the CSV for "Shot ID" and "Image Filename". Images are now converted to PNG files for consistency. Thanks for your feedback Vigneswaran Rajkumar!
- "Rendering During Playback" is now disabled when performing Batch Export to improve performance and reliability. Thanks for the suggestion Mitchell!
- Updated translations. Thanks to everyone who submitted fixes!

#### 🐞 Bug Fixes

- Fixed a bug when applying transitions in cases where there's multiple transitions with the same name. We now properly take into account the theme name as well. Thanks for reporting Selina Tannenberg!
- Fixed a bug in the Loupedeck Manager, which could prevent changes to Loupedeck layouts from saving correctly. Thanks for reporting Knut Hake & Kuba Rok!
- Fixed a bug that would cause CommandPost to fail to load if you were running an application that had no application bundle identifier. Thanks for reporting Helder S Ribeiro!
- Fixed a bug that would cause actions that changed the speed of clips in Final Cut Pro (such as "Speed to -50%") to fail. Thanks for reporting Prawit Sarathamwuthikul!
- Fixed some potential errors with MIDI banks. Thanks for reporting Marco Malaca!

---

### CommandPost 1.2.8

#### 🐞 Bug Fix

- Fixed a bug where CommandPost might not list the correct Share Destinations in the Timeline Batch Export tool if running Final Cut Pro 10.5 or later. Thanks for reporting Chris Walton & David Kuckhermann!

---

### CommandPost 1.2.7

#### 🐞 Bug Fixes

- Fixed a bug where CommandPost Overlays in Final Cut Pro wouldn't work correctly in some specific dual screen custom Workspace layouts. Thanks for your awesome assistance tracking this down Joseph Linaschke!
- Fixed a bug in the CommandPost download DMG, where the "Applications" alias was pointing specifically to "/Macintosh HD/Applications" instead of "/Applications". Thanks for reporting Iain Anderson!

---

### CommandPost 1.2.6

#### 🎉 New Features

- Added actions to trigger virtual mouse wheel actions. Thanks for suggesting Mikhael Pacheco!
- Added actions to trigger virtual Trackpad gestures.

#### 🔨 Improvements

- The feedback form will now always appear on top of other windows, even if the Debug Console has "Always On Top" enabled. Thanks for suggesting William Dalrymple!
- Added a new Touch Bar icon for Audio Fade In & Out. Thank Dani Ditu!

#### 🐞 Bug Fixes

- Fixed a bug which prevented the Colour Temperature controls from working on Tangent Panels. Thanks for reporting 천동주!

---

### CommandPost 1.2.5

#### 🎉 New Features

- Added option to "Ignore Every Second P1 to P8 Wheel Command" and "Ignore Every Second Control Dial Command" in the Loupedeck+ Preferences panel. This is because on some models of the Loupedeck+ the P1-P8 wheels and/or the Control Dial will trigger two actions for every hardware "click". Thanks for reporting Davvi!
- Added a search bar to allow you to filter plugin in the Plugins Preferences panel. Thanks for suggesting Shahin Shokoui! We've also added the ability to open each plugin in your preferred Text Editor, and have added an explanations of how plugins work at the top of the panel.

#### 🔨 Improvements

- The Jog & Nudge actions for Final Cut Pro in Monogram Creator now make sure the timeline is in focus prior to moving the playhead. Thanks for suggesting Andy Hayes!
- The ability to attach a screenshot when sending feedback is now disabled by default for your privacy protection. Thanks for suggesting William Dalrymple!
- The feedback form no longer tries to populate your full name and email from the Contacts app, to avoid any privacy concerns. Thanks for suggesting Joseph Linaschke!

#### 🐞 Bug Fixes

- Fixed potential bug when using a secondary monitor in Final Cut Pro. Thanks for reporting Dale Ryan Leckie!
- Fixed potential bug when CommandPost is trying to detect the timeline in Final Cut Pro.
- Fixed potential bug when triggering certain menu items in Final Cut Pro. Thanks for reporting Milos Jokic!

---

### CommandPost 1.2.4

#### 🎉 New Features

- Added a preference to disable User Interface Animations within Final Cut Pro. This will allow you to disable, for example, the animated fade effect of the "Custom Speed" window and the timeline Appearance popup when they open and close.
- Added an action to copy the Final Cut Pro Viewer contents to the Pasteboard. Thanks for suggesting Alex Gollner!
- Added an action to "commit multicam" within Final Cut Pro using automation. It’s a bit clunky, but it works. We essential “Reveal in Angle Editor”, then “Reveal in Browser”, mark an in-point, then connect that clip back on top of the timeline. Essentially a macro, like Timeline Batch Export. One day I hope to use the Pasteboard instead to make it a one click thing. Thanks for suggesting Knut Hake & Sam Pluemacher!
- Added actions to control the Anchor controls within the Final Cut Pro Video Inspector.
- Added actions to reset Compositing, Crop, Distort and Transform within the Final Cut Pro Video Inspector. Thanks for suggesting Nariman Gafurov!
- Added a "Retime to Duration" action for Final Cut Pro. This will trigger a "Custom Speed" action and select the "Duration" radio button, so that you can then just type in the new duration, rather than having to click it manually with the mouse.

#### 💪 Changes

- The wording on Monogram Preferences panel has been changed. You can now use the public version of Monogram Creator 4.1.11 or later, as opposed to just the beta and alpha releases.
- We now disable certain user interface animations within Final Cut Pro when triggering CommandPost actions, so that the actions are more responsive.

---

### CommandPost 1.2.3

#### 🎉 New Features

- Added support for the Loupedeck CT and Loupedeck Live beta firmware, which changes the connection method from a virtual ethernet port to a virtual serial port.
- Added support for multiple Loupedeck CT and multiple Loupedeck Live devices at the same time. Each device can now have its own unique layout.
- Added actions for triggering virtual mouse clicks. Thanks for suggesting Chase Guidroz!

#### 💪 Changes

- The setup screen no longer refers to the "satellite icon". Thanks for reporting Shahin Shokoui!

---

### CommandPost 1.2.2

#### 🔨 Improvements

- Improved the Search Console so that, for example, if you open it when setting up a layout for Final Cut Pro in the Loupedeck CT preferences, it now shows Final Cut Pro actions by default - but you still have access to all the other application actions by using one of the toolbar icons, or right-clicking on the Search Console to change which Action Groups you want to filter.
- Added a preference to the Loupedeck CT/Live Preferences to "Automatically Apply Icon From Action". Thanks for suggesting Eric Badura!
- We now automatically add a text label based on the action title, when you assign an action in the Loupedeck CT/Live Preferences.
- Added an action to "Reset Color Wheel" in Final Cut Pro, which resets all the controls for the selected color wheel. Thanks for suggesting Matthew H Green!
- Added the ability to delete custom applications from Loupedeck CT/Live preferences. Thanks for reporting Eric Badura!
- Improved the reliability of the Final Cut Pro Color Wheel Tint Controls on Tangent Panels. Thanks for reporting David Brown!

#### 🐞 Bug Fixes

- Fixed a bug where enabling then disabling a Loupedeck CT/Live vibration control wouldn't actually disable it, requiring you to reset the whole control to get rid of the vibration. Thanks for reporting Eric Badura!
- Fixes some mistakes in the German language translation for CommandPost. Thanks for reporting Eric Badura!
- Fixed a bug where resetting the Color Wheels on a Tangent Panel would not work correctly. Thanks for reporting Richard Guinand!
- Fixed a bug in our Final Cut Pro Angle Editor API. Thanks for reporting Sam Pluemacher!

---

### CommandPost 1.2.1

#### 🔨 Improvements

- When you click an action select button in the Loupedeck CT/Live Preferences panel, if there was previously an action already assigned, this name will now be automatically populated in the Search Console.
- When you click an action select button in the Loupedeck CT/Live Preferences panel, the selected action groups will now default to whatever application you currently have selected in the Loupedeck CT/Live Preferences. For example, if you're changing the layout for TextEdit, which you click an action select button, only the actions for TextEdit will appear by default. However, you can still access all the other application actions via the toolbar, or the right-click menu for complete control.

#### 🐞 Bug Fixes

- Fixed a bug in the Loupedeck CT/Live manager, where resizing some legacy icons could fail, preventing the Loupedeck screens from updating correctly. Thanks for reporting Eric Badura!
- Fixed some user interface issues in the Loupedeck CT/Live Preferences when the interface is in Dutch. Thanks for reporting Jeroen van Amerongen!
- The default Loupedeck Live layout incorrectly had actions for the Loupedeck CT, which just made things very confusing. This has now been corrected.

---

### CommandPost 1.2.0

#### 🎉 New Features

- We have a new dock and menubar icon by the incredible Matthew Skiles. Woohoo!
- We have also added the option to select 5 new built-in menubar icons, or select any image from your machine to use as a menubar icon. You can also now customise the menubar text label for full control.
- We now support the Monogram and Palette control surfaces. CommandPost integrates closely with the Monogram Creator, so once you enable Monogram support in CommandPost, you can jump into Monogram Creator to set up your layout. It also supports Automatic Profile Switching. Monogram support requires the latest beta or alpha builds of Monogram Creator - it won't work on the public release yet. Any ideas, comments, suggestions welcome!
- You can now use Lua Snippets to programatically generate Loupedeck CT/Live icons, and also define the LED color. With some simple lines of code, you can now make your Loupedeck device appear exactly how you want it. There's a new option in the preferences to adjust the refresh frequency (defaults to 1 second).
- Added option to "Resize Images on Import" and set a custom "Image Background Colour on Import" in the Loupedeck CT/Live Preferences panel.
- Added ability to customise the font, font size and colour of text labels in the Loupedeck CT/Live Preferences panel.
- Added the ability to consolidate images when using the Shot Data Toolbox. This means if you have any images "connected" to the Shot Data Motion Template in your timeline, they'll be copied to the same location as the CSV export. Thanks for the suggestion Vigneswaran Rajkumar!
- Added actions to control the individual red, green and blue parameters for the Color Wheels in Final Cut Pro. Thanks for suggesting Eric Badura!

#### 🔨 Improvements

- We've renamed "All Applications" to "Unlisted & Ignored Applications" in the Control Surfaces panels to better describe what this option does.
- We've improved how the Search Console searches and orders the results.
- Updated all the translations, and improved the Lua documentation.
- Various user interface improvements in the Preferences and Control Surfaces windows.

#### 🐞 Bug Fixes

- Fixed a bug in both the Shot Data Toolbox, Save Browser Contents to CSV and Save Timeline Index to CSV. Thanks for reporting Aaron Villa!
- Various improvements and bug fixes in the Loupedeck CT/Live Preferences panels - especially in regards to dragging and dropping icons. Thanks to Eric Badura for all your testing and ideas!

---

### CommandPost 1.1.5

#### 🎉 New Features

- If you assign an action to a Loupedeck CT/Live Touchscreen button that has an image in the Search Console, that image will now be automatically applied to the button. For example, if you apply the action to launch Disk Utility to a Loupedeck CT/Live Touchscreen Button, the Disk Utility icon will be automatically applied. Thanks for suggesting Eric Badura!
- You can now select Applications (in addition to image files) when you click the Image Drop Zone in the Loupedeck CT/Live Control Surfaces panel.

---

### CommandPost 1.1.4

#### 💪 Changes

- On a fresh installation, CommandPost will no longer ask you if you want to copy the CommandPost application to your application folder. Instead, you should manually copy CommandPost to the application folder via the Applications shortcut in the DMG package. This has been changed to get around issues where people want to install CommandPost in their user-specific application folder, or when there's permission issues trying to copy CommandPost across, which can happen on some Big Sur installations.

#### 🐞 Bug Fixes

- Fixed the "Zoom to selection" action in Final Cut Pro. Thanks for reporting Jeffrey Linneman!
- Fixed the "Save Current Frame" option in the Final Cut Pro Viewer Overlay popup. Thanks for reporting David Brown!

---

### CommandPost 1.1.3

#### 🎉 New Features

- Added actions that adjust the Position controls in Final Cut Pro's inspector in reverse using MIDI. Thanks Joe Dull!
- Added an action to "Toggle Opacity Fade Handles in Video Animation Popup on Selected Clips". Thanks for the suggestion Ripple Training! Unfortunately, due to a bug in Final Cut Pro's Accessibility API this doesn't work for clips within a secondary storyline container.
- Added preferences to change the Search Console width and height. This can be found when you right click on the Search Console. Each individual Search Console has its own unique width and height (i.e. the Search Console in Final Cut Pro can be different than in After Effects).

#### 🔨 Improvements

- DaVinci Resolve & After Effects Tangent support is now disabled by default on a fresh install.
- Updated the Shot Data Motion Template, so that it works with all common aspect ratios. Thanks Iain Anderson!
- We've removed the EULA from the CommandPost DMG, and updated the tag-line to match the website.
- We've adjusted the window sizes on Big Sur so there's not as much wasted space at the bottom of the windows.
- The Shared Pasteboard will no longer prompt you on CommandPost's startup if the shared folder is not accessible. This means that if you're using something like PostLab Drive, the Shared Pasteboard will now work when the drive is connected, and you won't get notified if the drive becomes disconnected. Thanks for reporting Dale Ryan Leckie!

#### 🐞 Bug Fixes

- Fixed a bug where the menu bar actions had the wrong menu path in the Search Console subtext.
- Fixed a bug where you will be asked for Accessibility Permissions straight away on a fresh install. Thanks for reporting Iain Anderson!

---

### CommandPost 1.1.2

#### 🐞 Bug Fixes

- Fixed a bug that could cause the hue control in the Final Cut Pro Colour Wheels to change its value to 90 degrees when CommandPost first loads, if the Colour Wheel is active on a clip. Thanks for reporting Valerio D'Andrassi.

#### 🔨 Improvements

- The Shot Data Motion Template has been updated. Thanks Vigneswaran Rajkumar!

---

### CommandPost 1.1.1

#### 🔨 Improvements

- We've added some caching to dramatically increase the responsiveness of control surfaces, such as the Loupedeck CT. This has massive improvements for controlling the Color Wheels with the Loupedeck CT Touch Screen, for example.

#### 🆕 New Actions

- We've added new actions to control the Final Cut Pro Color Board, by increments of 1, 2, 3, 4, 5 and 10. They are all contained within their own Action Group called "Color Board" on the Search Console. Thanks for suggesting Eric Badura!

#### 🐞 Bug Fixes

- Fixed the Hue controls on Tangent Panels. Thanks for reporting Robert J. Bradshaw!
- Fixed an error that could occur randomly when refreshing Loupedeck devices. Thanks for reporting Eric Badura!
- Some actions that used popup menus (such as "Show Horizon") weren't working correctly. This is now fixed. Thanks for reporting Adam Terlanda!
- Some fields weren't being correctly exported in the Shot Data Toolbox Utility. This is now fixed. Thanks for reporting Vigneswaran Rajkumar!
- Fixed a bug which cause a MIDI error when launching ### CommandPost 1.1 or later for the first time. Thanks for reporting Scott Dodson!
- Fixed a bug where Stream Deck settings weren't migrated from ### CommandPost 1.0.6 (or earlier) to 1.1 (or later). The Final Cut Pro and All Applications settings are now automatically migrated to the Stream Deck Unit 1.

---

### CommandPost 1.1.0

#### 🎛 Control Surfaces Support

- Control Surfaces have been moved out of Preferences into their own window.
- Added Loupedeck (original), Loupedeck CT and Loupedeck Live support.
- Added Stream Deak XL and Stream Deck Mini support.
- Added TourBox support.
- Added placeholder Control Surface panels for Monogram and Gamepad, with an explanation of how to use these control surfaces with CommandPost until we add built-in support.
- MIDI, Loupedeck & Stream Deck Preferences panels now support Custom Applications.
- AudioSwift now correctly works with CommandPost's MIDI functionality. Thanks for reporting Nigel Rios!
- Added Skype, Microsoft Teams, Zoom, Disk Utility, System Preferences and TextEdit to the default Control Surfaces application drop-down lists. However, currently there is only basic keyboard shortcut actions for Skype.
- Tangent panel support has been re-engineered to support multiple CommandPost applications within Tangent Mapper (i.e. you can now have a completely seperate Tangent Mapper layout for Final Cut Pro and DaVinci Resolve). Better support for DaVinci Resolve will come in a future beta - this release it just laying the foundations.

#### 🧰 Toolbox Utilities

- The FCPXML Titles Processor allows you update the titles within a FCPXML, based on new data from a CSV file. This utility was commissioned by Connor Eberhart.
- Shot Data is new specialised Toolbox utility that allows you to import a FCPXML which contains one or more Shot Data Titles in a timeline, and converts the data from these Motion Templates into a single CSV file for use in other applications. This feature has been commissioned by Vigneswaran Rajkumar for his upcoming feature film.

#### 🎉 New Features

- Added non-keyboard shortcut actions for Final Cut Pro Browser Clip Height & Browser Duration.
- Added speed rate actions for 40, 50, and 200.
- Added actions to increase and decrease display brightness.
- Added actions for adjusting opacity in Final Cut Pro.
- Added actions for Filmstrip & List Mode in the Final Cut Pro Browser.
- Added a Contrast action for Final Cut Pro which adjusts shadows & highlights brightness at the same time.
- Added actions for Timeline Zoom (using the Appearance Popup). Thanks for suggesting Prescott Van Leer!
- All your Keyboard Maestro Macros are now available in the Search Console as actions.
- Added initial support for Adobe After Effects. There are now actions for each individual effect in After Effects, as well as actions for all the shortcut keys and menubar items.
- Added actions for Zoom keyboard shortcuts. Thanks for your assistance Jonathan Zuck!
- CommandPost can now generate menu bar actions for all Custom Applications.
- Added an option to create Captions when using the Text To Speech feature in Final Cut Pro. Thanks for the suggestion Vigneswaran Rajkumar!
- Added actions that allow you to "emulate" a Tangent Element panel in DaVinci Resolve. This feature requires Tangent support to be enabled, and at least one physical Tangent device to be connected to your machine (i.e. a Tangent Ripple). This means you can now use Tangent Mapper to customise your DaVinci Resolve layout for any Tangent panel, as well as trigger Tangent actions from any other control surface or shortcut key (i.e. you can control a colour wheel from a Loupedeck CT or TourBox). It also means you can control DaVinci Resolve from a Tangent Arc or CP200.
- Added a Contrast Color Wheel control to Tangent Mapper. Thanks for suggesting Von Jackson!

#### 🔨 Improvements

- Recompiled CommandPost to natively support Apple Silicon.
- Improved the method we detect "Screen Recording" permissions on macOS Catalina & Big Sur.
- We now use Sentry instead of Firebase Crashlytics for tracking crashes.
- CommandPost now uses Lua 5.4.
- We've made lots of changes and improvements to our underlying Final Cut Pro X API. These changes should make writing your own Lua Snippets a lot more simple and easy to understand.
- The Search Console now loads faster, and displays a "loading" message when the contents of the Search Console is still populating. We've also adjusted the way the Search Console orders its results to improve usability.
- Added more Touch Bar icons. Thanks Daniele Di Tuccio!
- Changed the way we trigger shortcut keys for better performance.
- HUD now watches for Viewer resizing.
- Browser Playhead Highlight now follows playhead when visible.
- "Select Clips Forward/Backwards" actions now selects clips with speed handles.
- Timeline Batch Export now correctly handles clips with speed handles visible.
- Removed unnecessary "Failed to cache User Effects Presets” debug message in Plugin Scanner.
- Added option to enable/disable all draggable guides in Final Cut Pro Viewer Overlay.
- Improved the performance of the Video Inspector actions.
- Improved the MIDI Controls for Colour Wheels, so that you can use both the horizontal and vertical actions at the same time. This allows you to use the controls smoothly in AudioSwift using X/Y mode. Thanks for reporting Nigel Rios!
- Added relative MIDI actions for controlling the Final Cut Pro Colour Board. Thanks Nigel Rios!
- We now just play an error sound instead of showing a dialog box when a menubar action cannot be triggered. Thanks Knut Hake!
- You can now use a velocity value for the "Note Off" and "Note On" MIDI commands. The velocity is also now detected and filled out in the MIDI Preferences panel when you use the "Learn" button. Thanks Nigel Rios!
- Improved the "Relative A" MIDI Controls for the Color Board & Color Wheels, for use with AudioSwift (and other MIDI devices).
- "Sections" in the Search Console has been renamed to "Show Action Groups", and is now grouped by application.
- The "Text to Speech" feature has been re-designed and improved.
- Actions that trigger virtual keyboard presses now take into account any modifier keys triggered by the "Press and hold Modifier Key" actions. Thanks for reporting Flavio Saramin!

#### 🐞 Bug Fixes

- Fixed Touch Bar support on 16-inch MacBook Pro.
- Fixed bug in Search Console where toggling “Search Subtext” wouldn’t take affect until the Search Console was closed and re-opened.
- Fixed bug where the Effects & Transitions search box contents would not be restored correctly after applying an effect or transition via an action.
- Fixed bug in Notes HUD panel.
- Fixed bug in Final Cut Pro Crop Bottom Action.
- Fixed bug where double quotation marks in Snippet names prevented the Snippets from being editable.
- Fixed bug which prevented the "Clear" buttons in the Loupedeck+ preferences panel from working.
- Fixed a bug in the "Press and hold" modifier actions for CONTROL, OPTION and COMMAND. Thanks for reporting Knut Hake!
- Fixed a bug where the "Make Pasteboard Text Uppercase/Lowercase/Camelcase" actions would not affect certain characters such as "å". Thanks for reporting Eivind Lie Nitter!
- Fixed a bug where the Search Console was incorrectly case sensitive.
- Fixed a bug which prevented the individual "Play" and "Pause" actions from functioning. A better description for these actions has also been added to the Search Console, so that it's clearer to understand their purpose (i.e. the play button only plays - it won't stop playback). Thanks for reporting Prescott Van Leer!
- Fixed a bug where Colour Wheel actions wouldn't not automatically change to the Colour Wheel Inspector if you were on the Colour Curves. Thanks for reporting Prescott Van Leer!
- Fixed a bug in the Timeline Batch Export tool, where sometimes CommandPost could fail to change the destination directory.
- Fixed a bug which prevented MIDI commands from applying correctly if you manually entered them in the MIDI Preferences panel (as opposed to using the "Learn" button). Thanks Nigel Rios!
- Fixed a bug in the Text to Speech function and Media Watch Folders where certain non-alphanumeric characters in filenames could cause the functions to fail. Thanks for reporting Vigneswaran Rajkumar!
- Fixed a bug which prevented Color Wheels from opening correctly in the Final Cut Pro Inspector when you moved a Tangent wheel or knob.
- Fixed a bug in MIDI Timeline Scroll action.
- Fixed a bug where the "Leave Files in Place" menubar item tick was incorrectly reversed. Thanks for reporting Mark Westcott!
- Fixed a bug that could cause certain items to not appear in the Search Console, due to a "Share Destinations" folder not existing on some machines. Thanks for reporting Peter Moss!
- Fixed a bug with the Jog/Shuttle control for Tangent Panels in Final Cut Pro. Thanks for reporting Vigneswaran Rajkumar!
- Fixed a bug where a deleted Media Watch Folder would reappear when you restarted CommandPost. Thanks for reporting Erik Lathouwers, Matt Steeves & Jiří Fiala!
- Fixed a bug which prevented Color Board controls from working in some newer versions of Final Cut Pro when the interface was in German. Thanks for reporting Eric Badura!
- Fixed a bug that would cause an error if you tried to Restore a Browser Layout that wasn't previously saved. Thanks for reporting Gábor Kertai!

---

### CommandPost 1.0.6

🎉 New Feature

- Improved the Batch Rename HUD. You can now add sequential numbers to clip names. Thanks for the suggestion Vigneswaran Rajkumar! You can also process clip names with custom Lua code, giving you the ultimate renaming freedom.

#### 🐞 Bug Fix

- Fixed bug in "Color Wheel - Midtones - Brightness - Down" actions. Thanks for reporting Valerio D'Andrassi!

---

### CommandPost 1.0.5

#### 🎉 New Features

- Added additional Colour Wheel actions for different increments. For example, you can now increase or decrease the Tint by 0.1, 0.2, 0.3, 0.4, 0.5, 1, 5 or 10. This applies to Saturation, Brightness, Tint, & Temperature. Thanks for suggesting Rafa Alejandro!
- Added actions to trigger custom keyboard shortcuts (for example COMMAND+C).

#### 💪 Changes

- CommandPost will now prompt for Screen Recording permissions on macOS Catalina, and will not start until those permissions are granted. CommandPost requires Screen Recording permission on macOS Catalina to detect the state of various user interface elements - for example, to detect when Final Cut Pro is playing or stopped. We also allow users to optionally share screenshots when submitting feedback.
- The CommandPost Dock Item is now disabled by default. You can change this in CommandPost's General Preferences panel if required.
- The contextual menu that appears when you right-click on the top of the Final Cut Pro Viewer is now disabled by default. You now have to click "Enable Viewer Contextual Menu" from the CommandPost menubar to enable it.
- The Uninstall tool now removes all of CommandPost's permissions in macOS Catalina.

#### 🐞 Bug Fixes

- Fixed a bug that prevented Timeline Batch Export from working correctly in macOS Catalina. Thanks for reporting Chris Walton!
- Fixed a bug that prevented the Batch Name Tool in the HUD from permanently renaming items in the browser. Thanks for reporting Vigneswaran Rajkumar!
- Fixed bug in Timeline Batch Export. Thanks for reporting Rima H. Bassil!
- Fixed a bug which prevented the "Reveal Multicam Clip in Browser" action from working correctly.

#### 翻訳 Translations

- Added Danish Translation. Thanks for adding Patrick Fust!

---

### CommandPost 1.0.4

#### 🐞 Bug Fix

- Fixes a bug introduced in 1.0.3 that can prevent Effects & Generators from being applied correctly. Thanks for reporting Anton Lopez & Wayne Kopping!

---

### CommandPost 1.0.3

#### 🎉 New Feature

- Added option to "Use Better Quality in Angles Viewer" in the Advanced Final Cut Pro Preferences.

#### 🔨 Improvements

- Added a preference to enable or disable the Text Pasteboard History, and also set a History Size in the Finder Preferences panel. The Text Pasteboard History is now off by default.
- CommandPost now disconnects from Tangent Hub when the Color Finale 2 window is open, allowing you to control Color Finale 2 with Tangent Panels. When you close the Color Finale 2 window, CommandPost reconnects to Tangent Hub.

#### 🐞 Bug Fixes

- The "Select Active/Topmost Library in Browser" actions now put focus on the Browser Sidebar when triggered so that the Library becomes active in the Inspector. Thanks for reporting Mads Larsen Nielsen!
- Fixed a bug where Final Cut Pro could freeze temporarily when importing clips from a Media Watch Folder notification. Thanks for reporting Corky Ballas!

---

### CommandPost 1.0.2

#### 🎉 New Features

- You can now apply multiple Compressor presets to the same watch folder.
- Added Final Cut Pro X preference for "Correct Spelling Automatically". Thanks for the suggestion Afshin Rohani!
- Added support for IFTTT Notifications. Thanks [JFtechOfficial](https://github.com/JFtechOfficial) for implementing!
- Added action for "Select Topmost Library in Browser" and "Select Active Library in Browser". Thanks for the suggestion Mads Larsen Nielsen!

#### 🐞 Bug Fixes

- Improved reliability of "Change Duration" menu item action. Thanks for reporting Vigneswaran Rajkumar.
- Fixed the naming of destinations in Timeline Batch Export if you have a fresh install of Final Cut Pro X without any custom destinations.
- Updated the Final Cut Pro, Motion & Compressor Feedback Form assistant.
- Fixed bug when disabling the Custom Touch Bar on Mojave.

#### 🧨 Workarounds

- The Touch Bar features are currently not working correctly on the new 16-inch MacBook Pro so we have temporarily disabled Touch Bar support on these machines until we can come up with a proper fix. If anyone has any ideas, please get in touch.

#### 翻訳 Translations

- Added Hungarian Translation. Thanks Gyula Hegedüs!

---

### CommandPost 1.0.1

#### 🐞 Bug Fixes

- Fixed a bug where the Timeline Batch Export feature would not list all the installed Destination Presets. Thanks for reporting Edgar Davis!
- Fixed a bug where Snippets assigned as an action (i.e. as a keyboard shortcut) would not trigger the latest Snippet code if the Snippet was updated in the Preferences panel after being assigned. Thanks for reporting Stefan Benz!

#### 🎉 New Additions

- Added Polish Translation. Thanks Robert!

---

### CommandPost 1.0.0

Woohoo! 🎉

After **78 releases*- of FCPX Hacks and **91 beta releases*- of CommandPost, we're extremely excited to announce that we're finally removing the beta label from CommandPost.