# myReadings

My reading catalog, powered by
[bookward](https://github.com/bdcbqa314159/bookward). Published here: the
**LaTeX catalog** (`reports/*.tex`). The database itself (`reading.db`) and the
PDFs stay local, and the binaries ship in with
`~/work/bookward/scripts/dist.sh ~/work/myReadings/bin`.

Each entry gets a generated id (`bk-0001`, ...) which names the book's PDF on
the archive drive — the database is the index connecting titles to files.

```sh
./bw                                  # TUI (Books / Table / Stats)
./bw add "Dune" --author "Frank Herbert" --edition "Penguin" --year 2023
./bw add "Stochastic Calculus for Finance II" --author "Shreve" --worked yes
./bw find shreve                      # title/author search -> id -> PDF
./bw list --year 2026
./bw worked bk-0002 yes
./bw year bk-0001 2021                # correct a year after the fact
./bw remove bk-0003
./bw report                           # full LaTeX catalog into reports/
./bw report 2026                      # one year only
```

Convention: books read before the list began (2022) are logged with
`--year 2021`.
