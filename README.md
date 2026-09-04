# myReadings

My reading log, powered by
[bookward](https://github.com/bdcbqa314159/bookward). Published here: the
yearly **LaTeX reports** (`reports/*.tex`). The database itself (`reading.db`)
and the PDFs stay local, and the binaries ship in with
`~/work/bookward/scripts/dist.sh ~/work/myReadings/bin`.

```sh
./bw                                  # TUI (Books / Table / Stats)
./bw add dune "Dune" --author "Frank Herbert" --pages 412
./bw progress dune 120
./bw finish dune --rating 5
./bw report 2026                      # LaTeX/PDF into reports/
```
