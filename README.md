# طريقك أمان | Tareeqak Aman

Co-authors: **Yousef Tamime and Abdelrahman**.

An educational road-issue reporting app using Expo / React Native, Firebase and Leaflet / OpenStreetMap, with an optional image-upload service and a web admin panel.

## Source code

The complete source is in **1-tareeqak-aman-source.zip** in this repository. Download and extract it before following the setup notes. The repository is an archive distribution, not an unpacked source tree.

See **2-tareeqak-publish-NOTICE.md** for the preserved original attribution to Abdelrahman Khaled. Both co-authors are credited for their work together on this project.

## Setup

1. Extract the source ZIP and install its dependencies with `npm ci`. Review dependencies before running third-party code.
2. Create your own Firebase project and register a web app. Fill the placeholders in `src/config/firebase.js` and `admin-web/index.html`, then set your own project ID in `.firebaserc`.
3. Enable Firebase Authentication with Email/Password and create your own admin account. Put its UID in `firestore.rules` where indicated. Configure and review your rules before deploying to your own project.
4. Set your own demo PIN in `src/config/admin.js` and corresponding SHA-256 PIN hash in `admin-web/index.html`. The client-side PIN is not a security boundary. Firebase Auth and Firestore rules control admin writes.
5. Optional: configure your own Cloudinary cloud and restricted upload preset in `src/config/cloudinary.js`. No original image-service account is included.
6. Run locally with `npx expo start`. For cloud builds, create/link a **separate Expo/EAS project under your own account** and review the app identifiers and build configuration first.

## Security and status

No working backend credentials, admin account, PIN or Expo project credentials are included. Configuration values are placeholders. A static credential scan was performed before publication; the application and its dependencies have not been executed or tested as part of this upload.

The supplied Firestore rules allow public reads and report creation, while restricting updates and deletion to the configured admin UID. Review validation, privacy, abuse prevention and upload restrictions before any real deployment. Do not use production data or leave an open test database.

The original source README is preserved inside the ZIP for reference. This setup section takes precedence where that older README implies credentials are already configured, suggests open test mode, or assumes an existing backend. Deploy only to your own projects after replacing placeholders and reviewing rules.
