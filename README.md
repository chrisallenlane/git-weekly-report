git-weekly-report
=================
Version 1.0

Chris Lane, 17 November 2011
chris@chris-allen-lane.com
http://chris-allen-lane.com




About
-----
git-weekly-report is a simple Ruby script used to generate weekly reports
of your recent development activities on a per-project basis by aggregating
information out of the git logs.

It is very minimalist script based off of the YAGNI (You Ain't Gonna Need
It) philosophy, and thus has no dependencies, and has uncomplicated source.

It has only been tested on Ubuntu 11.04, and may not work on other platforms.


What it Does
------------
This script iterates over all of the git repositories you specify to it, 
and queries your commit messages out of the logs. For each repository
that has been worked on during the week, your commit messages are saved
to a specified directory on a per-project basis.

If run without a date, this script determines the date of the most recent
Monday, and only queries the git logs back to that date. The general
usage scenario for this script assumes that it's likely to be run once per
week at the end of the week, and should query back to the most recent
Monday. Thus, "git-weekly-report".

This script evolved (unsurprisingly) from my own needs. Every Friday
I send my employee a summary of my git commit logs on a per-project basis.
Assembling this information manually quickly became tedious though, and 
hence this script was born.


Configuration
-------------
The script is configured by editing it directly; it does not rely on any
external configuration files.

There are only a few points of configuration for this script:

* log_save_path - The location to which you'd like to save the log files.
* author - Your name, according to git (as in: git config --global user.name)
* projects - This is a hash of the projects you want to have monitored.
For each project, you will need to specify a project name (which will be
used for naming the resultant log files) and the path to the repository.


Use
---
Frequently, you'll likely just invoke the script with no parameters, as in:

./git-weekly-report

Optionally, you may invoke the script with one parameter: the date back to which
you'd like to query, as in:

./git-weekly-report "1 Nov 2011"

That parameter is useful if you want to query farther back than simply one
week.


Contacting Me
-------------
If you have questions, concerns, bug reports, feature requests, offers
for discount viagra, whatever, feel free to contact me at chris@chris-allen-lane.com


License
-------
This product is licensed under the GPL 3 (http://www.gnu.org/copyleft/gpl.html).
It comes with no warranty, expressed or implied.
