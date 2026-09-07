# MinimalCalcResigner

Resigns the Minimal Calc (MonoChrome) split APKs with a fresh signing key on every workflow run.

The split APKs are already committed under `apks/`. The base APK is split into
`apks/com.devstacktools.bigcalc.apk.part00`..`part05` (GitHub blob upload size limit) --
the workflow reassembles them automatically before signing.

## Run

Actions tab -> "Resign APK" -> Run workflow. Each run generates a brand new random
signing key, so every run's output has a different signature. Download the signed
APKs from the run's Artifacts section, then install with:

```
adb install-multiple signed/*.apk
```
