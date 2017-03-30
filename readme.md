# Dropbox handler

The Dropbox handler allows the Grassroots Server to access any files and directories stored on a [Dropbox](https://www.dropbox.com) system. Its use the [Dropbox C](https://github.com/Dwii/Dropbox-C) and [liboauth](https://sourceforge.net/projects/liboauth) libraries.

Handlers are components that abstract out common I/O operations such as opening and closing files as well as reading and writing to them. By using the Handler API, any component in the Grassroots infrastructure can access these resources without having to worry about how or where they are stored.
 
## Installation

To build this handler, you need the [grassroots core](https://github.com/TGAC/grassroots-core) and [grassroots build config](https://github.com/TGAC/grassroots-build-config) installed and configured. 

The files to build the Dropbox handler are in the ```build/<platform>``` directory. 

### Linux

Enter the build directory 

```cd build/linux```

and create a *user.prefs* file.

```cp example-user.prefs user.prefs```

You will need to edit this file to configure where the Dropbox handler dependencies are stored. The file content is similar to the following

``` 
#
# dropbox dependencies
#

# Set this to where you have the dropbox and liboauth directory 
# containing "include" and "lib" subdirectories.
export DROPBOX_HOME := $(DIR_GRASSROOTS_EXTRAS)/dropbox
export OAUTH_HOME := $(DIR_GRASSROOTS_EXTRAS)/liboauth
```

Adjust the ```DROPBOX_HOME``` and ```OAUTH_HOME``` variables to where you have the mongo-c-driver installed. You can then build the handler by typing

```make all```

and then 

```make install```

to install the handler into the Grassroots system where it will be available for use immediately.

