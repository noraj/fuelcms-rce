# Fuel CMS RCE exploit / PoC

> Fuel CMS 1.4 - Remote Code Execution

Exploit / PoC for [CVE-2018-16763](https://nvd.nist.gov/vuln/detail/CVE-2018-16763).

[[PacketStorm](https://packetstormsecurity.com/files/160080/Fuel-CMS-1.4-Remote-Code-Execution.html)] [[WLB-2020110119](https://cxsecurity.com/issue/WLB-2020110119)]

## Usage

```
$ ruby exploit.rb -h
Fuel CMS 1.4 - Remote Code Execution

Usage:
  exploit.rb <url> <cmd>
  exploit.rb -h | --help

Options:
  <url>         Root URL (base path) including HTTP scheme, port and root folder
  <cmd>         The system command to execute
  -h, --help    Show this screen

Examples:
  exploit.rb http://example.org id
  exploit.rb https://example.org:8443/fuelcms 'cat /etc/passwd'
```

## Requirements

- [httpclient](https://github.com/nahi/httpclient)
- [docopt.rb](https://github.com/docopt/docopt.rb)

Example for BlackArch:

```
pacman -S ruby-httpclient ruby-docopt
```

Example using gem:

```
gem install httpclient docopt
```

## Reference

This is a better re-write of [EDB-ID-47138][EDB-ID-47138] ([Github](https://github.com/dinhbaouit/CVE-2018-16763)):

- better output (displays only command's output)
- using arguments (instead of hardcoded values)
- cleaner & more customizable
- using ruby (python2 is deprecated)

This exploit was tested with Ruby 2.7.2.

About [EDB-ID-47138][EDB-ID-47138]:

```
# Exploit Title: fuelCMS 1.4.1 - Remote Code Execution
# Date: 2019-07-19
# Exploit Author: 0xd0ff9
# Vendor Homepage: https://www.getfuelcms.com/
# Software Link: https://github.com/daylightstudio/FUEL-CMS/releases/tag/1.4.1
# Version: <= 1.4.1
# Tested on: Ubuntu - Apache2 - php5
# CVE : CVE-2018-16763
```

[EDB-ID-47138]:https://www.exploit-db.com/exploits/47138
