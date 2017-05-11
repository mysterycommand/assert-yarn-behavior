# Assert Yarn Behavior
>Just trying to suss out how Yarn works with a little experiment.

## A Clean Start
This repo now contains just the test packages (in the packages folder as `@test/foo`, `@test/bar`, and `@test/baz`, all at v1.0.0) and a `tmp` folder (used by `npm-register` to store the `htpasswd` file, `auth_tokens` (ignored), package info, and tarballs).

#### Here's what I'm running:
```bash
$ node --version
v6.10.3
$ npm --version
3.10.10
$ yarn --version
0.23.4
```

## Getting Started
In order to set this test up, you'll need to install [`npm-register`](https://github.com/dickeyxxx/npm-register) globally. Use _either_ (not both) of the following (I'm running v2.2.0 at time of writing):
```bash
$ yarn global add npm-register
```
Sometimes Yarn appears to have issues linking binaries. This might be related to switching Node versions with `nvm`? Anyway if you get `-bash: npm-register: command not found` you could try it the old fashioned way:
```bash
$ npm --global install npm-register
```

Once it's installed you can start it with (the `--always-https` flag is so that Yarn doesn't bark about non-https redirects, [more here](https://github.com/dickeyxxx/npm-register#yarn-compatibility), but I think they actually fixed this on the Yarn side, so maybe you don't need it):
```bash
$ npm-register start --always-https
```

With your local registry running at `http://localhost:3000/` you should be able to:
```bash
$ npm login --registry=http://localhost:3000/
Username: test
Password: test
Email: (this IS public) test@test.com
Logged in as test on http://localhost:3000/.
$ npm whoami --registry=http://localhost:3000/
test
```


