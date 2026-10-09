# Egyptian Plate Detector V2 — Android prototype

**This is a buildable Android source project, NOT a prebuilt APK.** It uses Android SpeechRecognizer, not Google Cloud Streaming. The recognition service may require internet and may differ by device. The demo list is hardcoded; do not use it for enforcement or treat a nonmatch as clearance.

## Build using GitHub Actions from a phone
1. Create a new empty GitHub repository (main branch).
2. Upload the CONTENTS of this folder to repository root, including `.github/workflows/android.yml` (hidden folders may require browser desktop mode or git upload).
3. Actions > Build Android APK > Run workflow (or push to main).
4. Open completed run > Artifacts > download `EgyptianPlateDetectorV2-debug-apk` ZIP > extract `app-debug.apk` and install it. Debug APK is signed with an ephemeral debug key; upgrading between builds may require uninstalling the previous build.
5. Grant microphone access and test in Arabic Egyptian. The app listens only while open; it may restart recognition between phrases, with gaps.

## Next milestone (NOT IMPLEMENTED)
Replace SpeechRecognizer with AudioRecord -> authenticated WebSocket gateway -> Google Cloud streaming Speech-to-Text, add account auth, rate limiting, proper segmentation and robust Egyptian number parser; encrypted authorized plate dataset with exact-match auditing. Never put cloud credentials in APK.

## Known limitations
- This is a proof of concept, not the high-accuracy cloud engine.
- Numeric parser supports basic words and simple compounds, not all colloquial variants.
- No real database import, no background recording, no 100% accuracy promise.
- Testing is needed across Android versions, devices and speech services.
