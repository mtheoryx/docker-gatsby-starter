# Docker Gatsby Starter

Using the gatsby-cli generator for a new site from the default starter
usually looks like this:

```bash
gatsby new .
```

This is in ideal conditions and presents a few issues that this image
can help with.

## Usage

```bash
d pull mtheoryx/gatsby-docker-base:1.0.0
d create --name gatsby-starter gatsby-docker-base
d cp gatsby-starter:/usr/app/. ./public-site
dct rm gatsby-starter
```

## Motivation

- No need to install gatsby globally
- No need for yarn or npm or npx or even Node
- No need for GIT
- Only Requires Docker installed

## Detailed Explanation

The end result you need to get going is just the files from a starter. This image, and the above commands, will get you there with zero frustration.

The image is only slightly bigger than the Apline Node image due to the
multistage Docker build strategy.

After this image is pulled, you can create a container from it. The
container won't be running, and if you have the alpine node version
already pulled, that will be cached and the image pull will be even faster
for you, thanks Docker!

After you create this container, which is not running, you can simply
copy files from it onto your host machine, destroy the container, forget about this whole thing, and be on your merry way making awesome Gatsby Stuff!
