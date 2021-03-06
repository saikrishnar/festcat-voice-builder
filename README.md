# FestCat Voice Builder

This set of Makefiles and templates have been written to ease the building 
of [HTS](http://hts.sp.nitech.ac.jp/) voices in Catalan for the [FestCat](http://www.talp.cat/festcat) project.

It also supports builing HTS voices based on the [ARCTIC](http://festvox.org/cmu_arctic/) dataset.

This Makefiles and templates can be extended to support building of HTS voices 
in other languages.

# Dependencies

## Dependencies which you need to install

Some dependencies are not installed automatically:

1. General utilities such as:
   - C, C++ compilers
   - make
   - autoconf
   - grep, awk, sed
   - sox
   - perl
   - csh

2. I also needed the Debian package `libx11-dev` to build HTS and *maybe?* tcl-snack. Sorry for not providing more details.

## Language independent tools automatically downloaded, built and run

The following software is not language specific and is downloaded to the `deps` directory, 
compiled and installed automatically to the `tools` directory.

1. [Speech Tools 2.4-release](http://festvox.org/packed/festival/)
2. [Festival 2.4-release](http://festvox.org/packed/festival/)
3. [SPTK 3.8](http://sourceforge.net/projects/sp-tk)
4. [HTS-2.3beta](http://hts.sp.nitech.ac.jp/) for [HTK-3.4.1](http://htk.eng.cam.ac.uk/) (downloading HTK requires a [user and password](http://htk.eng.cam.ac.uk/register.shtml), as well as agreeing to the [non-free license](http://htk.eng.cam.ac.uk/docs/license.shtml))
5. [HDecode 3.4.1](http://htk.eng.cam.ac.uk/) (it has similar restrictions to HTK)
6. [hts_engine 1.09](http://sourceforge.net/projects/hts-engine)


## Language specific tools

Any language specific tool should be installed automatically from the Makefile available in
data/$lang.

### Catalan

This is downloaded automatically:

 - upc_ca_base (also known as festival-ca in some GNU/Linux distributions)
 - raw recordings and utt files.

### English

This is downloaded automatically:

 - festlex_CMU and festlex_POSLEX
 - recordings and utt files from ARCTIC dataset.

# Usage

Training Catalan voices may take several days, some GB of Hard disk and a lot of RAM.

In order to train HTS voices, run:

    ./configure htk_user="yourhtkuser" htk_password="yourhtkpassword"
    make ca_ona.spk
    make ca_bet.spk
    make ca_pau.spk
    make en_slt.spk
    make en_awb.spk


