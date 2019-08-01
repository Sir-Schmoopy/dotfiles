These are my dotfiles.  There are many like them, but these ones are mine.

# Notes to Future Sams:

## New computer?

* clone this repo to ~/dotfiles
* `cd dotfiles`
* Set up shell helpers, aliases, config files, and so on:
  * `./symlink_all_the_things`
* Make sure homebrew is installed:  https://brew.sh/
* Install `asdf` and use it to manage Ruby versions:
  * `brew install asdf`
  * `brew install openssl libyaml libffi` (required by the `asdf-ruby` plugin; note that this may cause some Ruby Woes below)
  * `asdf plugin-add ruby https://github.com/asdf-vm/asdf-ruby.git`
* Launch vim and run `:PlugInstall`

## Ruby Woes

### Trouble getting Ruby's `mysql2` gem to build properly?

You probably need to add a few hints about where stuff is.  (Obviously,
double-check the paths below; new computers may not need to run MySQL 5.6, for
example.)

* If mysql_config can't be found, try adding:
  `-- --with-mysql-config=/usr/local/opt/mysql@5.6/bin/mysql_config`
* If `-lss` can't be linked, try adding:
  `-- --with-ldflags=-L/usr/local/opt/openssl/lib --with-cppflags=-I/usr/local/opt/openssl/include`

--

Clever ideas I could possibly implement at some point:

- add an indicator to the prompt showing whether the last command had an
  exit status of 0


