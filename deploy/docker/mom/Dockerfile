FROM node:20-alpine

RUN apk add --no-cache \
    bash git openssh-client \
    # node-gyp build tools
    python3 make g++ \
    # canvas native dependencies
    cairo-dev pango-dev jpeg-dev giflib-dev librsvg-dev pixman-dev \
    # pkgconfig needed by canvas build
    pkgconf

WORKDIR /repo

COPY entrypoint.sh /usr/local/bin/entrypoint.sh
RUN chmod +x /usr/local/bin/entrypoint.sh

ENTRYPOINT ["/usr/local/bin/entrypoint.sh"]
CMD ["sh","-lc","node -v && sleep infinity"]
