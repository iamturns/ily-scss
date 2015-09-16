I Love You SCSS - Contributing
==============================

Publish
-------

- Find the existing version number in `src/_ily.scss`
- Decide on a new version number based on unreleased changes (refer to http://semver.org)
- Update the new version number in `src/_ily.scss`
- Commit changes, see example:

```
git add -A
git commit -m "Prepare version 0.0.1"
git push
git tag -a v0.0.1 -m "Version 0.0.1"
git push --tags 
```
