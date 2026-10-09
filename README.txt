QUALI EXAM BANK - build & update guide

FIRST TIME (one repository, no coding)
 1. Make a free GitHub account and a new repository (public is needed for the in-app update check).
 2. Upload everything in this folder, including keystore.jks and the .github folder.
    If .github won't upload, use Add file > Create new file, name it .github/workflows/build-apk.yml and paste in the file contents.
 3. Actions tab > "Build APK" runs by itself (or click Run workflow). About 5-8 minutes.
 4. Open the Releases page (right side of the repository) > download QualiExamBank.apk > install on your phone.

UPDATING LATER
 Upload the new www folder (and any changed files). The workflow rebuilds and publishes a new release.
 In the app: Settings > Check for updates. Every build uses the same signing key (keystore.jks),
 so updates install over the old app and keep your progress.

IMPORTANT
 - Back up before switching from an older build: an app signed with a different key cannot be installed over it,
   so the old app must be removed first (that deletes its saved progress).
 - Keep keystore.jks. If you lose it, future updates cannot install over this app.
 - The keystore password is in the workflow file, so anyone who can see the repository could sign APKs as you.
   Fine for a personal study app. A private repository avoids that, but the in-app update check then won't work.
 - Fallback: each run also uploads QualiExamBank-debug-fallback (a debug build) under Actions > the run > Artifacts.
