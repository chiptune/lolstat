# lolstat
an i3wm status bar alternative

### usage

1. copy <b>lolstat</b> to your i3 config directory (usually ~/.i3/)

2. create and save an <b>i3status.sh</b> file:

    \#!/usr/bin/env bash<br>
    i3status -c ~/.i3/<b>i3status.conf</b> | while :<br>
    do read line; ~/.i3/<b>lolstat</b> 2>/dev/null || exit 1; done

  don't forget to chmod 775 it!

3. edit your ~/.i3/config file and update the "status_command" to call the previously created file

    status_command ~/.i3/<b>i3status.sh</b>

4. reload your i3wm setup! \\:D/
