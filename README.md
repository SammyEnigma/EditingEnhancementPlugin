# EditingEnhancementPlugin
A Plugin for QtCreator which enhances the editing by some commands that are not possible otherwise

## Compilation
Setup the environment variables:
* QTC_SOURCE has to point to the QtCreator source
* QTC_BUILD has to point to the QtCreator build

## Installation
Copy the <ideversion>/libEditingEnhancement.so from the prebuild directory into the plugin directory. Depending on you system its on the following locations:
* Windows: "%LOCALAPPDATA%\QtProject\qtcreator\plugins\<ideversion>"
* Linux: "$XDG_DATA_HOME/data/QtProject/qtcreator/plugins/<ideversion>" or "~/.local/share/data/QtProject/qtcreator/plugins/<ideversion>"
* Mac: "~/Library/Application Support/QtProject/Qt Creator/plugins/<ideversion>"

Currently there are only prebuilds for linux

## New Commands
* Sort paragraph: CTRL+SHIFT+E,CTRL+SHIFT+S
  * This sorts all lines on the current paragraph. A paragraphs delimiter is an empty or only with whitespaces filled line. (There is a similar method within QtCreator already but that one only works if you select lines, this one does
without a selection

* Sort indented paragraph: CTRL+E,CTRL+S
  * This sorts all lines on the current paragraph, similar to the previous call but this time the paragraph ends when the indentation stops. This is helpfull if you want to order stuff like the "HEADER += \" entries in the .pro file.

* Advanced Alignment: CTRL+E,CTRL+R
  * This vertically aligns by a common found object. You select from the First char you want the lines align to to the last char it should align to and then press the combo.
  * The following two pictures show a simple example on how to verticaly align at the matching string '= '
  * First you select from the starting '= ' to the finishing one: <br/>
    ![Selection for alignment](https://github.com/CMon/EditingEnhancementPlugin/blob/master/doc/markingBeforeSpecialAlignment.png)
  * Then you hit the combo and the result will be this: <br/>
    ![After the alignment happened](https://github.com/CMon/EditingEnhancementPlugin/blob/master/doc/afterSpecialAlignment.png)
  * This works for all kinds of strings as long as all lines have this string in common

## new QuickFix
* When hitting ALT+Enter and if you are within an if statement you are now able to add or remove a '!' infront of the current statement

