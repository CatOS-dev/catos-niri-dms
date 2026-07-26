# catos-niri-dms

Complete CatOS Niri desktop Profile powered by Dank Material Shell.

The repository contains the installed Profile tree directly:

```text
usr/share/catdot/profiles/catos-niri-dms/profile.toml
usr/share/catos-niri-dms/...
```

Select the Profile with:

```sh
catdot select catos-niri-dms
```

Catdot installs the exact package names declared by the Profile and maps the
content below `/usr/share/catos-niri-dms` into the user's HOME. Switching a
Profile does not restart applications or the desktop session.

## Managed configuration

The Profile owns and refreshes these paths:

```text
.config/niri/config.kdl
.config/environment.d/80-catos-niri.conf
.gtkrc-2.0
.config/gtk-3.0/settings.ini
.config/gtk-4.0/settings.ini
.config/gtk-4.0/gtk.css
.icons/default/index.theme
```

Run the following command to explicitly accept a newer installed revision:

```sh
catdot update catos-niri-dms
```

## Seed configuration

All other files under `/usr/share/catos-niri-dms` are initial Profile seeds.
The managed main Niri config includes DMS fragments plus the profile-scoped
`~/.config/niri/custom/catos-niri-dms/` directory. Its `input.kdl`,
`outputs.kdl`, and `rules.kdl` files are seeded once and are never managed, so
later selections and updates preserve user changes. DMS-generated fragments and
Ghostty configuration remain seeds as well.

Niri starts Xwayland Satellite and DMS directly from `config.kdl`. Terminal and
launcher bindings invoke Ghostty and DMS directly; no Catdot runtime wrapper is
used.
