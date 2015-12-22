FROM ruby:2.2
MAINTAINER kohey

ADD app.rb app.rb
RUN gem install sinatra

EXPOSE 4567
CMD ["ruby", "app.rb"]


