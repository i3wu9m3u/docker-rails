FROM ruby:2.6.5

ARG TZ

RUN curl -sL https://deb.nodesource.com/setup_12.x | bash - && \
    apt update -q && \
    apt install -y \
        build-essential \
        libpq-dev \
        nodejs \
        vim && \
    rm -rf /var/lib/apt/lists/*

ENV APP_ROOT /webapp
WORKDIR $APP_ROOT
COPY ./src/Gemfile* ./

RUN bundle install

# puma.sockを配置するディレクトリを作成
RUN mkdir -p /tmp/sockets
