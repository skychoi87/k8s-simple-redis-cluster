# Alpine with ruby support image
FROM redis

# Copy redis-trib.rb
# chmod +x redis-trib.rb
COPY redis-trib.rb /data/redis-trib.rb

# Copy redis.conf, port=7000, datadir=/data/
COPY redis.conf /usr/local/etc/redis/redis.conf

RUN apt-get update

# Install ruby
RUN apt-get install -y ruby

# Install gem redis plugin
RUN gem install --no-rdoc redis

CMD [ "redis-server", "/usr/local/etc/redis/redis.conf" ]

# Run command below to build the image
# docker build -t redis-test .
# Run command below to run the container
# docker run -ti --rm redis-test /bin/bash
