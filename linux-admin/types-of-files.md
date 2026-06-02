# Types of files in linux

| File Symbol |   File Type  |
|-------------|--------------|
|  -          | Regular file |
|  d          | Directory    |
|  l          | Link         |
|  c          | Device File  |     
|  s          | Socket       |
|  p          | FIFO or Named Pipe |
|  b          | Block Device |


## Socket (s)

Special file to enable communication between two process.

Find under `/run/`

Example : `/run/chrony/chronyd.sock`

## FIFO or Named-pipe (p)

Sends Data from one process to another so that first receiving process reads the data first-in-first-out manner.

can be created using `mkfifo` command.

## Black device file (b)

A file that refers to a device.

find under `/dev/`

Example: `/dev/sda1/`

## Character device file

We can create using mknod command. 
These files are present in `/dev` folder.
File that reads/writes data in character by character. 

Example: `/dev/input/mouse2`


