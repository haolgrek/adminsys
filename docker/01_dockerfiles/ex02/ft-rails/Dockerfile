FROM ruby:2.5

RUN apt-get update && \
apt-get install -y nodejs &&\
gem install rails -v 5.2.1 &&\
mkdir -p /opt/app

ONBUILD WORKDIR /opt/app
ONBUILD ADD . /opt/app
ONBUILD EXPOSE 3000

ONBUILD RUN rvm all do bundle install
ONBUILD CMD rvm all do bundle exec rails server
