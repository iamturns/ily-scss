I Love You SCSS - Contributing
==============================

Publish
-------

- Follow `[unreleased]` link at bottom of `CHANGELOG.md`
- Summarise changes at top of `CHANGELOG.md` (refer to http://keepachangelog.com)
- Decide on a new version number based on unreleased changes (refer to http://semver.org)
- Within `CHANGELOG.md`
    - Create duplicate `[unreleased]` block
    - Change second `[unreleased]` block to version number and release date
    - Create new version link at bottom of file
- Update version number in `src/_ily.scss`
- Commit changes, see example:

```
git add -A
git commit -m "v0.0.1"
git push
git tag -a v0.0.1 -m "v0.0.1"
git push --tags 
```
