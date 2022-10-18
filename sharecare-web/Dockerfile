FROM node:12-alpine

ENV PORT=80 

# Metadata as defined in OCI image spec annotations - https://github.com/opencontainers/image-spec/blob/master/annotations.md
LABEL org.opencontainers.image.title="Title_Here" \
      org.opencontainers.image.description="Description_Here" \
      org.opencontainers.image.authors="Authors_Here" \
      org.opencontainers.image.vendor="Vendor_Here"

# add debugging utilities
RUN apk --no-cache add \
  curl \
  ca-certificates \
  jq \
  less \
  vim

# bundle app and install dependencies 
COPY . /app
WORKDIR /app
RUN npm install

# run application
EXPOSE $PORT
CMD npm start
