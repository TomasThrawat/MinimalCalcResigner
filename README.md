# MinimalCalcResigner

Resigns the Minimal Calc (MonoChrome) split APKs with a fresh signing key on every workflow run.

## Setup (one-time, you do this)

Put the 4 split APKs from the XAPK into an `apks/` folder in this repo, then commit + push:

```
mkdir apks
cp com.devstacktools.bigcalc.apk apks/
cp config.arm64_v8a.apk apks/
cp config.en.apk apks/
cp config.zh.apk apks/
git add apks
git commit -m "add split apks"
git push
```

## Run

Go to the Actions tab -> "Resign APK" -> Run workflow. Each run generates a brand new random signing key, so every run's output has a different signature. Download the signed APKs from the run's Artifacts section, then install with:

```
adb install-multiple signed/*.apk
```
