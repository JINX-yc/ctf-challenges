# Blue Anchor Imports — Solution

**Category:** OSINT
**Difficulty:** Medium

## Challenge

An anonymous tip claims that Blue Anchor Imports, a specialty foods importer, is actually a front for laundering money through international shipping containers.

Investigators managed to obtain a single photograph of a container believed to be involved in the operation. No other evidence is available.

Follow the digital trail, unravel the network behind the company, and identify the real person running the operation.

**Flag Format:** `Flag{full_name}`

At first glance, the only artifact provided is a photograph of a shipping container.

## Step 1: Inspect the Image Metadata

Running `exiftool` on the image reveals the metadata, and among the fields are:

```
Artist       : todwell
XP Comment   : hehe 67
```

The metadata suggests the name `todwell`, while the comment hints that `67` should also be included. Combining them gives: `todwell67`

## Step 2: Find todwell67

Searching for `todwell67` leads to a Reddit account: `u/todwell67`. The account contains a post featuring a photograph.

## Step 3: Geolocate the Photograph

The harbor photo was taken from **Grand Avenue Park** overlooking **Port Gardner Bay** in Everett, Washington (found via reverse image search). Once the location is identified, the next step is checking whether the same user has any other public account tied to that location.

## Step 4: Search the Reviews

Looking at reviews for the location reveals that Todwell left a review, which contains a reference to a ControlC page:

```
https://controlc.com/988i8c3k
```

## Step 5: Reading the Note

Opening the ControlC page reveals what appears to be an old personal note referencing a password-protected Pastebin archive:

```
https://pastebin.com/hfZ2aqWn
```

## Step 6: Obtain the Password

The Pastebin requires a password. Going back through the investigation, the Reddit account contains a self-comment:

```
am i cooked if i'm still using [REDACTED]
```

The password is therefore: `[REDACTED]`

## Step 7: Opening the Protected Paste

Entering the password unlocks the archive. The page contains a public Google Drive link to a PDF.

## Step 8: Inspecting the PDF

The PDF appears to be an ordinary settlement document from Blue Anchor Imports. A QR code is embedded within the document.

## Step 9: Scanning the QR Code

Scanning the QR code returns a base64-encoded string:

```
[REDACTED]
```

Decoding it reveals the identity of the person running the operation — this is the flag payload:

```
[REDACTED]
```

## Flag

```
Flag{REDACTED}
```

---
