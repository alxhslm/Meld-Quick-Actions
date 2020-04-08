# Meld Finder Integration
A pair of Quick Actions to quickly compare selected files or directories from Finder on macOS (Mojave or later). This was designed to mimic the WinMerge's integration with Explorer on Windows.

## Installation

### To install
- Double click on the workflow file
- 'Quick Action Installer' will ask you if you want to install the workflow
- Select 'Install'
- The Quick Action is installed and should now be visible in Finder

### To uninstall
- Go to System Preferences > Extensions > Finder
- Right click on the Quick Action and select 'Move to Bin'

## Usage

Select the files or directories, and then select the required action from Right-Click > Quick Actions. They can also be selected on the Preview pane in Finder if enabled.

There are two Quick Actions which work together:

* _Select for Meld:_ Pre-selects the item as the first item to be compared. This is useful if you want to compare files from different directories. If an item has already been pre-selected, then this is replaced with the current item. 
* _Compare with Meld:_ Different behaviour depending on number of items selected.
    * One file/directory is selected: Compares the selected item with one pre-selected with _Select for Meld_.
    * Two files/directories are selected: Compares the two selected items. Any items pre-selected items are discarded.

A new instance of Meld.app is always opened, so you can perform multiple comparisons. 

## How it works
The path of a pre-selected item is stored in the text file `/tmp/meld_cmp`. 

The items to be compared are then passed to Meld.app using the CLI.

These Quick Actions could easily be modified to work with FileMerge.app or other diff tools.