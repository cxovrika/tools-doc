# Gobuster

**Note**: seems like an alternative to dirbuster with almost (if not exactly) the same functionality

### Packages
* [AUR package](https://aur.archlinux.org/packages/gobuster/)

### Cheatsheet

GoBuster flag     | Description
------------------|-------------------------------------
-e                | Print the full URLs in your console
-u                | The target URL
-w                | Path to your wordlist
-U and -P         | Username and Password for Basic Auth
-p <x>            | Proxy to use for requests
-c <http cookies> | Specify a cookie for simulating your auth


### Usage
```
Usage:
  gobuster [command]

Available Commands:
  dir         Uses directory/file enumeration mode
  dns         Uses DNS subdomain enumeration mode
  fuzz        Uses fuzzing mode
  help        Help about any command
  s3          Uses aws bucket enumeration mode
  version     shows the current version
  vhost       Uses VHOST enumeration mode

Flags:
      --delay duration    Time each thread waits between requests (e.g. 1500ms)
  -h, --help              help for gobuster
      --no-error          Don't display errors
  -z, --no-progress       Don't display progress
  -o, --output string     Output file to write results to (defaults to stdout)
  -p, --pattern string    File containing replacement patterns
  -q, --quiet             Don't print the banner and other noise
  -t, --threads int       Number of concurrent threads (default 10)
  -v, --verbose           Verbose output (errors)
  -w, --wordlist string   Path to the wordlist

Use "gobuster [command] --help" for more information about a command.
```