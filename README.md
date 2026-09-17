# flyover-pill

An Omarchy bar widget: an ambient "aircraft nearby" count for the bar.
Left-click launches (or focuses) [flyover](https://github.com/linuxbren/flyover), a
real-time ADS-B radar scope for the terminal. Right-click toggles
flyover's screensaver on/off.

This widget is deliberately thin — it owns no scope-drawing or
screensaver-patching logic of its own. It just polls [adsb.lol](https://adsb.lol)
every ~20s for a count (using the same location flyover itself reads, from
`~/.local/state/omarchy/settings/weather.json`), launches the `flyover`
binary in a new terminal window on left-click, and on right-click runs
`omarchy branding screensaver text|reset` — repurposed by flyover's own
[screensaver packaging](https://github.com/linuxbren/flyover/tree/master/packaging/screensaver)
to enable/disable it, which needs a one-time setup there first.

## Install

```
omarchy plugin add https://github.com/linuxbren/flyover-pill.git --enable
```

Requires [flyover](https://github.com/linuxbren/flyover) itself to be built and
either on your `PATH` or cloned to `~/flyover` (the widget checks `PATH`
first, falling back to `~/flyover/target/release/flyover`).

## License

MIT — see [LICENSE](LICENSE).
