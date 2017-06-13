Peak Users Script is a simple script to monitor the peak user count of one or more channels on a per-channel basis, announcing new peaks in the channel and reporting on the current peak on demand.

Last updated on 3.04.14 for v1.2.


Installation
============

To load the script into KVIrc (which then persists until you uninstall) and run its startup alias, first disable 'User friendly command-line mode' (it prevents the parse command from working):

In a KVIrc console window, look at the bottom right - on the far right of the text entry widget, you'll see an arrow button. Press to expand, then press the 3rd button from the left - normal KVS command mode is now active, and the parse command below works:

    /parse <path to script file, speechmark-delimited if the path contains spaces>
    /PeakUsersScript::Startup

Once the script is installed, PeakUsersScript::Startup is automatically called when KVIrc is started.

You can turn back on 'User friendly command-line mode' if you want, its a per-window setting.


Dependencies
============

This script depends on the Common Scripting Services script, see the [Github repo](https://github.com/OmegaPhil/kvirc-common-scripting-services).


Uninstallation
==============

In a KVIrc console window:

    /PeakUsersScript::uninstall::uninstall


General Configuration
=====================

The 'Scripts' menu is created on the main KVIrc menubar, which then hosts the Peak Users Script menu. This allows you to turn the script on/off and list all monitored channels on all networks:

![Script menu](https://f92fac806bf10a96c0b8-8a0a46e5f1a5cc9854958bc3503f0f88.ssl.cf1.rackcdn.com/media_entries/7478/script-menu.png)

You can enable/disable the script on channels you are currently in by right-clicking the channel window (please get permission from the channel OPs before enabling this script due to the spam potential):

![Channel menu](https://f92fac806bf10a96c0b8-8a0a46e5f1a5cc9854958bc3503f0f88.ssl.cf1.rackcdn.com/media_entries/7479/channel-menu.png)

The option turns into 'Unmonitor <channel\>' when it is currently monitored.


Channel Trigger And Event
=========================

On monitored channels, any user can use the '!peak' trigger to show the current peak information:

![Channel trigger](https://f92fac806bf10a96c0b8-8a0a46e5f1a5cc9854958bc3503f0f88.ssl.cf1.rackcdn.com/media_entries/7480/channel-peak-trigger.png)

You can also trigger the trigger by submitting '!peak' to the channel yourself (as seen in the above screenshot).

The following happens when a new joining user breaks the peak:

![New peak event](https://f92fac806bf10a96c0b8-8a0a46e5f1a5cc9854958bc3503f0f88.ssl.cf1.rackcdn.com/media_entries/7501/new-peak-event.png)


Commands
========

The following commands are available:

    /PeakUsersScript <command>

    <no command>
        Returns the on/off state of the script

    help, h
        Returns this usage information
        
    on
        Turns script on
        
    off
        Turns script off

    monitor <network> <channel>
        Enable this script for the desired channel

    !peak <network> <channel>
        Spams peak information to the relevant channel

    reset <network> <channel>
        Clears the channel's peak record data

    reload
        Reloads peak record data from file

    unmonitor <network> <channel>
        Disable this script for the desired channel


Alias/Scripting Usage
=====================

The script is fully commented so should be fairly accessible for those wanting to see how to take its use further - for alias usage, see comments preceeding the alias, or run the alias without parameters for help/errors.


Development
===========

Try out my modification of the [geany](http://www.geany.org/) IDE, extending it to syntax highlight, parse KVIrc Script for aliases, events, variables, shortcut for loading scripts into KVIrc etc: [Github documentation](https://github.com/OmegaPhil/geany-kvircscript/wiki/README---KVIrc-Script-Integration).


Bugs And Feature Requests
=========================

Please create an issue on the [Github issue tracker](https://github.com/OmegaPhil/kvirc-peak-users-script/issues).


Contact Details
===============

OmegaPhil+KVIrc.Script@gmail.com
