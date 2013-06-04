# Console.IO

Console.IO is a NodeJS project. It provides Remote Web Console for websites and web applications.
It uses express.io (express & socket.io) to provide user real time experience.

It works pretty much on all modern browsers, mobile devices, Smart TVs, etc

Tested on: 
* Toshiba TV (2011, 2012)
* LG NetCast TV (2011, 2012, 2013)
* Philips NetTV (2011, 2012)
* Samsung TV (2010, 2011, 2012, 2013)
* Technika Avtrex STB
* Firefox, Safari, Opera, Chrome, Maple and IE
* iPhone, iPod, iPad, Android browser, windows 8 phone etc


## Install express.io (execute install.bat)

```bash
npm install express.io
```

## Start server (execute start.bat)

```bash
node ./server/main.js
```

##Scale Console.IO server

Console.IO use socket.io and in order to scale socket.io you need to run redis server (/redis/redis-server.exe).
And also change following value in server/config.js before starting the Console.IO server

```html
redis: {
        enable: true, // <- true to enable socket.io scaling
        process: 6 // number of process to run
    }
```

## Include Console.IO in your web page

include inject.js scripts with config parameters

```html
<script type="text/javascript" src="inject.js?url=http://NodeServerURL:Port&secure=false"></script>
```

OR create a create ConfigIO global object with config options

```html
<script type="text/javascript" src="configIO.js"></script>
<script type="text/javascript" src="inject.js"></script>
```

configIO.js
```html
window.ConfigIO = {
	url: 'http://nodeserver:port/',
	secure: false
};
```

OR you can include all files individually

```html
<script type="text/javascript" src="<Local Folder OR Node Server/socket.io>/socket.io.js"></script>
<script type="text/javascript" src="<Local Folder OR Node Server>/console.io.js"></script>
<script type="text/javascript" src="<Local Folder OR Node Server>/socket.js"></script>
<script type="text/javascript" src="<Local Folder OR Node Server>/inject.js?url=http://NodeServerURL:Port"></script>
```


Visit http://NodeServerURL:Port/ for ConsoleIO interface

![Screen shot](https://raw.github.com/nkashyap/console.io/master/console.io.png)

##Console.IO Editor

You can execute commands on remote client from Console.IO. You can execute single & multilines javascript code.

Shortcuts: 
* Ctrl+Enter: execute command
* Ctrl+Space: autocomplate
* Ctrl-Q: toggle comments

Note: All multilines code should be wrapped within self executable function. E.G
```html
(function doSomeThing(){
 .......
}())
```

##Console.IO Device and Tabs
* Files: Show all attached javascript and css files in the web page
* Status: Device Status and some basic information
* Source: Double click on a file in file explorer to view file content
* Preview: HTML dom structure
* Console: Remote console 
	* Pause incoming logs
	* Clear logs
	* Export logs
	* Change page size
	* Search word or use regex to filter logs
	* Filter logs by type


##Console API methods supported
 * console.assert(x)
 * console.count(key)
 * console.time(name, reset)
 * console.timeEnd(name)
 * console.debug(arguments...)
 * console.warn(arguments...)
 * console.info(arguments...)
 * console.log(arguments...)
 * console.dir(object)
 * console.dirxml(HTML Element)
 * console.error(error)
 * console.exception(error)
 * console.trace()

##Coming soon...
 * console.group()
 * console.groupCollapsed()
 * console.groupEnd()
 * console.markTimeline()
 * console.timestamp()
 * console.profiles
 * console.profile()
 * console.profileEnd()

##TODO
 * Change it into npm module
 * Load addons dynamically (e.g web, socket, etc)
 * Update Readme with full feature list
 * Add SSL support

##Copyright and license
 MIT LICENSE 

##Reference
 * [Javascript Stacktrace] (https://github.com/eriwen/javascript-stacktrace)
 * [codemirror] (http://codemirror.net/)
 * [express.io] (https://github.com/techpines/express.io)
 * [Socket.io] (http://socket.io/#how-to-use)
 * [prettify] (https://code.google.com/p/google-code-prettify/)
 * [dhtmlx] (http://dhtmlx.com/) [GPL LICENSE]