FROM node:10.15-alpine

RUN mkdir -m 755 /app

COPY . /app/

WORKDIR /app

RUN yarn install

CMD sh -c 'if [ "${WATCH}" = "1" ]; then yarn watch; else yarn test; fi'
