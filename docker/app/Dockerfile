FROM ruby:3.1.0

ARG TZ

RUN curl -sL https://deb.nodesource.com/setup_12.x | bash - && \
    apt update -q && \
    apt install -y \
        build-essential \
        libpq-dev \
        nodejs \
        yarn \
        vim && \
    rm -rf /var/lib/apt/lists/*

ENV APP_ROOT /webapp
WORKDIR $APP_ROOT
COPY ./src/Gemfile* ./

RUN bundle instal
#RUN yarn install --check-files
#RUN bundle exec rails webpacker:compile

# puma.sockを配置するディレクトリを作成
RUN mkdir -p /tmp/sockets
