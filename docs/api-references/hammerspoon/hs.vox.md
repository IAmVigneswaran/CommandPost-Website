# hs.vox

Controls for VOX music player

---

## API Overview
**Functions** - _API calls offered directly by the extension_
 * [addurl](#addurl)
 * [backward](#backward)
 * [decreaseVolume](#decreasevolume)
 * [fastBackward](#fastbackward)
 * [fastForward](#fastforward)
 * [forward](#forward)
 * [getAlbumArtist](#getalbumartist)
 * [getCurrentAlbum](#getcurrentalbum)
 * [getCurrentArtist](#getcurrentartist)
 * [getPlayerState](#getplayerstate)
 * [getUniqueID](#getuniqueid)
 * [increaseVolume](#increasevolume)
 * [isRunning](#isrunning)
 * [next](#next)
 * [pause](#pause)
 * [play](#play)
 * [playpause](#playpause)
 * [playurl](#playurl)
 * [previous](#previous)
 * [shuffle](#shuffle)
 * [togglePlaylist](#toggleplaylist)
 * [trackInfo](#trackinfo)


---

## API Documentation

### Functions


### [addurl](#addurl)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.vox.addurl(url)`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Add media URL to current list                                                                     |
| **Parameters**                              | <ul><li>url {string}</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul></ul>                |

---

### [backward](#backward)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.vox.backward()`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Skips the playback position backwards by about 7 seconds                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul></ul>                |

---

### [decreaseVolume](#decreasevolume)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.vox.decreaseVolume()`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Decreases the player volume                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul></ul>                |

---

### [fastBackward](#fastbackward)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.vox.fastBackward()`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Skips the playback position backwards by about 14 seconds                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul></ul>                |

---

### [fastForward](#fastforward)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.vox.fastForward()`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Skips the playback position forwards by about 17 seconds                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul></ul>                |

---

### [forward](#forward)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.vox.forward()`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Skips the playback position forwards by about 7 seconds                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul></ul>                |

---

### [getAlbumArtist](#getalbumartist)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.vox.getAlbumArtist()`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Gets the artist of current Album                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A string containing the artist of current Album, or nil if an error occurred</li></ul>          |
| **Notes**                                   | <ul></ul>                |

---

### [getCurrentAlbum](#getcurrentalbum)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.vox.getCurrentAlbum()`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Gets the name of the album of the current track                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A string containing the Album of the current track, or nil if an error occurred</li></ul>          |
| **Notes**                                   | <ul></ul>                |

---

### [getCurrentArtist](#getcurrentartist)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.vox.getCurrentArtist()`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Gets the name of the artist of the current track                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A string containing the Artist of the current track, or nil if an error occurred</li></ul>          |
| **Notes**                                   | <ul></ul>                |

---

### [getPlayerState](#getplayerstate)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.vox.getPlayerState()`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Gets the current playback state of vox                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>0 for paused</li><li>1 for playing</li></ul>          |
| **Notes**                                   | <ul></ul>                |

---

### [getUniqueID](#getuniqueid)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.vox.getUniqueID()`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Gets the uniqueID of the current track                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A string containing the name of the current track, or nil if an error occurred</li></ul>          |
| **Notes**                                   | <ul></ul>                |

---

### [increaseVolume](#increasevolume)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.vox.increaseVolume()`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Increases the player volume                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul></ul>                |

---

### [isRunning](#isrunning)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.vox.isRunning()`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns whether VOX is currently open                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A boolean value indicating whether the vox application is running</li></ul>          |
| **Notes**                                   | <ul></ul>                |

---

### [next](#next)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.vox.next()`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Skips to the next track                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul></ul>                |

---

### [pause](#pause)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.vox.pause()`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Pauses the current vox track                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul></ul>                |

---

### [play](#play)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.vox.play()`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Plays the current vox track                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul></ul>                |

---

### [playpause](#playpause)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.vox.playpause()`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Toggles play/pause of current vox track                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul></ul>                |

---

### [playurl](#playurl)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.vox.playurl(url)`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Play media from the given URL                                                                     |
| **Parameters**                              | <ul><li>url {string}</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul></ul>                |

---

### [previous](#previous)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.vox.previous()`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Skips to previous track                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul></ul>                |

---

### [shuffle](#shuffle)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.vox.shuffle()`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Toggle shuffle state of current list                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul></ul>                |

---

### [togglePlaylist](#toggleplaylist)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.vox.togglePlaylist()`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Toggle playlist                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul></ul>                |

---

### [trackInfo](#trackinfo)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.vox.trackInfo()`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Displays information for current track on screen                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul></ul>                |

---