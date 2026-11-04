MOVIE HUB — GITHUB PAGES + FIREBASE SETUP
===========================================

ADMIN UID
---------
EnFXzVouXFdMBtTh4YbAktrm0Tu1

WHAT HAS BEEN UPDATED
---------------------
- index.html: ADMIN_UID is set to the UID above.
- firestore.rules: admin authorization uses the UID above.
- storage.rules: admin authorization uses the UID above.

IMPORTANT: GITHUB UPLOAD ALONE IS NOT ENOUGH
--------------------------------------------
This ZIP is ready to upload to the ROOT of a new GitHub repository for the
website files. However, Firebase credentials were not included in the ZIP you
provided, so the live login, movie database, and video storage will not work
until you add your own Firebase Web App configuration.

ONE-TIME FIREBASE SETUP
-----------------------
1. Open https://console.firebase.google.com/ and create/select your Firebase project.
2. Add a Web App in Project settings and copy its Firebase config.
3. In index.html, replace the placeholder values in firebaseConfig:
   - PASTE_API_KEY
   - PASTE_PROJECT_ID
   - PASTE_MESSAGING_SENDER_ID
   - PASTE_APP_ID
   Use the exact values from your Firebase Web App configuration.
4. Firebase Authentication -> Sign-in method -> enable Email/Password.
5. Authentication -> Users: create the admin user whose UID is:
   EnFXzVouXFdMBtTh4YbAktrm0Tu1
   The UID must match exactly. If the existing user has a different UID, this
   package's admin UID must be changed to that user's actual UID instead.
6. Firestore Database -> Create database. Open Rules, paste the contents of
   firestore.rules, and click Publish.
7. Firebase Storage -> Get started. Open Rules, paste storage.rules, and
   click Publish.
8. Authentication -> Settings -> Authorized domains: add your GitHub Pages
   domain (for example: YOURNAME.github.io).

GITHUB PAGES DEPLOYMENT
-----------------------
1. Create a new GitHub repository.
2. Extract this ZIP on your device/computer.
3. Upload index.html, firestore.rules, storage.rules, and README.txt directly
   into the repository ROOT (not inside another nested folder).
4. Commit the files to the main branch.
5. Repository Settings -> Pages -> Build and deployment:
   choose "Deploy from a branch", branch "main", folder "/ (root)", then Save.
6. Wait for GitHub Pages to publish, then open the Pages URL.

HOW TO USE
----------
- Open the published website and choose Admin Login.
- Sign in using the Firebase Email/Password account associated with the exact
  admin UID above.
- Admins can add movies and delete entries.
- Add a poster URL and at least one direct video URL, or upload a video file.
- Uploaded video files are stored in Firebase Storage and saved as 1080p.

SECURITY / CONTENT NOTES
------------------------
- GitHub Pages only hosts the frontend. It does not automatically publish
  Firestore or Storage rules. Those rules must be pasted into Firebase Console
  and published as described above.
- Only add videos you own or are licensed/authorized to distribute.
- Firestore reads and video reads are public in the included rules. Admin-only
  restrictions apply to writes.
- Storage uploads are limited to 200 MB and video content types.
- External hosts may block embedding or direct downloads.
