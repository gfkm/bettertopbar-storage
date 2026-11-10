# bettertopbar-storage

Settings storage page for **BetterTopBar**, a top-bar mod for Deadlock. The mod loads
https://gfkm.github.io/bettertopbar-storage/ in a hidden in-game browser panel and keeps one `localStorage` record
(`bettertopbar.settings.v1`): the settings the player changed in BetterTopBar's section, so they survive a game
restart. The page sends nothing anywhere and stores nothing else.

Protocol: request `#btb1.<id>.<op>[.<base64url payload>]` (`get` | `set` | `del`), answer in the page title,
`BTB1:` + JSON `{id, ok, op, value?, err?}`.

The same page as OPT's `opt-storage` and BetterMap's `bettermap-storage` (one origin, gfkm.github.io, so each keeps
its own key). Source of truth: the BetterTopBar repository, `web/bettertopbar-storage/`. Edit there and redeploy; do
not edit the published copy.
