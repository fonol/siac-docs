# Settings

Due to historic reasons, there are currently multiple places where settings of
the add-on can be configured. It is planned to eventually move all of the most important
options to the add-on settings which can be accessed [from the menubar](#from-menubar).

----------------------------

## From menubar

To open the add-on settings, click on `SIAC>Add-On Settings` in the Anki menubar.
The settings will only be saved if you confirm the Dialog with `OK`.

!> Some of the settings may require a restart of Anki! If you want to make sure, restart
Anki after making any major changes.

### Appearance

### Shortcuts
In this tab, most of the user-configurable shortcuts can be set. To do so, use
the keygrabber functionality by pressing the `Edit`-Button of the shortcut you want to change.
You may now press an individual combination of keys.

!> The keygrabber is not able to identify all sensible shortcuts yet. If in doubt, use the `Manual` configuration.
Make sure to only enter valid key combinations there, as this input is not sanity-checked.

To remove a keyboard shortcut completely, click on `Manual` and remove the Shortcut from the text input.
Confirm with `OK`.

Please notice that it is not easily possible to identify clashes with shortcuts of other Anki add-ons or
Anki itself. If a keyboard shortcut is not working as expected, please try setting it to a different one first!

!> Changed shortcuts will only be enabled after a restart of Anki.


### Interleaving

----------------

## From Add Card-dialog

-----------------

## Manual configuration

All of the settings can be manually specified and manipulated in the `.json` file of the add-on.
