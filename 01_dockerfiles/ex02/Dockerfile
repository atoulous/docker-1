FROM ruby

RUN apt-get update \
	&& apt-get install -y nodejs \
	&& gem install rails

ONBUILD COPY . ./opt/app
ONBUILD WORKDIR /opt/app

ONBUILD RUN bundle install
ONBUILD RUN rails db:migrate
ONBUILD RUN rake db:setup
ONBUILD RUN rake db:seed
