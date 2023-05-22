# Fix Monitor magenta

Apple attempts to use YCbCr instead of RGB resulting in a bad color encoding.

To fix it, get the EDID information that the panel gives and override it removing all support for YCbCr.
Then, add the overridden EDID into the system overrides for display under `/Library/Displays/Contents/Resources/Overrides`.

## Long story short (using the backup)

Place this directory content in `/Library/Displays/Contents/Resources/Overrides`. Create the directory if don't exist.

## Tooling used

- BetterDisplay
- AW EDID Editor

## Procedure for new displays

0. Connect the mac to the display.
1. Open *BetterDisplay* and get EDID data and export it as `.bin`. (Prefer OS managed)
2. Open the exported EDID in *AW EDID Editor*.
3. Switch off all `YCbCr` support and save.
4. In *BetterDisplay*, check `Configuration Override`.
5. Unfold `EDID override` and import edited EDID.
6. Reconnect the display and check.
7. Save the config to this backup dir.

- Note that *BetterDisplay* will create the directory `/Library/Displays/Contents/Resources/Overrides` and place the config for us.

## Backup content

- README
- Gigabyte M28U EIDID override
