To use the script in cmus, you must acquire an API key from [audioscrobbler](http://www.last.fm/api/account/create)

Then update the script
```python
 15 # api key is now required, old txt method no longer works
 16 # http://www.last.fm/api/account/create
 17 API_KEY = ''
```

Then set status_display_program to the path of the
cmus_add_similar.py file, e.g. in cmus:

`:set status_display_program=/path/to/cmus_add_similar.py`

If you want to use multiple status display programs, you have to write a
wrapper shell script

```bash
cat >/home/XXX/.cmus/status_display_program.sh <<END
#!/bin/sh

/path/to/cmuscrobbler "$@"
/path/to/cmus_add_similar.py "$@" &
END
```

```bash
chmod 755 /home/XXX/.cmus/status_display_program.sh
```

In cmus:
`:set status_display_program=/home/XXX/.cmus/status_display_program.sh`


Attention: You need at least cmus 2.4.x, 2.3.x or older is not
           supported anymore.

For questions: jargon@molb.org
