# Jung Hae Sung's Blog

# WSL(Ubuntu)을 위한 설정

Ruby 설치 (2.5.0 이상, `ruby -v`로 버전 확인)

```
$ sudo apt-get update
$ sudo apt-get install ruby-full
```

Gem 설치 (`gem -v`)

```
$ sudo gem update --system
```

gcc, g++

```
$ sudo apt install gcc
$ sudo apt install g++
```

Jekyll, Bundler 설치

```
$ sudo apt-get install ruby-full build-essential zlib1g-dev
$ sudo gem install jekyll bundler
```

# 빌드

```
$ bundle
$ bundle exec jekyll s
```

또는 (for auto reload)

```
$ bundle exec jekyll s --force_polling --livereload
```
