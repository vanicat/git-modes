Emacs modes for various Git-related files
-----------------------------------------

This repository contains several libraries which are useful when
dealing with certain Git-related files.  For the most part these
libraries do not depend on one another and are available as a
separate Elpa package.

To use the current versions install each of the packages you are
interested in from [Melpa][melpa].  Alternatively you can clone
this repository and put it on the `load-path`.

Note that loading any of these libraries modifies `auto-mode-alist`.


### gitconfig-mode: edit .gitconfig files

This mode is automatically enabled for `.gitconfig`, `.git/config`
and `git/config` files.  The mode derives from `conf-unix-mode`, so
all commands provided by `conf-mode` work as expected.

Also see the [`git-config(1)` manpage][git-config].


### gitattributes-mode: edit .gitattributes files

This mode is automatically enabled for `.gitattributes`,
`.git/info/attributes`, and `git/attributes`.  `eldoc-mode` is
supported for known attributes.

Also see the [`gitattributes(5)` manpage][gitattributes].


### gitignore-mode: edit .gitignore files

This mode is automatically enabled for `.gitignore`,
`.git/info/exclude` and `git/ignore` files.

Also see the [`gitignore(5)` manpage][gitignore].


### git-commit-mode: edit Git commit messages

This mode is automatically enabled for `COMMIT_EDITMSG` and similar
files.  Features include:

* Spell-checking.
* Use of arbitrary major-mode.
* Insertion of pseudo headers.
* Highlighting of badly formatted parts of the commit message.
  See e.g. the [guidelines][pope-note] by Tim Pope.
* History cycling.

Also see the [`git-commit(1)` manpage][git-commit].


### git-rebase-mode: edit git-rebase-todo files

This mode is automatically enabled for `git-rebase-todo` files, such
as created by `git rebase -i`.

Also see the [`git-rebase(1)` manpage][git-rebase].


### with-editor: use the Emacsclient as $EDITOR

This is a low-level library used by `git-commit-mode` and
`git-rebase-mode`.  It can also be used by other packages.

The use of the `with-editor` macro instructs child processes to use
the Emacsclient as `$EDITOR`, making sure they know how to call home.
For remote processes a substitute is provided, which communicates with
Emacs on stdout instead of using a socket as the Emacsclient does.


Credits
-------

- `gitattributes-mode` was created by [Rüdiger Sonderfeld][r].

- `gitconfig-mode` was created by [Sebastian Wiesner][s].

- `gitignore-mode` was created by [Sebastian Wiesner][s].

- `git-commit-mode` consolidates various implementations which existed
  under this or other names.  This includes [Sebastian Wiesner][s]
  implementation which was originally forked from [Florian Ragwitz][f]
  [implementation][rafl-mode], and code which was previously part of
  [Magit][magit], mostly by [Marius Vollmer][m] and [Phil Jackson][p].
  Some of these implementations may have incorporated ideas and code
  from the `log-edit` library which is part of Emacs.

  The core functionality has, for the most part, been rewritten by
  [Jonas Bernoulli][j] among other things to clean it up, use the
  `with-editor` library and make it more flexible.  The font-lock and
  pseudo-header functionality is mostly based on
  [Sebastian Wiesner][s] work.

- `git-rebase-mode` was previously part of [Magit][magit] as
  `rebase-mode`.  It was created by [Phil Jackson][p] and later
  improved by [Peter J. Weisberg][w].  [Jonas Bernoulli][j] cleaned it
  up and made it use `with-editor`.

For a full list of contributors see [this page][contributors].

All modes are currently maintained by [Jonas Bernoulli][j].

Thanks to all of you - may the source be with you!


License
-------

Git-Modes is free software; you can redistribute it and/or modify it
under the terms of the GNU General Public License as published by the
Free Software Foundation; either version 3, or (at your option) any
later version.

Git-Modes is distributed in the hope that it will be useful, but
WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU
General Public License for more details.

You should have received a copy of the GNU General Public License
along with Git-Modes.  If not, see <http://www.gnu.org/licenses/>.

See [`COPYING`][copying] for details.


[contributors]: https://github.com/magit/git-modes/graphs/contributors
[copying]: https://github.com/magit/git-modes/blob/master/COPYING
[git-commit]: http://git-scm.com/docs/git-commit
[git-config]: http://git-scm.com/docs/git-config
[git-rebase]: http://git-scm.com/docs/git-rebase
[gitattributes]: http://git-scm.com/docs/gitattributes
[gitignore]: http://git-scm.com/docs/gitignore
[magit]: http://magit.github.com/magit
[melpa]: http://melpa.milkbox.net
[pope-note]: http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html
[rafl-mode]: https://github.com/rafl/git-commit-mode

[f]: https://github.com/rafl
[j]: https://github.com/tarsius
[m]: https://github.com/mvollmer
[p]: https://github.com/philjackson
[r]: https://github.com/ruediger
[s]: https://github.com/lunaryorn
[w]: https://github.com/pjweisberg
