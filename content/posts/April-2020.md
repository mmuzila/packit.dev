---
title: "April 2020"
date: 2020-04-03
draft: false
weight: 89
---

## Week 14 (March 30th - April 3rd)

### packit

- Fix web URLs for Copr builds owned by groups [(#778)].
- Create downstream spec if it's not there (propose-update) - this used to happen when using packit on a newly created package in Fedora which did not have spec fille added yet. [(#779)]
- Packit no longer inspects archive extension set in `Source` and creates `.tar.gz` by default - this should be more flexible and prevent issues for "non-standard" archive names. [(#781)]

### packit-service

- Several fixes and improvements after switching data store from Redis to PostgreSQL.
- Use the configured COPR project when triggering Testing Farm (tests no longer fail for projects which are built in their own COPR namespace) [(#524)].

[(#778)]: https://github.com/packit-service/packit/pull/778
[(#779)]: https://github.com/packit-service/packit/pull/779
[(#781)]: https://github.com/packit-service/packit/pull/781
[(#524)]: https://github.com/packit-service/packit-service/pull/524

## Week 15 (March 6th - April 9th)

### packit

- [Tomáš] finished teaching `packit srpm` to [linearise extremely complex Git
  histories], in order to get patches that can be applied when building the
  SRPM.
- [Jirka] made the schema validation code [Marshmallow3 compatible]. This
  enables building `packit` in Fedora 32 and Rawhide.

### packit-service

- [Franta] fixed an issue with [parsing release events].
- [Jirka] made code [Marshmallow3] compatible in this project, too.

[tomáš]: https://github.com/TomasTomecek
[jirka]: https://github.com/jpopelka
[franta]: https://github.com/lachmanfrantisek
[linearise extremely complex git histories]: https://github.com/packit-service/packit/pull/766
[marshmallow3 compatible]: https://github.com/packit-service/packit/pull/775
[marshmallow3]: https://github.com/packit-service/packit-service/pull/538
[parsing release events]: https://github.com/packit-service/packit-service/issues/536

## Week 16 (April 14th - April 17th)

### packit & packit-service

- Job metadata field `dist-git-branch` is now marked as deprecated, to be
  replaced by `dist_git_branches` to match the naming of other metadata fields
  and to accept multiple branch names where Packit should work. ([#797],
  [#788] and [#564]).
- A great deal of refactoring, CI work and general code improvements which
  will make Packit and Packit Service run smoother and development easier.

[#797]: https://github.com/packit-service/packit/pull/797
[#788]: https://github.com/packit-service/packit/pull/788
[#564]: https://github.com/packit-service/packit-service/pull/564

## Week 17 (April 20th - April 24th)

### packit-service

In this week we mostly focused on CentOS Stream and
some under the hood improvements,
none of which are available for Github projects.

- [Jano] did a lot of work on [initial CentOS Stream integration].
- [Hunor] added a Pagure build status reporting.
- [Anchit] added first API tests and improved build statuses given by the API.
- [Laura] and [Rishav] improved how data about Copr builds are stored in our db.

[anchit]: https://github.com/IceWreck
[hunor]: https://github.com/csomh
[jano]: https://github.com/sakalosj
[laura]: https://github.com/lbarcziova
[rishav]: https://github.com/rishavanand
[initial centos stream integration]: https://github.com/packit-service/packit-service/pull/515

## Week 18 (April 27th - April 30th)

### packit-service

- [Franta] did a great deal of service & worker refactoring related to CentOS ([#586])
  and to forks usage in Github. ([#589])
- [Hunor] fixed confusing Github status messages while building in Copr. ([#588])

[#586]: https://github.com/packit-service/packit-service/pull/586
[#588]: https://github.com/packit-service/packit-service/pull/588
[#589]: https://github.com/packit-service/packit-service/pull/589
