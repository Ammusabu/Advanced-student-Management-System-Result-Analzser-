# EduTrack Pro 🎓

A lightweight, single-file school management dashboard for tracking students, sections, and academic performance — no backend, no database, no build step. Just open the HTML file in a browser.

![Status](https://img.shields.io/badge/status-active-brightgreen) ![License](https://img.shields.io/badge/license-MIT-blue) ![No Backend](https://img.shields.io/badge/backend-none-lightgrey) ![Deployed on Netlify](https://img.shields.io/badge/deployed-Netlify-00C7B7)

🔗 **Live Demo:** [student-result-analysis.netlify.app](https://student-result-analysis.netlify.app/)

## Overview

EduTrack Pro is a client-side web app for managing student records and class sections and visualizing academic performance. It's built as a single self-contained `index.html` file, making it easy to run, share, or embed anywhere without installing dependencies or setting up a server.

## Features

- **Dashboard** — At-a-glance stats (total students, class average, pass percentage, total sections), a top-performers list, a section overview, and a performance trend chart.
- **Student Management**
  - Add students with an ID, name, section, and marks across 6 subjects (English, Hindi, Maths, Science, Chemistry, Biology)
  - Search and filter students by name, ID, or section
  - View detailed student profiles with per-subject grades in a modal
  - Delete students
- **Section Management**
  - Create sections with a name, class teacher, room number, and capacity
  - View section rosters and enrollment progress bars
  - Delete sections (cascades to remove enrolled students)
- **Analytics**
  - Highest/lowest scores, pass/fail counts
  - Subject-wise average score chart
  - Grade distribution pie chart
  - Section-wise performance comparison chart
  - Top 10 performers leaderboard
- **Import / Export**
  - Bulk import students from a CSV file
  - Download a sample CSV template
  - Export all students or a single section's students to CSV
- **Automatic grading** — Averages are converted to letter grades (A+ through F) using a standard percentage scale.

## Tech Stack

Everything runs in the browser — there is no server or database.

| Purpose | Library |
|---|---|
| Charts | [Chart.js](https://www.chartjs.org/) + [chartjs-plugin-datalabels](https://chartjs-plugin-datalabels.netlify.app/) |
| CSV parsing | [PapaParse](https://www.papaparse.com/) |
| Icons | [Font Awesome](https://fontawesome.com/) |
| Fonts | Google Fonts (Playfair Display, Raleway) |

All dependencies are loaded via CDN, so an internet connection is required for full styling/functionality.

## Getting Started

### Try it online

The app is deployed on Netlify — no setup needed: **[student-result-analysis.netlify.app](https://student-result-analysis.netlify.app/)**

### Run it locally

No installation or build process is required.

1. Download `index.html` (or clone this repo).
2. Open the file directly in any modern web browser (Chrome, Firefox, Edge, Safari).

```bash
git clone https://github.com/your-username/edutrack-pro.git
cd edutrack-pro
open index.html   # or double-click the file
```

That's it — the app starts with empty data, ready for you to add sections and students.

### Deploying your own copy

Since this is a static, single-file app, it can be deployed to any static host (Netlify, Vercel, GitHub Pages, etc.) with no build configuration:

- **Netlify**: drag-and-drop the project folder into the Netlify dashboard, or connect your GitHub repo for automatic deploys.
- **GitHub Pages**: enable Pages on the repo and set the source to the branch containing `index.html`.

## Usage

1. **Create a section first** (Sections → Add Section) — you'll need at least one section before adding students.
2. **Add students** (Students → Add Student), entering marks for each subject.
3. Check the **Dashboard** for a live summary, or **Analytics** for detailed charts and rankings.
4. Use **Import/Export** to bulk-load students from a CSV or export current data for reporting.

### CSV Import Format

```csv
id,name,section,english,hindi,maths,science,chemistry,biology
S001,Rahul Sharma,SEC001,85,78,92,88,90,86
S002,Priya Patel,SEC001,72,85,68,75,80,78
```

- `section` must match an existing Section ID (e.g. `SEC001`) — create the section first.
- Marks must be integers between 0 and 100.
- A sample template can be downloaded directly from the Import/Export tab.

## Grading Scale

| Average | Grade |
|---|---|
| 90–100 | A+ |
| 80–89 | A |
| 70–79 | B |
| 60–69 | C |
| 50–59 | D |
| 40–49 | E |
| Below 40 | F |

## Data Persistence

⚠️ **Data is stored in memory only** and resets on page reload. This project is currently intended for demos, prototyping, and single-session use. To persist data across sessions, you'd need to add browser storage (e.g. `localStorage`/`IndexedDB`) or connect it to a backend/database.

## Project Structure

```
edutrack-pro/
└── index.html   # Entire application: markup, styles, and logic
```

## Roadmap Ideas

- [ ] Persistent storage (localStorage, IndexedDB, or a backend API)
- [ ] Edit existing student/section records
- [ ] Multi-term/historical performance tracking (real trend data)
- [ ] Authentication and multi-user support
- [ ] Attendance tracking

## Contributing

Contributions are welcome! Feel free to open an issue or submit a pull request.

## License

This project is available under the [MIT License](LICENSE).
