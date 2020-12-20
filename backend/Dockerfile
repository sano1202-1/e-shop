FROM ruby:2.5.3

RUN apt-get update -qq && apt-get install -y nodejs mysql-client
RUN mkdir /e-shop
WORKDIR /e-shop
COPY Gemfile /e-shop/Gemfile
COPY Gemfile.lock /e-shop/Gemfile.lock
RUN bundle install
COPY . /e-shop

COPY entrypoint.sh /usr/bin/
RUN chmod +x /usr/bin/entrypoint.sh
ENTRYPOINT ["entrypoint.sh"]

EXPOSE 3000

CMD ["rails", "server", "-b", "0.0.0.0"]
