FROM ruby:latest
RUN git clone https://github.com/endymuhardin/endymuhardin.github.io.git /opt/website
WORKDIR /opt/website
RUN bundle install
CMD ["jekyll", "serve", "--host=0.0.0.0", "--unpublished", "--drafts", "--future", "--watch"]
EXPOSE 4000

# docker build -t website-endy .
# docker run -itd -p 4000:4000 website-endy
# docker ps -a
# docker cp new_post.md container_id:/opt/website/_posts/