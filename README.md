# myReadings

My reading catalog, powered by
[bookward](https://github.com/bdcbqa314159/bookward). Published here: the
rendered **[catalog site](https://bdcbqa314159.github.io/myReadings/)**, its
**[Markdown twin](reports/reading-catalog.md)**, and a **PDF**. The database
itself (`reading.db`) stays local, and the binaries ship in with
`~/work/bookward/scripts/dist.sh ~/work/myReadings/bin`.

Each entry gets a generated id (`bk-0001`, ...) which names the book's PDF on
the archive drive — the database is the index connecting titles to files.

```sh
./bw                                  # TUI (Books / Table / Stats)
./bw gui                              # desktop GUI
./bw add "Dune" --author "Frank Herbert" --edition "Penguin" --year 2023
./bw add "Stochastic Calculus for Finance II" --author "Shreve" --worked yes
./bw find shreve                      # title/author search -> id -> PDF
./bw list --year 2026
./bw again bk-0001 --year 2026        # re-read: same id, both years count
./bw edit bk-0001 --title "Sueños"     # fix typos/accents in place
./bw worked bk-0002 yes
./bw year bk-0001 2021                # move a reading to another year
./bw remove bk-0003 [--year 2021]     # forget one reading, or the whole book
./bw report                           # regenerate reports/ only
./bw publish ["commit message"]       # report + site, commit, push
```

Convention: books read before the list began (2022) are logged with
`--year 2021`.

## Publishing

`reading.db` is gitignored, so an edit is invisible to git until the catalog
is regenerated — `./bw publish` is the one command that closes that gap. It
runs the LaTeX/Markdown report, rebuilds `docs/index.html`, commits both, and
pushes. GitHub Pages serves `docs/` on the next build, no CI involved.

Only what the Markdown catalog already contains reaches the web: title,
author, edition, id, year, and the worked flag. The log stays on the machine.

`scripts/build_page.py` is the site generator (Python stdlib only, reads the
database directly). `python3 scripts/build_page.py --selftest` checks its
grouping, ordering, and escaping without touching the real log.
