# Assert Yarn Behavior
>Just trying to suss out how Yarn works with a little experiment.

Okay, so, I created these test packages, `@test/foo`, `@test/bar`, and `@test/baz`. All at `1.0.0`. I think what I need to do is `yarn add` each of these, and then bump one and make sure that other users running `yarn install` don't get a different `yarn.lock` file. Also, experiment with `--pure-lockfile` and `--frozen-lockfile`. Also, ensure that not only did the lock file not change, but that the dependency tree didn't change … so to that end, maybe use the `--modules-folder` so that we can just `tree whatever` and not get all the `npm-register` deps as well?

## How to Use
```bash
$ git clone git@github.com:mysterycommand/assert-yarn-behavior.git
$ cd assert-yarn-behavior/
$ npm install npm-register@2.2.0 # we don't want to yarn add/install here
$ yarn start # starts the npm-registry at localhost:3000
```

… then, in a separate tab/process/thread, I don't know … maybe like:
```bash
$ yarn add foo bar baz # ?
$ yarn --production # ?
```

Idk, that's all tbd I guess. What are the experiments, how do we assert results.
