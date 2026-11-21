# ITSD 85 Lab – Submission Requirements Checklist

A submission is complete only when **both GitHub and Google Classroom** are done before the deadline. Submission is worth **10%** of the final grade.

**Final grade = 0.50 × Lab work + 0.40 × Paper + 0.10 × Submission**

---

## Required deliverables

- [ ] GitHub repository link (add the instructor as a collaborator if the repo is private)
- [ ] Publication-ready paper (PDF) with CP1–6 screenshots, the 7.5 results table and the guide-question answers in the appendix
- [ ] Actions tab shows at least:
  - [ ] one green **test → deploy** run
  - [ ] one red **test** run from Test B
  - [ ] the **rollback** run from Test C
- [ ] Live demonstration (2 min): change the homepage text, merge, show it deployed without touching the server

---

## Step S1 – Finalize the GitHub repository

### 1. Repository name
- [ ] `itsd85-lab<no>-<section>-<surname>`
- Pairs use both surnames, e.g. `itsd85-lab3-bsit4a-cruz-santos`
- To rename: **Settings → General**

### 2. README.md at the root with these exact headings
```markdown
# ITSD 85 Lab <no>: Automated CI/CD Pipeline
Student(s): <full names>   Section: <section>   Instructor: <name>

## What this project does
## Pipeline diagram (image in docs/pipeline.png)
## How to run locally (npm commands)
## How the deployment works (test job → deploy job on self-hosted runner)
## Results (push-to-live times from Part 7.5)
## Screenshots (links to docs/screenshots/)
## Paper (link to docs/paper.pdf)
```

### 3. `docs/` folder
```
docs/
├── screenshots/
│   ├── cp1-versions.png
│   ├── cp2-...png
│   ├── ...
│   └── cp6-deploy-green.png
├── pipeline.png
└── paper.pdf
```
- [ ] `docs/screenshots/` (checkpoint images CP1–CP6)
- [ ] `docs/pipeline.png`
- [ ] `docs/paper.pdf`

### 4. No secrets committed
- [ ] No `.env`
- [ ] No runner token
- [ ] No private SSH key
- If one was committed: delete it, **rotate it** (generate a new one), and tell the instructor.

### 5. Actions history
- [ ] Required runs are still visible. **Do not delete workflow runs.**

### 6. Create the release (freezes the graded version)
```bash
git switch main && git pull
git tag -a v1.0 -m "ITSD 85 Lab final submission"
git push origin v1.0
```
- [ ] GitHub → **Releases → Draft a new release**
- [ ] Tag: `v1.0`
- [ ] Title: `Final submission`
- [ ] Attach `paper.pdf`
- [ ] Click **Publish release**

### 7. Private repo only
- [ ] **Settings → Collaborators → Add people** → instructor's GitHub username: ________

---

## Step S2 – Turn in on Google Classroom

1. [ ] Open **Google Classroom → ITSD 85 → Classwork → Lab <no>: Automated CI/CD Pipeline**
2. [ ] Under **Your work → + Add or create**, attach in this order:
   - [ ] **Link:** GitHub repository URL
   - [ ] **Link:** v1.0 release URL – `https://github.com/<user>/<repo>/releases/tag/v1.0`
   - [ ] **File:** `ITSD85_Lab<no>_<Section>_<Surname>_Paper.pdf`
   - [ ] **Link (optional):** screen recording of Tests A–C on Google Drive (access: *Anyone in your school with the link can view*)
3. [ ] **Private comment:** full name(s), latest commit ID on `main`, one sentence on anything not finished
4. [ ] Click **Turn in** and confirm. The status must read **Turned in**.
5. [ ] **Pairs:** both students turn in the same files

---

## Rules

| Rule | Detail |
|---|---|
| Deadline | ____________ 11:59 PM. Commits after the deadline are not graded; the **v1.0 tag date** is checked. |
| Late penalty | minus ___ points per day, up to ___ days |
| Resubmitting (before the deadline) | **Unsubmit** → replace files → push new tag `v1.1` → **Turn in** again |
| Academic honesty | Copied workflows, code or text without credit = **zero** and a report under the honesty policy |

---

## Submission rubric (100 points)

| Criteria | Full credit | Partial credit | No credit | Points |
|---|---|---|---|---|
| Repository completeness | Correct name; README with all headings; `docs/` with screenshots, diagram and paper | One or two items missing | README or `docs/` missing | 30 |
| Commit history and release | Regular, meaningful commits from every member; v1.0 tag and release with paper attached | Few large commits, or release missing | Single bulk upload, no tag | 25 |
| Google Classroom turn-in | All links + PDF, correct file name, private comment with commit ID, status Turned in | One item missing or misnamed | Not turned in | 25 |
| Security hygiene | No secrets, tokens or keys in repo | Secret committed but removed and rotated | Secret still exposed | 10 |
| Timeliness | On time | Late within allowed days (minus late penalty) | Beyond allowed days | 10 |
| **Total** | | | | **100** |

---

## Final pre-submit check

- [ ] Repo renamed correctly
- [ ] README has all 7 headings
- [ ] `docs/` complete (screenshots, pipeline.png, paper.pdf)
- [ ] Commit history shows regular, meaningful commits (not one bulk upload)
- [ ] No secrets in repo
- [ ] Required Actions runs visible
- [ ] `v1.0` tag pushed and release published with the paper attached
- [ ] Instructor added (if private)
- [ ] Classroom: repo link, release link, correctly named PDF attached
- [ ] Private comment with commit ID
- [ ] Status shows **Turned in** before 11:59 PM