# GMAD Docker image

This image includes a static build of GMAD, the GMod Addon creation and
extraction tool that is usually shipped with Garry's Mod.
The entrypoint is configured to point directly at the binary so it is possible
to use `docker run` on this image just as if you would use GMAD directly on your
system.

## Available tags

All available tags are always listed [in Docker Hub](https://hub.docker.com/r/icedream/gmad/tags),
the list below explains the maintained tags:

- `latest`, `1`, `1.1`: Latest stable version.

## Examples

### Creating an addon

Creating an addon from the current directory and saving the newly generated
add-on file to `example.gma`:

    docker run --rm -it -v "$(pwd):/src" -w /src icedream/gmad \
        create -folder . -out example.gma

### Extracting an addon

Extracting an addon `example.gma` to the current directory:

    docker run --rm -it -v "$(pwd):/src" -w /src icedream/gmad \
        extract -file example.gma -out .
