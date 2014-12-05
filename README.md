githubfs
========

Java Nio FileSystem for accessing github.

Accessing a github repository is very simple:
```
Path root = Paths.get(URI.create("github:gnodet/githubfs?revision=master!/"));
```

The uri syntax is the following:
```
github:[login[:password]@]user/repository[?params][!/[path]]
```

Where
```
| Name       | Description                                              |
|------------|----------------------------------------------------------|
| login      | the login to access github                               |
| password   | the password to authenticate                             |
| user       | the github user or organization                          |
| repository | the repository name                                      |
| path       | the file or directory in the repository                  |
| params     | additional connection parameters with a uri query syntax |
| oauth      | the oauth token to use                                   |
| revision   | the revision of the repository to use                    |
```

The `login`, `password` and `oauth` token will also be loaded as defaults from the `~/.github` property file if it exists.
If a `login` has been provided in the uri, the `login` in the configuration file must match.
