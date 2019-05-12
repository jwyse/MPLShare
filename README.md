# MPLShare
Tone Capture sharing, for Mooer Preamp Live users

## Features
* Read `.mo` preset files exported from MPL (v1.0.0, 1.0.1, and 2.0.0 formats) [complete]
* Read `.mbf` full backup files exported from MPL (v2.0.0 format) [complete]
    * Extract individual presets (as `.mo` files) from a full backup file, without restoring the backup to your Preamp Live [complete]
        * This can be used as a workaround for the [bug](https://github.com/jwyse/MPLShare/blob/master/studio-v2-bug.md) that prevents exporting Tone Captures from v2.
* Convert v2.x preset files to v1.x-compatible file format [in progress]
* Enable users to upload their presets and full backups, with a description of the tone(s) that they captured
    * example: "Marshall JVM410H, CH2 Orange, mids boosted"
    * Submitters and other users can tag presets: `highgain`, `classicrock`, `clean`, etc. [planned]
    * Users can rate uploaded presets [planned]
* The database is searchable...
    * by preamp model: using Mooer's nickname, or the amp-based-on name (`gas station` or `diezel`) [complete]
    * by Tone Capture (raw preset parameters vs. presets that include a Tone-Captured amp) [in progress]
    * by tags (`classicrock`, etc) [planned]

## Bug in Mooer Studio for Preamp Live software, version 2.0.0
There appears to be a bug in version 2.0.0 of the **Mooer Studio for Preamp Live** ('Studio') software for Windows (and possibly the Mac version also).  When saving individual presets from the `Library` in Studio, the exported .mo file will contain the preset parameters, but NOT the Tone Capture.  I have submitted a support request to Mooer.  If you have the same issue, please consider submitting your own support request to Mooer -- if more people have this problem, they're more likely to fix it (faster).  [Read more here](https://github.com/jwyse/MPLShare/blob/master/studio-v2-bug.md).

<!--
:white_check_mark: [complete] / :running: [in progress] / :hourglass: [planned]

complete
:bulb:
:ballot_box_with_check:
:heavy_check_mark:
:white_check_mark:
:thumbsup:
in progress
:running:
planned
:star:
:hourglass:
-->

## Proof of Concept
Ultimately, this project will be a web application, where users can search for presets or upload their own.  At this stage, I'm focused on the data parsing and storage, and testing that using a console.

Parsing a preset from .mo file
![display single preset](https://github.com/jwyse/MPLShare/raw/master/img/poc-display-preset.png)

Searching presets by preamp model (using Mooer's nickname, or the actual Based-On name)
![search](https://github.com/jwyse/MPLShare/raw/master/img/poc-search.png)

Parsing individual presets from full backup (.mbf) files
![Full backup](https://github.com/jwyse/MPLShare/raw/master/img/poc-parsed-full-backup.png)

Extract and export individual .mo presets from a full backup (.mbf) file
![Extract presets](https://github.com/jwyse/MPLShare/raw/master/img/poc-extract-presets-from-backup.png)

### Disclaimer
I am not affiliated with Mooer in any way, except that I've purchased a few of their products via normal retail.

This project is not blessed or supported by Mooer in any way.
