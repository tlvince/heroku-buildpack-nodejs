# Wintersmith Build Pack

The Wintersmith build pack will look for two files in the app root:

    .
    ├── Makefile
    └── Procfile

The first stage of the compilation is identical to that of a default [Node.js][]
build. `node_module` binaries are then added to the path and the site generated
using a `heroku` task in the `Makefile`.

## Usage

Add this build pack to your `BUILDPACK_URL`.

    heroku config:add BUILDPACK_URL="https://github.com/tlvince/heroku-buildpack-wintersmith.git#wintersmith"

Or, with a recent version of the heroku gem, set it at creation time:

    heroku create --stack cedar --buildpack https://github.com/tlvince/heroku-buildpack-wintersmith.git#wintersmith

Then create a `Makefile` task with the command used to build the site:

    heroku:
      wintersmith build site

## Examples

Further example `Procfile` and `Makefile`s can be found in my [portfolio
project][p].

  [p]: https://github.com/tlvince/portfolio
  [node.js]: https://github.com/heroku/heroku-buildpack-nodejs
