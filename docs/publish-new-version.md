Publish a new version
=====================

- Within `CHANGELOG.md`
    - Follow `[unreleased]` link at the bottom
    - Summarise changes beneath `Unreleased` heading at top
        - Refer to [keepachangelog.com](http://keepachangelog.com) 
    - Decide on a new version number based on unreleased changes
        - Refer to [semver.org](http://semver.org)
    - Create duplicate `Unreleased` heading, ready for the next unreleased features
    - Change second `Unreleased` heading to new version number and release date
    - Update the version number in the `[Unreleased]` link at the bottom
    - Add a new version link below it
- Update version number in `src/_ily.scss`
- Update version number in GitHub download links within `README.md` file
- Commit changes, see example:

```
git add -A
git commit -m "v0.0.1"
git tag -a v0.0.1 -m "v0.0.1"
git push origin master v0.0.1
```
