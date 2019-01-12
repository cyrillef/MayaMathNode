# Maya Math Node

[![Maya](https://img.shields.io/badge/Maya-2008+.svg)](https://www.autodesk.com/developmaya)
![Platforms](https://img.shields.io/badge/platform-windows%20%7C%20osx%20%7C%20linux-lightgray.svg)
[![License](http://img.shields.io/:license-mit-blue.svg)](http://opensource.org/licenses/MIT)

## Description

This plug-in can be used in place of the Maya 'Expression' system.
Maya's evaluation of 'Expressions' depends on the contents of the
expression – sometimes you have to force evaluation - whereas, for
a node, the Maya DG will always do it for you when needed. Debugging
a Maya 'Expression' is not easy either (no tools are available), and
requires a knowledge of MEL. Using the MathNode plug-in, you can use
a Python debugger to debug the Node evaluation [see the following
Blog post for details](http://around-the-corner.typepad.com/adn/2012/07/python-debugging-in-maya.html).
In any case, it is always preferable to use self-contained nodes and
connections over expressions whenever possible.

## System Requirements

This plug-in has been tested with Autodesk Maya 2012-18.

This plug-in is a Python based plug-in, so it does not require any
compilation and works on Window 32bit/64bit, Mac OS, and Linux.

## Installation

### Manual Installation

The following steps are for using the plug-in with Autodesk Maya
2012-18. If you are using Maya 2018, please consider the
release number as "2018" in the paths listed below.

  1. If you are using Windows 7 (or Vista), first check if the
     zip file needs to be unblocked. Right-click on the zip file
     and select "Properties". If you see an "Unblock" button, then
     click it.

  2. Extract the plug-in module to any location you'd like. But keep
     the directory structure as is.

  3. Copy the mathNode.mod into the following folder
     ```
     Windows 7
     C:\users\&lt;your login&gt;\Documents\maya\2018[-x64]\modules

     MacOS
     /Users/Shared/Autodesk/maya/2018/modules

     Linux
     /home/&lt;your login&gt;/maya/2018/modules
     ```

  4. Edit the new mathNode.mod file in a text editor and modify the
     path &lt;mypath&gt;, to reflect the location where you copied the files.

  5. Once installed, the "mathNode" plug-in will be available
     in your Maya plug-in manager. Open the plug-in manager, load
     the plug-in, and select the 'Auto load' option. The plug-in manager
     can be found in:
     ```
      ->Window->Settings/Preferences/Plug-in manager
     ```

### Install from the AppStore

Go and Download the plugin installer from the
[AppStore](https://apps.autodesk.com/MAYA/en/Detail/Index?id=212304226072872821&appLang=en&os=Win64)

## Usage

Inside Maya, create a new node by using the MEL command 'createNode'.
I.e.  createNode asdkMathNode;

Then you can create connections from this/to this node as usual.
The node has for now 3 possible input parameters 'a, b, c', one 'expression'
and 1 output parameter 'result'. The 'expression' parameter can contain
any mathematical formula (including constants). For examples below:
  ```
  sin(a)
  a+b
  sin(a*pi/2)
  sin((a+sqrt(b))*3.14/180)-c
  factorial(c)
  sum([10, .1, c])
  ```

The expression has to be written in Python syntax. Python Math functions are
documented here: http://docs.python.org/library/math.html

## Uninstallation

### Manual Uninstall

Simply removing the "mathNode.mod" files from your system folder, and
delete the plug-in module folder will uninstall the plug-in.

### Uninstall from the AppStore

Go and Download the plugin installer from the
[AppStore](https://apps.autodesk.com/MAYA/en/Detail/Index?id=212304226072872821&appLang=en&os=Win64)

## Notes

Instead of writing a very long formula in one node, you can combine
several node to compose a complete formula. This will have a very limited
impact on the execution/evaluation time.

## Limitations

The current implementation accepts both native Python math module functions
and your own function implemented in the Maya embedded Python Editor, but the
Python code for custom functions is not saved within the node/scene.
This UI in the property window is very limited today - the plug-in will be
enhanced in future to support:
  a library of functions,
  the ability to add variables,
  to store python code custom function in file,

## Further Reading

For more information on developing with Maya, please visit the
Maya Developer Center at http://www.autodesk.com/developmaya

## Feedback

Email us at cyrille @ autodesk . com with feedback or requests for enhancements.

## Release History

1.0    Original release                     (August 1, 2012)

--------

## License

This sample is licensed under the terms of the [MIT License](http://opensource.org/licenses/MIT).
Please see the [LICENSE](LICENSE) file for full details.


## Written by

Cyrille Fauvel <br />
Forge Partner Development <br />
http://developer.autodesk.com/ <br />
http://around-the-corner.typepad.com <br />
