
# seebz/php-node-cli

Provides [PHP][], [Composer][] and [Node.js][] in a single image.


## Included binaries

The following binaries are available through this image:

- `php`
- `composer`
- `node`
- `npm`
- `npx`


## Parent images

| Tag    | PHP                | Composer        | Node.js             |
|:------:|--------------------|-----------------|---------------------|
| latest | php:cli-alpine     | composer:latest | node:current-alpine |
| 8      | php:8-cli-alpine   | composer:latest | node:current-alpine |
| 8.1    | php:8.1-cli-alpine | composer:latest | node:current-alpine |
| 8.0    | php:8.0-cli-alpine | composer:latest | node:current-alpine |
| 7      | php:7-cli-alpine   | composer:latest | node:current-alpine |
| 7.4    | php:7.4-cli-alpine | composer:latest | node:current-alpine |


## Dockerfiles

The Dockerfiles used to build this image are available on my [GitHub repository][GitHub].


[PHP]:      https://php.net/
[Composer]: https://getcomposer.org/
[Node.js]:  https://nodejs.org/
[GitHub]:   https://github.com/seebz/dockerfiles
