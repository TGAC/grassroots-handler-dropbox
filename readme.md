# Dropbox handler

The Dropbox handler allows the Grassroots Server to access any files and directories stored on a [Dropbox](https://www.dropbox.com) system.

Handlers are components that abstract out common I/O operations such as opening and closing files as well as reading and writing to them. By using the Handler API, any component in the Grassroots infrastructure can access these resources without having to worry about how or where they are stored.
 
## Installation

To build this handler, you need the [grassroots core](https://github.com/TGAC/grassroots-core) and [grassroots build config](https://github.com/TGAC/grassroots-build-config) installed and configured. 

The files to build the Dropbox handler are in the ```build/<platform>``` directory. 

### Linux

If you enter this directory 

```cd build/linux```

you can then build the service by typing

```make all```

and then 

```make install```

to install the handler into the Grassroots system where it will be available for use immediately.

