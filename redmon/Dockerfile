FROM ruby:2.3.1
MAINTAINER Christopher Young "krsyoung@gmail.com"

# Install apt based dependencies required to run Ruby as
# well as RubyGems. As the Ruby image itself is based on a
# Debian image, we use apt-get to install those.
RUN apt-get update -qq && \
  apt-get install -y -qq build-essential && \
  apt-get clean \
  && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# Install redmon dependencies
RUN gem install mixlib-cli eventmachine redis thin

# Install redmon from RubyGems
RUN gem install redmon

# Expose the default redmon port
EXPOSE 4567

# Set redmon as the entry point
ENTRYPOINT ["redmon"]
