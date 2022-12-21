# Buildroot

> Buildroot configuration to build a v86 compatible minimal Linux system containing MySQL

## Getting started

The goal of this build process is to produce a `filesystem` folder containing a full Linux filesystem that will be mounted and served by v86

1. Build and run the container to execute Buildroot

```bash
./build.sh
```

  1.1. If you need to refresh the Buildroot configuration files from the host, execute this command [OPTIONAL]:

  ```bash
  cp -r /config/* /config/.config .
  ```

  1.2. Tweak the configuration and save it back to the host [OPTIONAL]:

  ```bash
  # Linux system config
  # Launch menuconfig
  make menuconfig
  # Save the changes back to the host
  cp .config /config/.config

  # Linux kernel config
  # IMPORTANT: If it's the first time you run this command,
  # exit the linux-menuconfig when it opens and copy the host file by running
  # cp /mysql-wasm/board/mysql-wasm/linux.conf ./output/build/linux-5.17.15/.config
  # then you can go back to "make linux-menuconfig" to edit this configuration
  # Launch menuconfig
  make linux-menuconfig
  # Save the changes back to the host
  cp output/build/linux-5.17.15/.config /config/board/mysql-wasm/linux.conf
  ```

2. Build the `filesystem` folder:

```bash
make
```

(At this point you can go for a walk, it will take a bit of time.)

The `filesystem` folder should be available on the host at `build/filesystem`

## Notes
When you build a filesystem using a Mac with Apple M1 chip, it fails with Kernel Panic at boot time.
