centos_kernel_builder is a helper script for building CentOS Stream and RHEL
kernels. It supports GA (initial release), y-stream (minor update), and
z-stream (maintenance update) workflows. The script can clone kernel sources,
prepare for backporting, configure kernels, apply patches, build kernel images,
optionally build RPMs, and generate initramfs images.

Two environment variables must be set before use:
  KERNEL_SRC_DIR
  KERNEL_BUILD_DIR

Basic examples:

# Clone the repo, prepare for backporting, configure, and build a debug kernel
$ centos_kernel_builder -a aarch64 -s y10 -g -B \
                        -f myfork:main -c -d -b

# Rebuild using existing configuration
$ centos_kernel_builder -a aarch64 -s y10 -d -b

# Clean, configure, and rebuild
$ Centos_kernel_builder -a aarch64 -s y10 -c -d -b

Run 'centos_kernel_builder -h' for full usage details.
