# Supported tags and respective `Dockerfile` links

- [`latest` (latest/Dockerfile)](https://github.com/punimeister/docker-jest/blob/master/latest/Dockerfile)

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
