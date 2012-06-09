git-weekly-report (2.0.0)
=========================
Chris Lane  
chris@chris-allen-lane.com  
http://chris-allen-lane.com  
http://twitter.com/#!/chrisallenlane


About
-----
`git-weekly-report` generates development reports based off of git 
commit logs on a per-project and per-user basis.

This script evolved from my own needs. Every Friday I send my 
clients a summary of my git commits on a per-project basis. 
Assembling such information manually is tedious, though, and thus I 
wrote this script.


What it Does
------------
`git-weekly-report` iterates over a hash of specified git repositories, 
and queries your commit messages out of the logs for each. 

If run without a date, this script queries the logs back to the most 
recent Monday. A typical use-case for this script would be to be 
run once per week at the end of the week. Thus, "git-weekly-report".


Configuration
-------------
Configuration is simple: you just need to tell `git-weekly-report` 
where your git repositories are located. You also need to specify a 
human-readable name for each. This information is specified in a 
hash in `projects.rb`.


Usage
-----
Usage will look like one of the following examples:

```bash
git-weekly-report -g 'John Smith' -l '~/Desktop/' -p ./projects.rb
git-weekly-report -g 'John Smith' -l '~/Desktop/' -p ./projects.rb -s 'monday'
git-weekly-report -g 'John Smith' -l '~/Desktop/' -p ./projects.rb -s '09 Jun 2012'
```

Wherein:
- `-g` (`--git-user-name`) specifies your git user name (as per `git config --global user.name`)
- `-l` (`--log-path`) specifies the directory in which to write the reports
- `-p` (`--project-file`) specifies the location of the project file
- `-s` (`--since`) optionally specifies a date back to which the logs should
be queried. If `--since` is omitted, the nearest Monday is assumed.


FAQ
---
**Why is the project hash stored in its own file? Why not store that 
hash in the `git-weekly-report` file itself?**

I felt like it would be cleaner to store the "program" in a location 
separate from its "data". Also, storing the data separately allows 
you to group projects within different files. This can be useful if 
you're managing a huge number of projects. For example, you may 
want to group each of your clients' projects into individual files, 
and then specify the appropriate project file at runtime.


License
-------
This product is licensed under the GPL 3 (http://www.gnu.org/copyleft/gpl.html).
It comes with no warranty, expressed or implied.
