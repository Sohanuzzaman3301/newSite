# Alex — Cybersecurity Portfolio (Jekyll CMS · Combo A)

Combo A: IBM Plex Sans / Source Sans 3 / IBM Plex Mono · SST palette #ffffff + Ink #303055 + Lavender #e8e8f2

## Run
```bash
bundle install
bundle exec jekyll serve --livereload
# → http://localhost:4000
```

## CMS
Decap CMS at `/admin/` — git-gateway backend. Edit Projects, Writeups, Experience, Certs without touching YAML.

## Demo data
- 6 projects (`_projects/`) — Home AD Lab, THM SOC1, HTB, OSINT Collector, CVE repro, picoCTF
- 5 writeups (`_writeups/`) — HTB Perfection SSTI→RCE, Phishing triage, OSINT 12 sites, Mimikatz detection, PNG forensics
- 3 experience (`_experience/`) — Home Lab, THM, CTF team
- 4 certs (`_certs/`) — Security+ (in prog), eJPT, THM SOC1, Google
- Skills + profile in `_data/`

## Edit
- Text/layout: `index.md` + `_includes/` + `_layouts/default.html`
- Style: `assets/css/style.css` (ported from `generated/style.css`)
- Content: `_projects/*.md`, `_writeups/*.md`, `_data/*.yml`

## Design notes
Combo A keeps code-block hero, 3-col cards, timeline, pill skills, cert cards — all responsive (900px → 2col, 600px → 1col).
