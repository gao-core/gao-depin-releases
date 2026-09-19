# Distribution policy

1. **Scope.** This repository distributes built artifacts of Gao DePIN and their public
   metadata. Nothing else is committed here: no application source, no history of the
   canonical repository, no key material, no credentials, no logs.
2. **Source of truth.** The canonical source is `gao-core/gao-depin` (private). Every release
   here records `source_repository` and `source_sha` in `releases/<tag>/artifact-record.json`
   and in the release notes.
3. **Tag naming.** `depin-<platform>-<tier>-<sha8>` — e.g. `depin-android-dev-9d5aa12d`.
   `<tier>` is `dev` for a Developer Preview. No `product/`, `stable`, `ga` or store naming.
4. **Immutability.** Assets and tags are never modified or removed. A correction is a new tag.
5. **Publication gate.** Before an asset is attached: its SHA-256 and size must equal the
   accepted values of the acceptance record; the archive is listed and must carry no
   identity-, key-, owner-, wallet-, intent- or state-shaped entry; a secret-safety review
   (credential filetypes and patterns) must pass. The verdicts are written in the record.
6. **Round trip.** After publication the asset is downloaded back anonymously and must hash
   to the recorded SHA-256 before any download surface links to it.
