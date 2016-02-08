This is ncp, but with some added cli functionality.

`--source` and `--dest` can be used to provide the source and dest files at any position in the arguments.  For my purposes, I wanted to put --source as the last thing on the command line, so that I could use NPM's [--](https://docs.npmjs.com/cli/run-script) feature and pass in an on the fly source file to copy to a static location without having to type out the full copy command each time.  $npm_package_config_etc would have worked, except it is platform specific, as windows uses % signs.

Also, I needed the ability to not clobber, and only copy files if they are newer, so I added in the --noclobber and --modified options to the CLI.

## TBD
I also updated the CLI arg parser to use nopt, and in the process I dropped support for `--limit`, `--filter`, and `--stopOnError`.  This would be easy to add back in but I didn't need them for my case.
