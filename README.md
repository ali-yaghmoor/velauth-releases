# Velauth releases

This repository holds nothing but published build artifacts for
[Velauth](https://velauth.com): the desktop installer, the agent installer and
the agent zip, plus a `SHA256SUMS` file for each release.

The source is not here and is not public.

## Why the downloads live here and not on velauth.com

A checksum published on the same site that serves the file proves very little.
Anyone able to replace the installer on that site can replace the checksum in
the same breath, and an administrator who diligently compares the two still
gets a match.

So the artifacts and their hashes are served from GitHub, which is separate
infrastructure from the marketing site. Someone who compromises velauth.com can
change the link on the download page, but cannot change the file or the hash,
because neither is hosted there. A changed link is also the kind of thing a
careful person notices, because the destination stops being github.com.

## Verifying a download

On the machine you downloaded to:

```powershell
Get-FileHash .\Velauth.Agent.Installer.msi -Algorithm SHA256
```

Compare the result against `SHA256SUMS` on the release you downloaded from.
Read that file from this repository, not from velauth.com.

## The installers are not code signed yet

Windows will warn you about an unknown publisher. That is expected for now and
code signing is in progress. Until it lands, the checksum above is how you
establish you have the file we published.

## Releases

See the [releases page](https://github.com/ali-yaghmoor/velauth-releases/releases).
Release notes are intentionally brief here; the product documentation lives at
[velauth.com](https://velauth.com).
