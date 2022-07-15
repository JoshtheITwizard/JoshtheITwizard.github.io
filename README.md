
## Horizontal Rules

___


## Emphasis

**This is bold text

__This is bold text__

*This is italic text*
_This is italic text_

~~Strikethrough~~



## Blockquotes


> Blockquotes can also be nested...
> >...by using additional greater-than signs right next to eachj other...
> > >...or with spaces between arrows


## Lists

Unordered

+ Create a list by starting with `+`, `-`, or `*`
+ Sub-lists are made by indenting 2 spaces:
  -Marker character change forces new list start:
    *Ac tristique libero volutpat at
    + Facilisis in pretium nisl aliquet
    -Nulla volutpat aliquam velit
+ Very easy!

Ordered

1. Lorem ipsum dolor sit amet
2. Consectetur adipiscing elit
3. Integer molestie lorem at massa

## Code

Inline `code`

Indented code

    // some comments
 #!/usr/bin/env python
import socket
import subprocess
import sys
from datetime import datetime

# Clear the screen
subprocess.call('clear', shell=True)

# Ask for input
remoteServer    = raw_input("Enter a remote host to scan: ")
remoteServerIP  = socket.gethostbyname(remoteServer)

# Print a nice banner with information on which host we are about to scan
print "-" * 60
print "Please wait, scanning remote host", remoteServerIP
print "-" * 60

# Check what time the scan started
t1 = datetime.now()

# Using the range function to specify ports (here it will scans all ports between 1 and 1024)

# We also put in some error handling for catching errors

try:
    for port in range(1,1025):  
        sock = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
        result = sock.connect_ex((remoteServerIP, port))
        if result == 0:
            print "Port {}: 	 Open".format(port)
        sock.close()

except KeyboardInterrupt:
    print "You pressed Ctrl+C"
    sys.exit()

except socket.gaierror:
    print 'Hostname could not be resolved. Exiting'
    sys.exit()

except socket.error:
    print "Couldn't connect to server"
    sys.exit()

# Checking the time again
t2 = datetime.now()

# Calculates the difference of time, to see how long it took to run the script
total =  t2 - t1

# Printing the information to screen
print 'Scanning Completed in: ', total
    
  
Block code "fences"

```
Sample text here...


Syntax highlighting

``` js
var foo = function (bar) {
  return bar++;
  };
  
  console.log(foo(5));
  ```
  
  ## Tables
  
  | option | Description |
  | ------ | ----------- |
  | data   | path to daty files to supply the data that will be passed into templates. |
  | engine | engine to be used for processing templates. Handlebars is the default. |
  | ext    | extenstion to be used for dest files. |
  
  Right aligned columns
  
  | Option | Description |
  | ------ | ----------: |
  | data   | path to data files to supply the data that will be passeed into templates. |
  | engine | engine to be used for processing templates. Handlebars is the default. |
  | ext    | extension to be used for dest files. 
  
  
  ## Links
  
  [link text](http://dev.nodeca.com)
  
  [link with title](http://nodeca.github.io/pica/demo/ "title text!")
  
  ## Images
  
  //![Minion](http://octodex.github.com/images/minion.png)
  
  ## The End!



    
