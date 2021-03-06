---
title: "February 2020"
date: 2020-02-07
draft: false
weight: 91
---

## Week 6

Both Packit and Packit Service pre-commit hooks [were][1] [updated][2] to include
[prettier] and [setup-cfg-fmt], in order to have a more consistent formatting of
markup, YAML, JSON and `setup.cfg` files.

It became easier for developers to [build the Packit base image] locally, and
tests in Zuul [were configured] to run on Fedora 31.

Packit learned [how to look for RPM spec files on its own], so specifying
`specfile_path` in the configuration is not mandatory anymore. Packit will
recursively search the tree and use the first spec file found.

The Redis pod in Packit Service uses an up to date image now, [based on Fedora 31].
Kudos to [hhorak] for the help!

[1]: https://github.com/packit-service/packit/pull/697
[2]: https://github.com/packit-service/packit-service/pull/383
[prettier]: https://github.com/prettier/prettier
[setup-cfg-fmt]: https://github.com/asottile/setup-cfg-fmt
[build the packit base image]: https://github.com/packit-service/packit/pull/695
[were configured]: https://github.com/packit-service/packit/pull/694
[how to look for rpm spec files on its own]: https://github.com/packit-service/packit/pull/634
[based on fedora 31]: https://github.com/packit-service/deployment/pull/51
[hhorak]: https://github.com/hhorak

## Week 7

The default configuration generated by Packit has [test jobs enabled] from now
on. This should simplify configuring Packit in new repositories.

[Fixed a bug] which was causing SRPM-build failures in Packit Service for projects
which had their spec files stored in a subdirectory.

As a result of [keys.fedoraproject.org] being turned off, Packit now [tries] a
list of GPG keyservers when downloading keys to check commit signatures.

When enabling Packit Service for new GitHub repositories, instead of checking
if the requester is a Fedora packager, we'll check if they [signed the Fedora
Project Contributor Agreement].

While proposing an update to Fedora, Packit Service will [report a failure] now
when there are no releases found in the upstream GitHub repository.

Test results became [serializable], we will not block when [no test results
are received], and Packit Service received [some initial code] to enable using
PostgreSQL as a data backend.

[test jobs enabled]: https://github.com/packit-service/packit/pull/703
[fixed a bug]: https://github.com/packit-service/packit/pull/698
[tries]: https://github.com/packit-service/packit/pull/699
[keys.fedoraproject.org]: https://lists.fedoraproject.org/archives/list/devel@lists.fedoraproject.org/message/COEYWJBQDAWRSYNQW7Y7TD2EKEGBWOAY/
[signed the fedora project contributor agreement]: https://github.com/packit-service/packit-service/pull/403
[no test results are received]: https://github.com/packit-service/packit-service/pull/388
[some initial code]: https://github.com/packit-service/packit-service/pull/319
[report a failure]: https://github.com/packit-service/packit-service/pull/399
[serializable]: https://github.com/packit-service/packit-service/pull/391

## Week 8

Postgresql database was introduced in production environment to improve performance and enable implementation
of new features, e.g. storing logs to reduce amount of messages sent directly to pull request [(#406)], [(#420)].

Cleanup in configuration files was performed, so no longer needed values were removed from .packit.yaml [(#709)].
User experience was improved by adding new `--upstrem-ref` option to `copr-build` command in command-line interface [(#718)]
and making error reporting more robust by adding new fedpkg clones related error message [(#714)].

Following bugs were fixed:

- bug in copr-build command fixed [(#713)]
- get_local_package_config() duplicate entries in 'directories' bug fixed [(#715)]

[(#709)]: https://github.com/packit-service/packit/pull/709
[(#718)]: https://github.com/packit-service/packit/pull/718
[(#714)]: https://github.com/packit-service/packit/pull/714
[(#713)]: https://github.com/packit-service/packit/pull/713
[(#715)]: https://github.com/packit-service/packit/pull/715
[(#406)]: https://github.com/packit-service/packit-service/pull/406
[(#420)]: https://github.com/packit-service/packit-service/pull/420

## Week 9

### packit

- Dist-git patches are now applied in source-git repos with `-p1` to resolve an issue when they are generated with git and patch program fails to apply them [(#730)].
- Fedora 32 was added to 'fedora-all' and 'fedora-development' aliases [(#731)].
- We have put more links to our documentation (README, deprecation warning in packit) so that people can easily correct their configuration files [(#726)].

### packit-service

- `targets` key in copr job definition in the packit.yaml is no longer a required field (it defaults to `fedora-stable`) [(#431)].
- Builds are now correctly linked to their actual GitHub projects (this can be seen in the logs view) [(#441)].

[(#730)]: https://github.com/packit-service/packit/pull/730
[(#731)]: https://github.com/packit-service/packit/pull/731
[(#726)]: https://github.com/packit-service/packit/pull/726
[(#431)]: https://github.com/packit-service/packit-service/pull/431
[(#441)]: https://github.com/packit-service/packit-service/pull/441
