# juce-plugin-template-vscode
A template repo for a juce plugin with VSCode support for Linux and Mac. With a WYSIWYG editor.

# Linux Setup for JUCE framework

## Features
- code-oss support
- C++ IntelliSense
- debugging
- .vscode automations

## Setup guide
### Juce and Projucer 
1. Downkoad the JUCE framework and Projucer from https://juce.com/download/
1. Move the JUCE folder to your home directory ~
1. Execute the Projucer executable located in ~/JUCE/Projucer
1. File > Sign In > select enable gpl mode
1. Make sure the File > Global Paths are ok. (They should point to your ~/JUCE/ directory). Check for 
    1. Path to JUCE 
    1. JUCE modules
1. Create a new project from Projucer, give it a name, make sure the Linux-Makefile is checked, Xcode (macOS) in the Exporters section, 
1. Or open an existing one. like this repo. (Open the .jucer file)

### Linux Manual build
1. Go to your project foler and `Builds/LinuxMakeFile`. Run `make CONFIG=Debug` to make sure you can build the file, and not missing any dependencies.
1. Execute the executable located in `Builds/LinuxMakefile/build/DemoApp` or check that your vst is created, depending on the options you set in Projucer
1. `sudo pacman -S gdb` for the debugger to work

### Mac build
Open and run the app once from xcode to generate some files that are necessary for the build task to run.

### Code-Oss
1. Install the C/C++ IntelliSense extension for code-oss

### `c_cpp_properties.json` (Linux)
1. update the usr/include/c++/x.x.x versions to match the ones installed in your system
1. update the usr/lib/gcc/ versions to match the ones installted in your system
1. Make sure the JUCE/modules paths are correct

### `tasks.json` (Mac)
Make sure the paths are correct

### `launch.json` (Mac)
1. make sure the `osx.program` path specified, is correct

### Running the app
- Click `ctrl+shift+b` to open the tasks menu in vscode
    1. clean all
    1. build
- Go to the run menu in the left side menu and select C++ Launch (The debugger should work by putting a breakpoint in vscode editor)

## Resources
- https://stackoverflow.com/questions/46258143/visual-studio-code-how-to-configure-includepath-for-better-intellisense-results
- https://github.com/icq4ever/emptyJUCEProject
- https://forum.juce.com/t/visual-studio-for-mac/22358/20
- https://github.com/ChristopherJohnston/HelloWorldPlugin
- https://www.reddit.com/r/JUCE/comments/bbrjsb/how_to_run_juce_project_on_linux/


