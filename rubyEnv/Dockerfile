FROM centos:centos8

LABEL maintainer="Akipon <test@test.com>"

# 必要なライブラリダウンロード
RUN yum update && yum install -y \
  sudo\
  git\
  make\
  bzip2\
  gcc\
  openssl-devel\
  readline-devel\
  zlib-devel\
  gcc-c++\
  sqlite-devel\
  mercurial\
  ncurses-devel

#rbenvクローン
RUN git clone https://github.com/sstephenson/rbenv.git ~/.rbenv
#rbenvのPATH登録
ENV PATH /.rbenv/bin:$PATH
#bash_profile更新
RUN source ~/.bash_profile
#ruby-buildクローン
RUN git clone https://github.com/sstephenson/ruby-build.git ~/.rbenv/plugins/ruby-build

RUN gem install bundle
RUN gem install rails
RUN gem install sassc -v '2.2.1' --source 'https://rubygems.org/'
RUN  install sqlite3 -v '1.4.2' --source 'https://rubygems.org/'
EXPOSE 80

