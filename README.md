# @intrnl/yarn

Patched version of [Yarn 1.x][yarn-v1-repo]

### Hardlinked install

Yarn stores extracted versions of packages on its global cache directory, and
then copies the extracted files to your project folder.

Rather than doing a copy, we made it so that it would try to hardlink the file,
giving you considerable storage savings if you're working with multiple project
with the same kind of dependencies.

This does not work the same way as `pnpm` however where it uses a CAS, you can
get relatively the same amount of saving by running [dupe-krill][dupe-krill] on
the cache directory. Caution is advised.


[yarn-v1-repo]: https://github.com/yarnpkg/yarn
[dupe-krill]: https://github.com/kornelski/dupe-krill
