
as seen previpously in building [[launch cuttelfish emulator]] 


Now that we have gotten Cuttlefish running, it’s time to explore one of the main reasons that I use it, which is validating Android kernels. Android has cool technologies in the kernel such as LTO and CFI, which are not currently in mainline. Replacing Cuttlefish’s prebuilt kernel is extremely easy, which is one of the main selling points; it makes it really easy for kernel hackers to get involved with it, especially with Google’s kernel build system. This section is expanded from Google’s official documentation.

First, we need to do is grab repo, Google’s git management tool. If you already have repo installed, just skip this portion. Alternatively, you can install repo into /usr/local/bin so that it is automatically added to PATH but for the sake of this tutorial, I keep everything localized as much as possible.

### Create a bin folder within the Cuttlefish area
`mkdir -p "${HOME}"/cuttlefish-playground/bin

