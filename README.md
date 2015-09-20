# lolstat
an i3wm status bar alternative

## usage

create and save an i3status.sh file:

> \#!/usr/bin/env bash
> i3status | while :
> do
>   read line
>   <install_path>lolstat 2>/dev/null || exit 1
> done


1. edit your ~/.i3/config file and update the "status_command" to call the i3status.sh file
