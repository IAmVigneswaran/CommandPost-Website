# hs.noises

Contains two low latency audio recognizers for different mouth noises, which can be used to trigger actions like scrolling or clicking.
The recognizers are also high accuracy and don't use much CPU time.

This module was written by [Tristan Hume](http://thume.ca/). If you have any issues with or questions about the recognition, email him.
All first person references in this module's documentation refer to him.

The detectors are tuned so that they work for most people and most microphones. For best results use a highly directional headset microphone so that it doesn't pick up other people and background
noises around you, and put the boom off to the side of your mouth so you aren't directly breathing on it.

The two mouth noises (and their corresponding event numbers) are:

### "sssssssssss"
The "sssss" noise/syllable is easy to make and can be made continuously. The detector emits an event `1` when you start saying "sss" and a `2` after you stop.
It's good to hook up to variable-length actions like clicking/dragging and scrolling. It can detect very quiet noises so even just barely saying "ssss" under your
breath should trigger it without annoying anybody else around you too much. It works with most "sss" syllables but I find sharper is better, in crispness that is, loudness doesn't matter much.
It has a very low false negative rate, but often has false positives. It will obviously trigger in english speech since "s" is a common syllable, but with some microphones breathing in certain ways
will trigger it as well. Personally I use this to scroll down, it allows me to read long articles and books lying down with my laptop without awkward hand positioning to scroll with the trackpad.

### Lip Popping
Popping your lips is harder to do reliably and can't be done for variable lengths of time. The detector calls your callback with the number `3` when it detects one.
This detector has an almost zero false positive rate in my experience and a very low false negative rate (when you manage to make the sound).
Personally I use this to scroll up by a large increment in case I scroll down too far with "sss", and when my RSS reader is focused it moves to the next article.
The only false positives I've ever had with this detector are various rare throat clearing noises that make a pop sound very much like a lip pop.

---

## API Overview
**Constructors** - _API calls which return an object, typically one that offers API methods_
 * [new](#new)

**Methods** - _API calls which can only be made on an object returned by a constructor_
 * [start](#start)
 * [stop](#stop)


---

## API Documentation

#### Constructors


### [new](#new)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.noises.new(fn) -> listener`                                                                    |
| **Type**                                    | Constructor                                                                     |
| **Description**                             | Creates a new listener for mouth noise recognition                                                                     |
| **Parameters**                              | <ul><li>A function that is called when a mouth noise is recognized. It should accept a single parameter which will be a number representing the event type (see module docs).</li></ul> |
| **Returns**                                 | <ul><li>An `hs.noises` object</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/noises/libnoises.m line 236](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/noises/libnoises.m#L236) |

---

#### Methods


### [start](#start)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.noises:start() -> self`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Starts listening to the microphone and passing the audio to the recognizer.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>The `hs.noises` object</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/noises/libnoises.m line 205](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/noises/libnoises.m#L205) |

---


### [stop](#stop)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.noises:stop() -> self`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Stops the listener from recording and analyzing microphone input.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>The `hs.noises` object</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/noises/libnoises.m line 189](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/noises/libnoises.m#L189) |

---

