# Overview

Several IETF working groups are using github to help progress their work.  The
[GitHub Integration and Tooling](https://datatracker.ietf.org/group/git/about/)
working group has developed a set of requirements for tooling to support that
work. Among them is [providing a publicly-accessible backup and
archive](https://tools.ietf.org/html/draft-ietf-git-github-wg-configuration-06#section-3.2)
of the information captured in each working group's github repositories. Note
that this includes each repository's issues and pull requests in addition to
content stored as code.

Respondents are expected to be familiar with
* [draft-ietf-git-github-wg-configuration](https://datatracker.ietf.org/doc/draft-ietf-git-github-wg-configuration)
* [draft-ietf-git-using-github](https://datatracker.ietf.org/doc/draft-ietf-git-using-github)

# Deliverables

1. A utility that creates a backup of a given set of github repositories, including the code repository, issues, and pull requests. It is expected that this utility will be based on the backup APIs provided by github, possibly levaraging open source tools such as [python-github-backup](https://github.com/josegonzalez/python-github-backup). This utility will be configurable with:
   1. A URL from which to retrieve the set of repositories to backup.
   1. A filesystem path identifying the root of the backup structure created.

1. A web-based utility that provides public read-only access to the backup.  Providing access via other mechanisms (such as rsync) is also desirable. At a minimum, it should be possible to make a git clone of the code in a given backup of a repository using normal git mechanisms.

1. A utility that will restore a backup to a given location. The deliverable should include tests demonstrating successful restores to github and to a test gitlab instance.
