# lolstat
an i3wm status bar alternative

### configuration

the last line of the script is my current status bar configuration, it use:
        
        ${USER}
        $(upd)
        $(disk "/dev/sda" "/") / $(disk "/home" "${home}") / etc...
        $(io "sda")
        $(cpu)
        $(ram)
        $(netw)
        $(url "lol.pm" "lol")
        $(weather)
        $(clock)
        $(power)
        $(mixer "Master")

### setup

1.  copy **lolstat** to your i3 config directory (usually ~/.i3/)

2.  create and save an **i3status.sh** file:

        #!/usr/bin/env bash
        i3status -c ~/.i3/i3status.conf | while :
        do read line; ~/.i3/lolstat 2>/dev/null || exit 1; done

    don't forget to chmod 775 it!

3.  edit your ~/.i3/config file and update the "status_command" to call the previously created file

        status_command ~/.i3/i3status.sh

4.  reload your i3wm setup! \\:D/

### bugfix

if you encounter some bugs on your computer, email me the output!

        **time(~/.i3/lolstat)
