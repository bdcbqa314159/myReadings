# myReadings

My reading catalog, powered by
[bookward](https://github.com/bdcbqa314159/bookward). Published here: the
generated **[Markdown catalog](reports/reading-catalog.md)** and its **PDF**.
The database itself (`reading.db`) stays local, and the binaries ship in with
`~/work/bookward/scripts/dist.sh ~/work/myReadings/bin`.

Each entry gets a generated id (`bk-0001`, ...) which names the book's PDF on
the archive drive — the database is the index connecting titles to files.

```sh
./bw                                  # TUI (Books / Table / Stats)
./bw add "Dune" --author "Frank Herbert" --edition "Penguin" --year 2023
./bw add "Stochastic Calculus for Finance II" --author "Shreve" --worked yes
./bw find shreve                      # title/author search -> id -> PDF
./bw list --year 2026
./bw again bk-0001 --year 2026        # re-read: same id, both years count
./bw edit bk-0001 --title "Sueños"     # fix typos/accents in place
./bw worked bk-0002 yes
./bw year bk-0001 2021                # move a reading to another year
./bw remove bk-0003 [--year 2021]     # forget one reading, or the whole book
./bw report                           # full LaTeX catalog into reports/
./bw report 2026                      # one year only
```

Convention: books read before the list began (2022) are logged with
`--year 2021`.
