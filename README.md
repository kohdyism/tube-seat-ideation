# Tube Seat Ideation Map

A rotatable 3D map of a deep-level London Underground train, platform, escalator and ticket hall, built for ideating on one problem: commuters find it awkward to **offer** a seat, or to **ask** for one when their need is invisible.

Click any part of the train or station (seats, poles, handles, doors, displays, the platform edge, gates and more) to see a design question for it, add ideas, tag them, link them to other parts and vote on the best ones.

**Live site:** https://kohdyism.github.io/tube-seat-ideation/

## How it works

- `index.html` is the whole app: three.js for the model, plain JavaScript for the ideation panel.
- Ideas and votes are shared through **Firebase Firestore**. Each visitor is signed in anonymously, which gives them a private id so they get one vote per idea and can only edit or delete their own ideas.
- Without a Firebase config the page still works, saving ideas and votes in each visitor's own browser.

## Setup

1. Create a Firebase project, add a **Web app**, and paste its `firebaseConfig` object into the `<script id="firebase-config">` block in `index.html`. The web config is not a secret; access is controlled by the rules.
2. In **Authentication > Sign-in method**, enable **Anonymous**.
3. Create a **Firestore Database** (production mode) and publish the rules in `firestore.rules`.
4. In **Authentication > Settings > Authorized domains**, add `<your-username>.github.io`.
5. In the GitHub repo, **Settings > Pages**, deploy from the `main` branch, root folder.

## Controls

Drag to move, right-drag or Shift-drag to rotate, scroll or pinch to zoom, arrow keys or WASD to walk, Q/E to turn. The camera buttons jump to an overview, inside the car, the platform, and the escalator and gates.

## Moderation

Visitors can only change their own ideas. To remove anything else, delete the document in the Firebase console under `ideas`.
