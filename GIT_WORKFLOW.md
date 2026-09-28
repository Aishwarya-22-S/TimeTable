# Smart Timetable Generator — Git & GitHub Team Workflow

**Team size:** 2 (Member A – Frontend, Member B – Backend)

## Step 1: Create the repository (Member A only)
1. Go to GitHub → **New repository** → name it `smart-timetable-generator` → Create.
2. Copy the repo URL, e.g. `https://github.com/memberA/smart-timetable-generator.git`.

## Step 2: Clone and make the first commit (Member A)
```
git clone https://github.com/memberA/smart-timetable-generator.git
cd smart-timetable-generator
```
Add `README.md` to this folder, then:
```
git add README.md
git commit -m "Initial commit with README"
git push origin main
```

## Step 3: Add Member B as a collaborator
1. On GitHub: **Settings → Collaborators → Add people** → enter Member B's GitHub username.
2. Member B accepts the invite (check email or GitHub notifications).
3. Member B clones the same repo:
```
git clone https://github.com/memberA/smart-timetable-generator.git
cd smart-timetable-generator
```

## Step 4: Member A pushes the frontend
```
git checkout -b frontend
```
Add `index.html` and `style.css` to the folder.
```
git add index.html style.css
git commit -m "Add frontend timetable form, grid UI, and styling"
git push origin frontend
```

## Step 5: Open and merge the frontend pull request
1. On GitHub, click **Compare & pull request** for the `frontend` branch.
2. Base: `main` ← Compare: `frontend`.
3. Title it (e.g. "Add frontend timetable form and grid UI") → **Create pull request**.
4. Click **Merge pull request** → **Confirm merge**.

## Step 6: Member B pulls the latest main, then pushes the backend
```
git checkout main
git pull origin main
git checkout -b backend
```
Add `timetable_backend.js` to the folder.
```
git add timetable_backend.js
git commit -m "Add backend logic for slot storage, conflict checking, and rendering"
git push origin backend
```

## Step 7: Open and merge the backend pull request
Same as Step 5, but base `main` ← compare `backend` → **Create pull request** → **Merge pull request**.

## Step 8: Both members sync the final project
```
git checkout main
git pull origin main
```
Both now have `index.html` + `style.css` + `timetable_backend.js` + `README.md` merged locally, and can open `index.html` in a browser to run the app.

---

## Suggested commit history

| Step | Branch | Commit message |
|------|--------|-----------------|
| 1 | main | Initial commit with README |
| 2 | frontend | Add frontend timetable form, grid UI, and styling |
| 3 | backend | Add backend logic for slot storage, conflict checking, and rendering |

## Optional next iteration (shows continued collaboration)

- Member A: `git checkout -b frontend-style` → improve table styling → PR → merge
- Member B: `git checkout -b backend-export` → add "export as PDF" or "clear timetable" feature → PR → merge
