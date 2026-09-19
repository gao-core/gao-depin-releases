# gao-depin-releases

**Binary distribution repository for Gao DePIN.** This repository publishes release artifacts
of the Gao DePIN app (today: the Android APK) as immutable GitHub Release assets so that they
can be downloaded directly, by anyone, from a stable URL.

**Canonical source remains in the private `gao-core/gao-depin` repository.** This repository
contains no source code, no source history, no signing keys, no wallet material, no node
identities, no credentials and no internal logs — only public release metadata, and the
release assets attached to each tag.

## What is here

| Path | Content |
|---|---|
| `releases/<tag>/artifact-record.json` | the machine-readable identity of every artifact published under that tag: filename, source repository and commit, SHA-256, size, package, version, signer fingerprint, release tier, acceptance |
| `releases/<tag>/SHA256SUMS` | the SHA-256 of every asset of that release, `sha256sum -c` / `shasum -a 256 -c` shaped |
| GitHub Releases | the artifacts themselves, attached to the tag named in the record |

## Distribution policy

- **Immutable.** A release asset is never replaced, re-uploaded, renamed or deleted once
  published; a newer build is published under a new tag. Tags are never moved.
- **Source-addressed.** A tag names the source revision it was built from
  (`depin-<platform>-<tier>-<sha8>`), and the record binds the exact commit of the canonical
  repository. A tag here does not point at that commit — the source is private — the record does.
- **Byte-exact.** An asset is the exact accepted artifact: never rebuilt, re-signed, aligned,
  recompressed or repackaged for publication. Its SHA-256 is measured from the bytes and listed
  in the record, in `SHA256SUMS` and in the release notes.
- **Truthfully labelled.** The release tier is stated on every release. A **Developer Preview**
  (DEV) build is signed with a development certificate, is not on Google Play or the App Store,
  and is not a Product, stable or GA release.
- **Generic.** An artifact carries no device-specific state: no node identity, owner wallet,
  membership intent, handoff session or device identifier.

## Verify a download

```
shasum -a 256 <file>        # macOS
sha256sum <file>            # Linux
```

The value must equal the SHA-256 in the release notes, in `releases/<tag>/SHA256SUMS` and in
`releases/<tag>/artifact-record.json`.

## Where to download

The Gao Developer Portal lists the current builds with their identity and install steps:
https://dev-sdk.gao.global/downloads/ (DEV). The Download buttons there link straight to the
release assets in this repository.
