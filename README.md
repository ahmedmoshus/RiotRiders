# Riot Riders — Android build

A small Android shell (full-screen landscape WebView) around the game page in
`app/src/main/assets/index.html`. GitHub builds the APK; nothing needs installing on your PC.

## Get the APK

1. Create a new repository on GitHub (private is fine) and upload **everything in this folder**,
   keeping the folders as they are — including the hidden `.github` folder.
   With git: `git init -b main && git add . && git commit -m "Riot Riders" && git remote add origin <repo-url> && git push -u origin main`
2. Open the repository's **Actions** tab. The "Build APK" run starts on its own (about 3–5 minutes).
3. When it turns green, open **Releases** on the repository home page and download `RiotRiders.apk`.
4. Copy it to the phone, open it, and allow "install unknown apps" when Android asks.

## Update the game

Replace `app/src/main/assets/index.html` with the new version and push; a new release is built.
Every build is signed with the same key (`app/sideload.keystore`), so it installs over the old one
and keeps the saved progress.

## Notes

- Works on Android 7.0 and newer. Progress is saved on the device.
- The key in this repository is for sideloading only. Publishing on Google Play needs your own
  private key that is **not** kept in a repository.
- PC version: open `app/src/main/assets/index.html` in any browser — it is the whole game in one file.
