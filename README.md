# Lifting and Diversifying C++ Binaries

This repository accompanies the [Trail of Bits blog post](https://blog.trailofbits.com/2018/09/10/protecting-software-against-exploitation-with-darpas-cfar/) discussing how to use mcsema with Immunant's multicompiler to lift and diversify binaries.

# The Example Program

The sample program uses stack variables, global variables, and C++ exceptions to showcase features of both McSema and the multicompiler.

# Prerequisites

Please install Immunant's multicompiler as [described in their blog post](https://immunant.com/blog/2018/09/multicompiler/).

To install McSema, please follow the [McSema installation instructions](https://github.com/trailofbits/mcsema/blob/master/README.md).

The version of remill and mcsema installed must be built against LLVM 3.8 (to match the multicompiler) and include ABI library support.

The following invocation of remill's `build.sh` should give the correct remill and McSema builds:
```sh
scripts/build.sh --llvm-version 3.8 --prefix <your installation location> --extra-cmake-args -DMCSEMA_DISABLED_ABI_LIBRARIES:STRING=\"\"
```
Currently the variable recovery scripts require IDA Pro.

# Further Reading

* The [Trail of Bits blog post](https://blog.trailofbits.com/2018/09/10/protecting-software-against-exploitation-with-darpas-cfar/) discussing using McSema with the multicompiler.
* The Immunant blog post showing how to install and use the multicompiler.
* The [Galois blog post](https://galois.com/blog/2018/09/protecting-applications-with-automated-software-diversity/) showing how McSema and the Multicompiler fit together into a larger project.
