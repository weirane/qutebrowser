## Background

qutebrowser is a keyboard-driven, vim-like browser based on Python and Qt.

**Command line system**: qutebrowser has a command line system, which can be triggered by hitting the <kbd>:</kbd> key
(<kbd>Shift</kbd>+<kbd>;</kbd>). You can then enter the command after the `:` in the
bottom input bar. For example, to open a web page, you type
`:open https://google.com`, and then hit <kbd>Enter</kbd>.

<img width="912" height="487" alt="Screenshot 2025-10-02 at 11 54 57" src="https://github.com/user-attachments/assets/c4309dd4-a48e-4781-b237-7f5e60fcf5b1" />

**`:open` command**: The `:open` command of qutebrowser is similar to the address bar of regular browsers. Apart from opening URLs, it can also serve as a search bar. For example, you can type `:open something` to go to the search result for "something" in the default search engine.

**Custom search engines**: qutebrowser allows you to define your own search engines. For example, when you define a search engine `wiki` as `https://en.wikipedia.org/w/index.php?search=%s`, using command `:open wiki something` will take you to the URL `https://en.wikipedia.org/w/index.php?search=something`, which is the search result for "something" on wikipedia.

## Setup guide

After you have cloned the repository, use command `python3 scripts/mkvenv.py` to
setup a virtual environment. A virtualenv will be created in `./.venv` and the qutebrowser
will be installed there. You can run it with
```
.venv/bin/qutebrowser
```

To enable debug logs, run it with
```
.venv/bin/qutebrowser --debug
```

If you encountered any issues, you can consult the official guide [here](./doc/contributing.asciidoc#running-qutebrowser).

## Running unit tests

To run the unit tests, you need to install [`tox`](https://tox.wiki/en/latest/). You can install it in the virtual
environment
```
source .venv/bin/activate
pip install tox
```
or you can install it globally using tools like [`uv`](https://docs.astral.sh/uv/).
```
uv tool install tox
```

You can run the unit tests related to the tasks with
```
tox -e py39-pyqt515-cov -- tests/unit/utils/test_urlutils.py
```

See [official guide](./doc/contributing.asciidoc#checkers) for more information.
