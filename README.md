# README

This is a dictionary lookup script for [Plover](https://github.com/openstenoproject/plover) made for OS X. You can use it to discover which strokes can be used to produce a word (or phrase).

Derived from [this Automator workflow](http://stenoknight.com/plover/aviary/phpBB3/viewtopic.php?f=14&t=4386&p=6524&hilit=dictionary+lookup#p6524).


# Features

* Bash dictionary lookup script to find all the briefs for a word you would like to learn how to type.
* AppleScript UI for presenting dictionary lookup results:
  * Shows the shortest brief first.
  * Presents a text area to practice typing in.


# Installation

1.  Download the 2 files included:

    `git clone https://github.com/dimonster/plover-dictionary-lookup.git ~/plover-dictionary-lookup`


2.  Update the path to your Plover dictionaries folder in `dictlook`, for example:

    `grep -ia "$str" $HOME/Library/Application\ Support/plover/*.json | awk -F '": ' '{ print length($1), $0 }' | sort -n | grep -o '".*$'`


3.  Update the path to `dictlook` in `dictlook-ui.scpt`, for example:

    `do shell script "$HOME/plover-dictionary-lookup/dictlook -x " & "\"" & input & "\""`



# Usage

There are a few options for using the dictionary lookup script:

- Run the script on the command line:

    `cd ~/plover-dictionary-lookup`

    `./dictlook the-word-you-want-to-lookup`

- Add the AppleScript to [an Automator workflow](http://stenoknight.com/plover/aviary/phpBB3/viewtopic.php?f=14&t=4386&p=6524&hilit=dictionary+lookup#p6524), then select the word you want to look up and use the context-menu service by right-clicking on the word or using a keyboard shortcut you've mapped to the service.

- Use [the Alfred workflow](https://github.com/dimonster/alfred-plover-dictionary-lookup).
