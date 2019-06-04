# infra-upgrade

- Upgrade all of our debians nodes while taking care of holding local
  packages
- Commit changes to `/etc` before upgrading if needed
- Keep a list of upgraded packages with pre and post version in `/etc/upgraded/$DATE`
- Commit changes to `/etc` after upgrading if needed

# Setup

See [SETUP](SETUP.md)

# Usage

## First, hold local packages

```bash
apt-hold.yml -l "$pattern" -C
apt-hold.yml -e notfoundok=True -l "$pattern" -C
apt-hold.yml -e notfoundok=True -e show=True -l "$pattern"
```

- The default search expression for packages to put on hold is
  `?and(?maintainer(epiconcept), ?installed)`
- When option `notfoundok` is `True` it is not an error for the search
  result list to be empty
- Option `show` gives a list of currently held packages, a list of
  found packages matching search expression and the difference between
  held and found

## Then upgrade

```bash
apt-upgrade.yml -l "$pattern" -e show=True -DC
apt-upgrade.yml -l "$pattern" -e show=True -e com=True -D
```
