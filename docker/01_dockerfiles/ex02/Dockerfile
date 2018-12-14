FROM ruby:2.3.0

RUN apt-get update -y && apt-get upgrade -y
RUN gem install rails
RUN apt-get install nodejs -y

ONBUILD COPY . /opt/app

ONBUILD WORKDIR /opt/app

ONBUILD RUN bundle install && rake db:migrate && \
rake db:seed

# docker build -t ft-rails:on-build .
# docker build -t test ~/42/test/railsapp
# docker run -it --name appppp -p 3000:3000 test
