+++
title = "Increase swap on Raspberry Pi"
date = 2020-01-02
toc = true  # Show table of contents? true/false
type = "docs"  # Do not modify.
weight = 61

[menu.docs]
  parent = "tips"
  weight = 61


+++
Edit `/etc/dphys-swapfile` with your favorite text editor and set `CONF_SWAPSIZE` parameters like above:
```
CONF_SWAPSIZE=2048
```
Apply the configuration with:
```bash
service dphys-swapfile restart
```
