(Instructions adapted from gmail-plasmoid:
http://code.google.com/p/gmail-plasmoid/)
KDE Ki18n translator's guide: https://api.kde.org/frameworks/ki18n/html/trn_guide.html

This document contains brief instructions on how to create new
translations for this plasmoid. If any of the instructions are unclear
or you encounter any difficulties please contact the author.


[Step 4](#step-4-install-the-mo-file) covers how to install existing translations.


---------------------------------------------
Step 1: Creating a new <locale>.po file
---------------------------------------------
Under the `po` folder, make a folder for the locale, e.g.: `fr/`

Make a copy of
  `plasma_applet_org.kde.userbase.plasma.luna3.pot`

Move/rename it to the folder you created, e.g.:
  `fr/plasma_applet_org.kde.userbase.plasma.luna3.po`

Bash:
```bash
  mkdir -p fr
  cp plasma_applet_org.kde.userbase.plasma.luna3.pot fr/plasma_applet_org.kde.userbase.plasma.luna3.po
  ```

You are now ready to start translating.

--------------------------------------
Step 2: Translate the required strings
--------------------------------------
While you can edit the .po file in any text editor, using the
"lokalize" program can make your life easier. This program is packaged
for most distributions so it should be easy to install. Whatever method
you choose, you need to supply a translation for all of the strings that
appear in the .po file.

If you encounter any strings that you cannot translate due to the choice
of words or some other issue, please contact the author to work out a
solution.

-------------------------------------------
Step 3: Convert the .po file to an .mo file
-------------------------------------------
The plasmoid needs the translation in a .mo file.

Go to contents/po and run `./Messages.sh` - this generates the .mo files for
all the .po files.

The .mo files are placed in the `locale` directory under `contents`,

e.g. `locale/fr/LC_MESSAGES/plasma_applet_org.kde.userbase.plasma.luna3.mo`

----------------------------
Step 4: Install the .mo file
----------------------------
First locate where the plasmoid has been installed.

if it was installed using Add Widgets menu, it will probably be:
  `~/.local/share/plasma/plasmoids/org.kde.userbase.plasma.luna3/`
Copy the `contents/locale` directory into `~/.local/share`.

If you did a global install of the plasmoid, it's probably under:
  `/usr/share/plasma/plasmoids/org.kde.userbase.plasma.luna3/`
In this case, there will be a `/usr/share/locale` directory already;
copy the `contents/locale` directory into `/usr/share`.

Logout and back in - it should pick up the translations.

----------------------------------------------------------
Step 5: Send the translation for inclusion with the widget
----------------------------------------------------------
Once you are happy with the translation please send the .po file to the
author along with translations for the following two strings (see
`metadata.json`):

For the "add widgets" screen:
   "Luna 3"
   "Display moon phases for your location"

Please send the translations for these two strings only when the
translation is not yet in `metadata.json`.

Alternatively, fork on Github (samuel-jimenez/Luna3), do your changes there, and
then send a pull request.