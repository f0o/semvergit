# semvergit

Extremely naive way of generating SemVer2 releases from gitlog.
Majors are tags, Minors are merges and Patches are commits.

Probably doesnt work everywhere.

## Requirements

* git
* tail
* cut
* bash

## Usage

```
foobar (master) $ ./getver.sh
0.0.1
foobar (branchname) $ git checkout -b branchname
foobar (branchname) $ ./getver.sh
0.0.1+branchname
foobar (branchname) $ date > test
foobar (branchname*) $ git add test
foobar (branchname*) $ git commit -a -m "test"
foobar (branchname) $ ./getver.sh
0.0.2+branchname
foobar (branchname) $ git checkout master
foobar (master) $ ./getver.sh
0.0.1
foobar (master) $ git merge --no-ff branchname
foobar (master) $ ./getver.sh
0.1.0
```
