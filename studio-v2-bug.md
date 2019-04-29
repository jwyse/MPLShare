# Bug in Mooer Studio for Preamp Live, version 2.0.0

## What is the bug?
When saving individual presets from the Library in Studio, the exported `.mo` file will contain the preset parameters, but NOT the Tone Capture data.

It's easy enough to "share" presets by posting parameters, like "Preamp model 1 (Gas Station Clean), Gain:15, Volume:9, Bass:18, ...", so being able to export and share the Tone Captures from actual amplifiers is the best part of the Preamp Live.  And this bug basically prevents that from happening.

## Does this issue affect every Preamp Live / Studio v2.0.0?
I don't know.  Other users have reported the same issue, and I have found only *one* shared preset that was exported in v2 format, and contains Tone Capture data.  This bug might only affect the Windows version of Studio, or only some hardware, or only if the user followed a specific upgrade path to get the v2.0.0 firmware.

## Do I have this issue?
Here's how you can check whether your MPL pedal/software has this issue:
* Capture a tone with your Preamp Live, or import someone else's preset file that contains a Tone Capture. (It doesn't seem to matter *how* the Tone Capture gets into your MPL pedal.)
* Verify that the Tone Capture exists: [img/tone-captured.png]
* Export the tone to your computer using Studio's `Library`
* Use a [hex editor](https://www.onlinehexeditor.com) to view the exported `.mo` file.
* Confirm whether there is data starting at offset 0x800 (hex; 2048 in decimal). [img/preset-with-tc.png]
    * If there's non-zero data there, then it DID export your Tone Capture.  I'd appreciate it if you would contact me and let me know what version of the software you're using (v2.0.0? Windows or Mac?), how you got to that version (upgraded from 1.0.0, or from 1.0.1?), and anything else that might help narrow down why this may not affect ALL users.
    * If that data is all zeroes through the end of the file, then **it did not export your Tone Capture**.

## How did you find this issue?
Immediately after I bought my Preamp Live, I upgraded the software+firmware to v1.0.1 (it shipped with v1.0.0), and then v2.0.0.  I captured the tone of my favorite amp, and exported it.  I tried out a few presets that other users had shared, and eventually did a factory reset and tried to restore my own preset with my tone capture... but there was no tone capture.

I downgraded my software+firmware back to v1.0.0 and confirmed that exported presets do contain tone capture data, as expected.  Then I upgraded to 1.0.1 and confirmed that it still works.  Then I upgraded to 2.0.0 and confirmed the bug again.  Other users have reported the same issue in a Facebook group.

## What should I do about it?
Please contact Mooer support, to encourage them to prioritize fixing this issue.
