# The Zodiac Archive — Solution

**Category:** OSINT
**Points:** 300

## Challenge

A private collector claims to possess four original letters attributed to the Zodiac Killer. Although all four appear authentic, investigators believe one contains a historical inconsistency. Examine the scans, verify the historical details using publicly available sources, and identify the forged document.

**Flag Format:** `Flag{YEAR_NAME}`

## Solution

The four letters appear nearly identical at first glance. A closer inspection reveals that Letter 3 uses a different postage stamp.

The intended approach is to reverse image search the postage stamp. The search identifies it as an American **[REDACTED]** commemorative stamp. The stamp prominently displays the year **[REDACTED]**, while the letter claims to have been written in **1971**. This historical inconsistency reveals that the document could not have existed as claimed.

Since the stamp's printed year contradicts the letter's claimed date of 1971, the document is historically inconsistent and is therefore the forged letter.

## Flag

*Redacted — identify the stamp's year and name, then format as `Flag{YEAR_NAME}`.*
