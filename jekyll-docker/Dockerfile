FROM ruby:latest
RUN git clone https://github.com/endymuhardin/endymuhardin.github.io.git /opt/website
WORKDIR /opt/website
RUN bundle install
CMD ["jekyll", "serve", "--host=0.0.0.0", "--unpublished", "--drafts", "--future", "--watch"]
EXPOSE 4000

