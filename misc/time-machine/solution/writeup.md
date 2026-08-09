# Time Machine — Solution

**Category:** Misc
**Points:** 150–200

## Challenge

An old container image has been recovered from an unknown source. The contents may reveal more than expected. Explore carefully and uncover the hidden secret.

```
docker pull jinx69/timemachine:latest
```

## Solution

### 1. Pull the image

```
docker pull jinx69/timemachine:latest
```

### 2. Inspect the image history

Docker image layers often contain useful information. Running:

```
docker history --no-trunc jinx69/timemachine:latest
```

reveals entries such as:

```
useradd -m void
echo "void:(REDACTED)" | chpasswd
COPY flag.sh /opt/flag.sh
```

From this, we learn:
- A user named **void** exists.
- The password is **REDACTED**.
- A script named **/opt/flag.sh** is present.

### 3. Run the container

```
docker run -it jinx69/timemachine:latest
```

The container starts as the unprivileged `player` user, so reading the flag directly results in a permission error.

### 4. Switch to the correct user

```
su void
```

Password: `REDACTED`

### 5. Execute the flag script

```
/opt/flag.sh
```

Output:

```
0xV0ID{REDACTED}
```

## Flag

```
0xV0ID{REDACTED}
```
