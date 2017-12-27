1.1.1
=====
### Fixes:
- Fix output interleaving in `check-vcs-permalinks` under python3.
    - #245 PR by @asottile.

1.1.0
=====
### Features:
- `check-yaml` gains a `--allow-multiple-documents` (`-m`) argument to allow
  linting of files using the
  [multi document syntax](http://www.yaml.org/spec/1.2/spec.html#YAML)
    - pre-commit/pre-commit#635 issue by @geekobi.
    - #244 PR by @asottile.

1.0.0
=====
### Features:
- New hook: `check-vcs-permalinks` for ensuring permalinked github urls.
    - #241 PR by @asottile.

### Fixes:
- Fix `trailing-whitespace` for non-utf8 files on macos
    - #242 PR by @asottile.
- Fix `requirements-txt-fixer` for files ending in comments
    - #243 PR by @asottile.

0.9.5
=====
- Fix mixed-line-endings `--fix=...` when whole file is a different ending

0.9.4
=====
- Fix entry point for `mixed-line-ending`

0.9.3
=====
- New hook: `mixed-line-ending`

0.9.2
=====
- Report full python version in `check-ast`.
- Apply a more strict regular expression for `name-tests-test`
- Upgrade binding for `git-lfs` for `check-added-large-files`.  The oldest
  version that is supported is 2.2.1 (2.2.0 will incorrectly refer to all
  files as "lfs" (false negative) and earlier versions will crash.
- `debug-statements` now works for non-utf-8 files.

0.9.1
=====
- Add `check-executables-have-shebangs` hook.

0.9.0
=====
- Add `sort-simple-yaml` hook
- Fix `requirements-txt-fixer` for empty files
- Add `file-contents-sorter` hook for sorting flat files
- `check-merge-conflict` now recognizes rebase conflicts
- Metadata now uses `types` (and therefore requires pre-commit 0.15.0).  This
  allows the text processing hooks to match *all* text files (and to match
  files which would only be classifiable by their shebangs).

0.8.0
=====
- Add flag allowing missing keys to `detect-aws-credentials`
- Handle django default `tests.py` in `name-tests-test`
- Add `--no-ensure-ascii` option to `pretty-format-json`
- Add `no-commit-to-branch` hook

0.7.1
=====
- Don't false positive on files where trailing whitespace isn't changed.

0.7.0
=====
- Improve search for detecting aws keys
- Add .pre-commit-hooks.yaml for forward compatibility

0.6.1
=====
- trailing-whitespace-hook: restore original file on catastrophic failure
- trailing-whitespace-hook: support crlf
- check-yaml: Use safe_load
- check-json: allow custom key sort
- check-json: display filename for non-utf8 files
- New hook: forbid-new-submodules

0.6.0
=====
- Merge conflict detection no longer crashes on binary files
- Indentation in json may be an arbitrary separator
- Editable requirements are properly sorted
- Encoding pragma fixer pragma is configurable

0.5.1
=====
- Add a --no-sort-keys to json pretty formatter
- Add a --remove to fix-encoding-pragma

0.5.0
=====
- Add check-byte-order-marker
- Add check-synlinks
- check-large-files-added understands git-lfs
- Support older git
- Fix regex for --django in test name checker
- Add fix-encoding-pragma hook
- requirements-txt-fixer now sorts like latest pip
- Add check-ast hook
- Add detect-aws-credentials hook
- Allow binary files to pass private key hook
- Add pretty-format-json hook

0.4.2
=====
- Add --django to test name checker
- Add check-merge-conflict hook
- Remove dependency on plumbum
- Add q as a debug statement
- Don't detect markup titles as conflicts
- Teach trailing-whitespace about markdown
- Quickfix for pyflakes - flake8 version conflict

0.4.1
=====
- Respect configuration when running autopep8
- Quickfix for pep8 version conflicts

0.4.0
=====
- Fix trailing-whitespace on OS X
- Add check-added-large-files hook
- Add check-docstring-first hook
- Add requirements-txt-fixer hook
- Add check-case-conflict hook
- Use yaml's CLoader when available in check-yaml for more speed
- Add check-xml hook
- Fix end-of-file-fixer for windows
- Add double-quote-string-fixer hook

0.3.0
=====
- Add autopep8-wrapper hook

0.2.0
=====
- Add check-json hook

0.1.1
=====
- Don't crash on non-parseable files for debug-statement-hook

0.1.0
=====
- Initial Release
