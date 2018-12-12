# lolstat
an i3wm status bar alternative
> ![system](http://lol.pm/lolstat/system.png)

### configuration

the last line of the script is my current status bar configuration, it use:

function   | comment
---------- | ---------
${USER}    | be proud of yourself, display your username!
$(upd)     | countdown to the next lolstat update (in second)
$(disk "**path**" "**name**") | disk usage, specify a **path** and an optional display **name**
$(io "**partition**") | volume input/output, specify a /dev/ **partition**
$(cpu)     | cpu speed and charge
$(ram)     | ram usage
$(netw)    | display all networks currently in use (except lo 127.0.0.1)
$(url "**url**" "**name**") | ping the specified **url** (happyface when ping<100ms)
$(weather) | current weather based on your geolocalized IP
$(clock)   | time!
$(power)   | your current battery status (if `ACPI` is available)
$(mixer "**channel**") | current sound mixer **channel** volume (generally `Master`)

### setup

1.  copy **lolstat** to your i3 config directory (usually ~/.i3/)

2.  create and save an `i3status.sh` file:

```bash
#!/usr/bin/env bash
i3status -c ~/.i3/i3status.conf | while read line; do ~/.i3/lolstat 2>/dev/null || exit 1; done
```

3.  add lolstat font to your local fonts:

```bash
mkdir -p ~/.local/share/fonts
cp lolstat.ttf ~/.local/share/fonts
```

4.  edit your `~/.i3/config` file and update the `status_command` line as following:

```bash
bar {
  font pango:lolstat 20
  status_command ~/.i3/i3status.sh
}
```

5.  reload your i3wm ($mod+shift+r) setup and it's done! \\:D/

### bugfix

if you encounter some bugs on your computer, email me the output of the following command:

```bash
time(~/.i3/lolstat)
```
