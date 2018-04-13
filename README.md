# makefile-go
Golang project/library based on Makefile

makefile-go temaplate has a bold assumption and convention like the followings: 
* Your project use [dep](https://github.com/golang/dep) 
* Your project have VERSION file as version origin
* Your project have tests and tests run in travis (and appveyour)
* README.md is generated from godoc (no more doc duplicity/mismatch)
* Your app project is released to github releases
* vendor dir is gitignored (vendor isn't commited - https://github.com/golang/dep/blob/master/docs/FAQ.md#should-i-commit-my-vendor-directory)
* run test with coverege (https://github.com/pierrre/gotestcover#deprecated)

## Project

### structure
* [appveyor.yml](appveyor.yml)
* [.gitignore](.gitignore)
* [.godocdown.tmpl](.godocdown.tmpl)
* [.goreleaser.yaml](.goreleaser.yaml)
* [Makefile](Makefile)
* [.travis.yaml](.travis_app.yaml)

### setup release
1. [generate github token](https://help.github.com/articles/creating-a-personal-access-token-for-the-command-line/)
2. `gem install travis`
3. `travis encrypt 'GITHUB_TOKEN=<YOUR_GITHUB_TOKEN>'`

### release
1. `make release` use content of [VERSION](VERSION) file to create new tag
2. travis-ci automatically build app and release it

## Library

### structure
* [appveyor.yml](appveyor.yml)
* [.gitignore](.gitignore)
* [.godocdown.tmpl](.godocdown.tmpl)
* [Makefile](Makefile)
* [.travis.yaml](.travis_library.yaml)

### release
1. `make release` use content of [VERSION](VERSION) file to create new tag
