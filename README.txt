PRODUCTION TRACKING BOARD — project files
==========================================

Folder layout:
  firebase.json          hosting config (serves the /public folder, no-cache on HTML)
  public/index.html      landing page (Manager / Board Tablet / TV Display)
  public/board.html      the board app (all logic + live Firestore sync)

The Firebase project config (apiKey, projectId, etc.) is already filled into
public/board.html, so it connects to the same shared board.

Manager passcode: 1234  (change MANAGER_PASSCODE near the top of the <script> in board.html)

--------------------------------------------------
DEPLOY (from this folder, in a terminal):
--------------------------------------------------
1) One-time setup on a new computer:
     npm install -g firebase-tools
     firebase login
     firebase use --add          (pick the "tracking-boards" project, alias: default)

2) Every deploy:
     firebase deploy --only hosting

   Live URL: https://tracking-boards.web.app

--------------------------------------------------
URLs:
--------------------------------------------------
  Landing ........... https://tracking-boards.web.app
  Manager Mode ...... https://tracking-boards.web.app/board.html          (passcode)
  Board Tablet ...... https://tracking-boards.web.app/board.html?tablet
  TV Display ........ https://tracking-boards.web.app/board.html?tv
  TV, fixed line .... https://tracking-boards.web.app/board.html?board=Line A&tv
  TV, auto-rotate ... add &rotate  (also toggleable from Manager Mode)
