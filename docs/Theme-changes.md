This page lists various breaking and non-breaking theme changes that providers of custom themes will want to incorporate.

### 2025.12.0
The way the options screens work has been reworked.

All elements that start with any of these names should be entirely removed:
* `OptionsGame`
* `OptionsGraphics`
* `OptionsSound`
* `OptionsInput`
* `OptionsLyrics`
* `OptionsThemes`
* `OptionsRecord`
* `OptionsAdvanced`
* `OptionsNetwork`
* `OptionsWebcam`
* `OptionsJukebox`

Copy (and if desired: modify) all elements that start with these names from `Deluxe.ini` or `Modern.ini`:
* `OptionsSub`
* `OptionsNetworkLegend`
