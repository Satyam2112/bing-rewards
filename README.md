# Bing-Rewards

<div align="center">
<img alt="PyPI - Python Version" src="https://img.shields.io/pypi/pyversions/bing-rewards?style=flat-square&label=Python&logo=python&logoColor=yellow">
<a href="https://pypi.org/project/bing-rewards/"> <img alt="PyPi" src="https://img.shields.io/pypi/v/bing-rewards?label=PyPI&style=flat-square&logo=pypi&logoColor=yellow"></a>
<a href="https://pypi.org/project/bing-rewards/"> <img alt="PyPI - Downloads" src="https://img.shields.io/pypi/dm/bing-rewards?style=flat-square&label=Downloads&color=orange"></a>
<br>
<img alt="PyPI - License" src="https://img.shields.io/pypi/l/bing-rewards?style=flat-square&label=License&color=blueviolet">
<a href="https://github.com/psf/black"> <img alt="Formatting" src="https://img.shields.io/badge/Code%20Style-Black-000000?style=flat-square"> </a>

</div>

### A script to automate daily Bing rewards points
Please submit an issue or pull-request if you have an idea for a feature

#### :exclamation: NOTE: The user agent spoofing seems to have stopped working when using Microsoft Edge browser. Currently investigating if this is a breaking change on their side (See issue [#13](https://github.com/jack-mil/bing-rewards/issues/13)). For the time being, Brave and Chrome seem to work fine.

## **Features:**

* Spoofs user agent to appear as Mobile or Desktop Edge Browser using Chrome/Brave!
* Script auto-types searches, so must be run in a GUI environment. Great for AFK grinding once a day for those points
* Use a mobile user agent to get mobile points (`--mobile`)
* Configurable number of searches with `--count=`
* All files are local, makes no http(s) requests
* Only one external dependance (PyAutoGUI)
* Fine tune delay and set browser executable with config at $XDG_CONFIG_HOME or %APPDATA% on Windows
***

## **Install with Pip!**

```bash
pip install bing-rewards
```
Will make the executable `bing-rewards` available on your PATH.
Look below or try the `--help` flag to see detailed usage.

## **Requirements:**

- At least Python 3.6.

- [PyAutoGUI](https://github.com/asweigart/pyautogui) package is used to control keypresses and type Bing search URLS.
WARNING: This script *will* take control away from the keyboard while running. PyAutoGUI performs key presses. i.e., it does not operate headless or in the background.

- `chrome` must be discoverable on the system PATH. [Download Google Chrome](https://www.google.com/intl/en/chrome/).
If you use a different chromium based browser that supports setting user agents via the `--user-agent` option (tested with Brave), you can use the `--exe` flag with an absolute path to the browser executable to use.

- To earn points from searching, you must also have logged into [bing.com](https://www.bing.com) with your Microsoft account at least once, to save cookies.

## **Usage:**

#### `bing-rewards [-h] [--no-window] [-n] [--exe EXE] [-c COUNT] [-d | -m]`

Ex:
Complete mobile and desktop daily points

`$ bing-rewards`

Run 10 searches with mobile user-agent in a new window

`$ bing-rewards -m -c10`

`$ bing-rewards --mobile --count=10`

Launches Chrome as a subprocess with special flags. Only tested on Windows 10, however it should work on other platforms

??????Known Issue: No other instance of chrome.exe can be open when the script runs. Chrome prevents different user agents in each window. The script will run, but Chrome will not appear as Edge


## **All options:**

Running with no options will complete mobile and desktop daily search quota. The following options are available to change the default behavior.
| Flag              | Option                                                                              |
| ----------------- | ----------------------------------------------------------------------------------- |
| `-h`, `--help`    | Display help and exit                                                               |
| `-c`, `--count=N` | Override the number of searches to complete                                         |
| `-d`, `--desktop` | Only use desktop user agent                                                         |
| `-m`, `--mobile`  | Only use a mobile user agent                                                        |
| `-n`, `--dryrun`  | Do everything but type the search query                                             |
| `-X`, `--no-exit` | Do not close the browser after completing a search                                  |
| `--exe EXE`       | The full path of the Chrome compatible browser executable (Brave and Chrome tested) |
| `--nowindow`      | Don't open a new Chrome window, just type the keys                                  |


## User agents:

If interested, the following user agents are passed to Chrome using the `--user-agent` argument. These are clearly defined at the top of `bing-rewards.py`.

Edge Browser on Windows 10 desktop:
> Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.61 Safari/537.36 Edg/83.0.478.37

Mobile Edge Browser on Windows 10 phone:
> Mozilla/5.0 (Windows Phone 10.0; Android 6.0.1) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/70.0.3538.102 Mobile Safari/537.36 Edge/18.19041
***

## Words:
The [keywords](https://www.myhelpfulguides.com/keywords.txt) included in this repo where taken from this site
https://www.myhelpfulguides.com/2018/07/19/bing-rewards-auto-searcher-with-python-3/.

This script provided the original inspiration but has since been complelty rewritten and expanded.
The original author was contacted for the original source of keywords, but declined to respond
