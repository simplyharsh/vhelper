# vhelper
A helper script to deal with python virtualenv

### Pre-requisite
`python-virtualenv`
Script assumes that you already have a stable release of python-virtualenv installed. This script is just a helper, remember.

### Setup

1. Copy/move file `vhelper` into your home folder as `.vhelper`
2. Add to your .bashrc or .bash-profile

```
if [ -f ~/.vhelper ]; then
    source ~/.vhelper
fi
```

### Usage

1- `vhelper_create` - Create new virtualenv for current directory
```
$ vhelper_create 
New python executable in test_vhelper/bin/python2.7
Also creating executable in test_vhelper/bin/python
Installing setuptools, pip, wheel...done.
vhelper: Success. virtualenv 'test_vhelper' created and activated for you. Happy Coding.
 
(test_vhelper)taurean:test_vhelper Harsh$
```

Notes: 
* By default, the name of current directory will be used as name of virtualenv. You can pass an argument to any vhelper command to use a custom name.
* Running `vhelper_create` for the first time, vhelper will create a directory called `.virtualenvs` in your home directory.

If you are not using custom names of virtualenvs (recommended), `vhelper` automatically activates the virtualenv when you `cd` into a folder which has a virtualenv created for it.

```
(test_vhelper)taurean:test_vhelper Harsh$ cd ..
(test_vhelper)taurean:vhelper Harsh$ deactivate 
taurean:vhelper Harsh$ cd test_vhelper/
vhelper: Activated virtualenv 'test_vhelper' for you. Happy Coding.
 
(test_vhelper)taurean:test_vhelper Harsh$ 
```

2- `vhelper_activate` - Switch between virtualenvs
```
(test_vhelper)taurean:test_vhelper Harsh$ vhelper_create other_env
New python executable in other_env/bin/python2.7
Also creating executable in other_env/bin/python
Installing setuptools, pip, wheel...done.
vhelper: Success. virtualenv 'other_env' created and activated for you. Happy Coding.
 
(other_env)taurean:test_vhelper Harsh$ vhelper_activate test_vhelper
vhelper: Activated virtualenv 'test_vhelper' for you. Happy Coding.
 
(test_vhelper)taurean:test_vhelper Harsh$
```

3- `vhelper_goto_env` - Reach the virtualenv directory, for lets say debugging site-packages.
```
(test_vhelper)taurean:test_vhelper Harsh$ vhelper_goto_env 
vhelper: Success. Changed directory to virtualenv 'test_vhelper'. Happy Coding.
 
(test_vhelper)taurean:test_vhelper Harsh$ pwd
/Users/Harsh/.virtualenvs/test_vhelper
(test_vhelper)taurean:test_vhelper Harsh$ vhelper_goto_env v1
vhelper: Success. Changed directory to virtualenv 'v1'. Happy Coding.
 
(test_vhelper)taurean:v1 Harsh$ pwd
/Users/Harsh/.virtualenvs/v1
```

4- `vhelper_remove` - Removing a virtualenv is as easy, even the one you are currently working on.
```
(test_vhelper)taurean:test_vhelper Harsh$ vhelper_remove other_env
vhelper: Success. virtualenv 'other_env' removed. Happy Coding.

(test_vhelper)taurean:test_vhelper Harsh$ vhelper_remove
vhelper: Success. virtualenv 'test_vhelper' removed. Happy Coding.
 
taurean:test_vhelper Harsh$
```

Happy Coding.
