# What is this?

Building stack applications for arm64 is literaly the most painful thing ever.

The bighest use case for this is raspberry pi. :)

Use script [build.sh](build.sh) to build the stack application for arm64.

# Dependencies

- Docker
- qemu
- binfmt-support
- qemu-user-static

# How to use?

First install the dependencies:

```bash (once per machine)
sudo apt-get install qemu binfmt-support qemu-user-static
```

Then (once per machine)
```bash
docker run --rm --privileged multiarch/qemu-user-static --reset -p yes
```

Finally you can build the application:

```
./build.sh
```

# Problems

I am currently working on a fix how to not compile libraries every time you build the application.

# References

- https://www.stereolabs.com/docs/docker/building-arm-container-on-x86/