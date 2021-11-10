FROM python:3.10

ENV APP_HOME /app
WORKDIR $APP_HOME

RUN apt-get update \
  && apt-get install -y locales-all

ENV LANG ja_JP.UTF-8
ENV LANGUAGE ja_JP:ja
ENV LC_ALL ja_JP.UTF-8

COPY . .

RUN curl -sSL https://raw.githubusercontent.com/python-poetry/poetry/master/install-poetry.py | python -
ENV PATH /root/.local/bin:$PATH
RUN poetry install
