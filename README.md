# Hi, I'm Tobias 👋
 
**From first commit to running server: I build web apps and keep them running.**
 
Full-stack developer with 10 years of experience as a system administrator.
 
📍 Saxony-Anhalt, Germany · 💼 Open to junior full-stack roles, remote or hybrid · 🗣️ German (native), English (professional)
 
I build with **Angular and TypeScript** on the frontend and **Django / Django REST Framework** on the backend. Then I containerize what I build, ship it through CI/CD and run it on my own Linux server.
 
Since 2016 I've been a system administrator at a large social services organization: 7 sites, 600 employees, 1,000 students and more than 600 devices. Between mid-2024 and early 2026 I completed an 18-month web developer program at Developer Akademie. That combination is what I bring to a dev team: I know what happens after the merge. It's especially useful in small teams without a dedicated ops person.
 
---
 
## Featured: StackGraph
 
Turns a `docker-compose.yml` into an interactive graph of your stack: containers, networks, volumes, dependencies and exposed ports. Runs entirely in the browser, nothing gets uploaded.
 
**[Try it live](https://stackgraph.tobias-klanert.de)** · **[Source code](https://github.com/TobiasKlanert/stackgraph)**
 
- Angular with Signals for state and RxJS for the parse → layout pipeline
- ELK for automatic layout, custom SVG for rendering, interaction and export
- Strict TypeScript, Vitest, ESLint and Prettier, all enforced in CI
- Multi-stage Docker build (Node → nginx), running behind Caddy on my own VPS
## More projects
 
| Project | What it does | My part |
|---|---|---|
| **Videoflix**<br>[Code](https://github.com/TobiasKlanert/Videoflix-Backend) | Video streaming backend with HLS conversion via ffmpeg as background jobs. Four containers: Django with Gunicorn, RQ worker, PostgreSQL, Redis.<br><sub>Django · RQ · PostgreSQL · Redis · ffmpeg · Docker Compose</sub> | Course project. Frontend provided by Developer Akademie, backend and operations by me. |
| **Coderr**<br>[Code](https://github.com/TobiasKlanert/Coderr-Backend) | Marketplace backend connecting customers with business partners: REST API with roles, permissions and domain rules.<br><sub>Django · Django REST Framework</sub> | Course project. Frontend provided by Developer Akademie, backend and operations by me. |
| **Join**<br>[Live](https://join.tobias-klanert.de) · [Code](https://github.com/TobiasKlanert/Join) | Task management app with a drag-and-drop board.<br><sub>JavaScript · Firebase</sub> | Team project (3 people), design by Developer Akademie. I coordinated the team, built the Firebase integration, login and registration and the drag-and-drop board, and helped with bug fixes. |
| **Sharkie**<br>[Live](https://sharkie.tobias-klanert.de) · [Code](https://github.com/TobiasKlanert/Sharkie) | 2D browser game.<br><sub>Vanilla JavaScript · OOP</sub> | Course project. Graphics by Developer Akademie, sounds from Freesound.org. |
 
## How I ship
 
My new portfolio runs through the kind of pipeline I'd want in a team ([source](https://github.com/TobiasKlanert/portfolio)):
 
```text
pull request → CI: lint · format · tests · build → merge
             → Docker image on GHCR, tagged with the commit hash
             → deploy via SSH forced command: GitHub sends a tag, the server decides what runs
             → health check → automatic rollback if the new container isn't healthy
```
 
- **Staging and production:** `develop` deploys to a password-protected staging site, `main` to production
- **Least privilege:** the job that pushes images never sees a deploy key, and deploy keys can't open a shell
- **Supply chain:** GitHub Actions pinned to commit SHAs, updated by Dependabot with a 7-day cooldown
- **Hardened containers:** non-root, read-only filesystem, all capabilities dropped
- **Around it:** Caddy as reverse proxy, Uptime Kuma for monitoring with push alerts, self-hosted Umami for cookie-free analytics
## Tech stack
 
| Area | Tools | Where to see it |
|---|---|---|
| Frontend | ![Angular](https://img.shields.io/badge/Angular-0F0F11?style=flat-square&logo=angular&logoColor=white) ![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white) ![RxJS](https://img.shields.io/badge/RxJS-B7178C?style=flat-square&logo=reactivex&logoColor=white) ![SCSS](https://img.shields.io/badge/SCSS-CC6699?style=flat-square&logo=sass&logoColor=white) ![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black) ![HTML](https://img.shields.io/badge/HTML-E34F26?style=flat-square&logo=html5&logoColor=white) ![CSS](https://img.shields.io/badge/CSS-663399?style=flat-square&logo=css&logoColor=white) | StackGraph, Join, Sharkie |
| Backend | ![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white) ![Django](https://img.shields.io/badge/Django-092E20?style=flat-square&logo=django&logoColor=white) ![Django REST Framework](https://img.shields.io/badge/Django%20REST%20Framework-A30000?style=flat-square&logo=django&logoColor=white) ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white) ![Redis](https://img.shields.io/badge/Redis-FF4438?style=flat-square&logo=redis&logoColor=white) ![RQ](https://img.shields.io/badge/RQ-555555?style=flat-square) ![Firebase](https://img.shields.io/badge/Firebase-DD2C00?style=flat-square&logo=firebase&logoColor=white) | Videoflix, Coderr, Join |
| Infrastructure | ![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white) ![Docker Compose](https://img.shields.io/badge/Docker%20Compose-2496ED?style=flat-square&logo=docker&logoColor=white) ![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black) ![Caddy](https://img.shields.io/badge/Caddy-1F88C0?style=flat-square&logo=caddy&logoColor=white) ![nginx](https://img.shields.io/badge/nginx-009639?style=flat-square&logo=nginx&logoColor=white) ![Gunicorn](https://img.shields.io/badge/Gunicorn-499848?style=flat-square&logo=gunicorn&logoColor=white) | StackGraph, Videoflix, Portfolio |
| CI/CD and quality | ![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white) ![GHCR](https://img.shields.io/badge/GHCR-181717?style=flat-square&logo=github&logoColor=white) ![Vitest](https://img.shields.io/badge/Vitest-00FF74?style=flat-square&logo=vitest&logoColor=black) ![ESLint](https://img.shields.io/badge/ESLint-4B32C3?style=flat-square&logo=eslint&logoColor=white) ![Prettier](https://img.shields.io/badge/Prettier-F7B93E?style=flat-square&logo=prettier&logoColor=black) | StackGraph, Portfolio |
 
## Currently
 
- Building my new portfolio, launching at the end of 2026 at [tobias-klanert.de](https://tobias-klanert.de)
- Moving StackGraph's deployment to the same locked-down pattern as the portfolio
- Getting stronger at automated testing and clean API design
## Let's talk
 
Looking for a junior developer who builds features and also knows how to run them? I'd love to hear from you.
 
📧 [kontakt@tobias-klanert.de](mailto:kontakt@tobias-klanert.de) · 💼 [LinkedIn](https://www.linkedin.com/in/tobias-klanert-80563731a/) · 🌐 [tobias-klanert.de](https://tobias-klanert.de)
 
<sub>Fun fact: I get strangely excited about tidy folder structures, which is probably why my repos and my server both look the way they do.</sub>
