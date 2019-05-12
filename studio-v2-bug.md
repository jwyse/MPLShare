# Bug in Mooer Studio for Preamp Live, version 2.0.0

## What is the bug?
When saving individual presets from the Library in Studio, the exported `.mo` file will contain the preset parameters, but NOT the Tone Capture data.

It's easy enough to "share" presets by posting parameters, like "Preamp model 1 (Gas Station Clean), Gain:15, Volume:9, Bass:18, ...", so being able to export and share the Tone Captures from actual amplifiers is the best part of the Preamp Live.  And this bug basically prevents that from happening.

## Does this issue affect every Preamp Live / Studio v2.0.0?
I don't know.  Other users have reported the same issue, and I have found only *one* shared preset that was exported in v2 format, and contains Tone Capture data.  This bug might only affect the Windows version of Studio, or only some hardware, or only if the user followed a specific upgrade path to get the v2.0.0 firmware.

## Do I have this issue?
Here's how you can check whether your MPL pedal/software has this issue:
1. Capture a tone with your Preamp Live, or import someone else's preset file that contains a Tone Capture. (It doesn't seem to matter *how* the Tone Capture gets into your MPL pedal.)
2. Verify that the Tone Capture exists: ![Tone Captured](https://github.com/jwyse/MPLShare/raw/master/img/tone-captured.png)
3. Export the tone to your computer using Studio's `Library` feature.
4. View the exported `.mo` file with a hex editor like [OnlineHexEditor](https://www.onlinehexeditor.com) (online/no installation).
5. Look for data starting at offset 0x800 (800 in hex; 2048 if your hex editor displays offsets in decimal). ![Hex data](https://github.com/jwyse/MPLShare/raw/master/img/preset-with-tc.png)
    * If there's non-zero data there, then it DID export your Tone Capture.  I'd appreciate it if you would contact me and let me know what version of the software you're using (v2.0.0? Windows or Mac?), how you got to that version (upgraded from 1.0.0, or from 1.0.1?), and anything else that might help narrow down why this may not affect ALL users.
    * If that data is all zeroes through almost the end of the file (offset 0xFFF / 4095 in decimal), then **it did not export your Tone Capture**. ![Hex data](https://github.com/jwyse/MPLShare/raw/master/img/preset-without-tc.png)

## What should I do if I have this issue?
Please contact Mooer support, to encourage them to prioritize fixing this issue.

## Is there a way to export my tone captures?
Yes. Although exported preset files omit the Tone Capture data, the full backup file does include tone captures.  MPLShare is able to extract individual presets, as `.mo` preset files, from a full backup file (`.mbf`).
