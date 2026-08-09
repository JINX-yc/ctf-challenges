# Signal Loss — Solution

**Category:** Cryptography
**Points:** 150

## Challenge

A short radio transmission was intercepted before the signal abruptly disappeared. Analysts believe the message has been encoded in multiple layers to conceal its true contents.

Recover the original message.

**Flag Format:** `0xV0ID{...}`

## Solution

The provided file is a `.wav` audio recording. Listening to it reveals a series of short and long beeps, suggesting that the transmission is encoded using **Morse code**.

The intended approach is to decode the Morse sequence using an online decoder, Audacity, or any Morse decoding tool. Decoding the audio produces the following hexadecimal string:

```
[REDACTED]
```

The resulting text is not yet the flag. The next step is to recognize that it is **hexadecimal-encoded ASCII**.

Decoding the hexadecimal string reveals the original message:

```
0xV0ID{REDACTED}
```

## Flag

```
0xV0ID{REDACTED}
```
