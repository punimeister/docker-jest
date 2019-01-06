# punimeister/jest

[![Docker Stars](https://img.shields.io/docker/stars/punimeister/jest.svg)](https://hub.docker.com/r/punimeister/jest/)
[![Docker Pulls](https://img.shields.io/docker/pulls/punimeister/jest.svg)](https://hub.docker.com/r/punimeister/jest/)
[![Docker Automated](https://img.shields.io/docker/automated/punimeister/jest.svg)](https://hub.docker.com/r/punimeister/jest/)
[![Docker Build](https://img.shields.io/docker/build/punimeister/jest.svg)](https://hub.docker.com/r/punimeister/jest/)

## Source Code

### [jest:latest](https://github.com/punimeister/docker-jest/tree/master/latest)

## Environment Variables

### `WATCH`

When set to 1 enable to watch mode

## Example

### Directory structure

```
.
├── docker-compose.yml
└── web
    └── src
        └── js
            ├── add.js
            └── add.spec.js
```

### docker-compose.yml

```
version: '3'

services:

  jest:
    image: 'punimeister/jest'
    restart: 'on-failure'
    environment:
      WATCH: '0'
    volumes:
      - './web:/app/web:ro'
```

### add.js

```
export const add = (a, b) => a + b;
```

### add.spec.js

```
import { add } from './add';

test('1 + 1 = 2', () => {
  expect(add(1, 1)).toBe(2);
});
```
