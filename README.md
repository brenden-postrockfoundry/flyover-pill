# flyover-pill

An Omarchy bar widget: an ambient "aircraft nearby" count for the bar,
click to launch (or focus) [flyover](https://github.com/<you>/flyover), a
real-time ADS-B radar scope for the terminal.

This widget is deliberately thin — it owns no scope-drawing logic of its
own. It just polls [adsb.lol](https://adsb.lol) every ~20s for a count
(using the same location flyover itself reads, from
`~/.local/state/omarchy/settings/weather.json`) and launches the `flyover`
binary in a new terminal window on click.

## Install

```
omarchy plugin add https://github.com/<you>/flyover-pill.git --enable
```

Requires [flyover](https://github.com/<you>/flyover) itself to be built and
either on your `PATH` or cloned to `~/flyover` (the widget checks `PATH`
first, falling back to `~/flyover/target/release/flyover`).

## License

MIT — see [LICENSE](LICENSE).
