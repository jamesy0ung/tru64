# Prerequisites
* Compaq C Compiler (http://osarchive.org/os/osf1-tru64/Development/Developers%27%20toolkit%20for%20Tru64%20UNIX/Compaq%20C%20V6.5-303.tar.lz)

## Licence Compaq C Compiler

Run lmfsetup

Enter the following details

           Product Name: OSF-DEV
               Producer: DEC
                 Issuer: DEC
   Authorization Number: NON-COMMERCIAL-TRU64-UNIX-4
        Number of units: 0
    Activity Table Code: CONSTANT=100
               Checksum: 2-ABBL-EDCP-AHFP-LKHO
               
When asked if you want to reset the lmf, answer yes

# Compile tar

 Download and copy to the system http://ftp.gnu.org/gnu/tar/tar-1.23.tar.gz
 
 gunzip tar-1.23.tar.gz 
 tar -xvf tar-1.23.tar 
 cd tar-1.23
 env CPPFLAGS=-I/usr/local/include LDFLAGS=-s FORCE_UNSAFE_CONFIGURE=1 ./configure
 make 
 make install

# Compile libiconv

 Download and copy to the system http://ftp.gnu.org/gnu/libiconv/libiconv-1.8.tar.gz
 
 tar xvf libiconv-1.8.tar.gz
 /usr/local/bin/tar -xvf libiconv-1.8.tar
 cd libiconv-1.8
 env CPPFLAGS=-I/usr/local/include LDFLAGS=-s ./configure
 make
 make install
 
 # Compile gmp
 
 Download and copy to the system http://ftp.gnu.org/gnu/gmp/gmp-5.0.5.tar.bz2
 
 bunzip2 gmp-5.0.5.tar.bz2
 /usr/local/bin/tar -xvf gmp-5.0.5.tar
 cd gmp-5.0.5
 env CPPFLAGS=-I/usr/local/include LDFLAGS=-s ./configure
 make
 make install
 
 # Compile MPFR
 
 Download and copy to the systemhttp://mpfr.loria.fr/mpfr-2.4.2/mpfr-2.4.2.tar.gz
 
 gunzip mpfr-2.4.2.tar.gz
 /usr/local/bin/tar -xvf mpfr-2.4.2.tar
 cd mpfr-2.4.2
 env CPPFLAGS=-I/usr/local/include LDFLAGS=-s ./configure
 make
 make install
 
 # Remove old gmake
 
 rpm -e gmake
 
 # Compile GNU Make
 
 Download and copy to the system http://ftp.gnu.org/gnu/make/make-3.80.tar.gz
 
 gunzip make-3.80.tar.gz
 /usr/local/bin/tar -xvf make-3.80.tar
 cd make-3.80
 env CPPFLAGS=-I/usr/local/include LDFLAGS=-s ./configure
 make
 
 # Append the following to /etc/sysconfigtab
 
 proc:
 per_proc_stack_size = 33554432
 per_proc_data_size = 801326592
 
 # Compile GCC

 Download and copy to the system http://ftp.gnu.org/gnu/gcc/gcc-4.4.7/gcc-4.4.7.tar.gz

 mkdir /usr/gcc
 gunzip gcc-4.4.7.tar.gz
 /usr/local/bin/tar -xvf gcc-4.4.7.tar.gz
 cd gcc-4.4.7
 ./configure --prefix=/usr/gcc --enable-threads=posix --disable-nls --enable-languages=c,c++ --without-gnu-ld --with-ld=/usr/ccs/bin/ld --without-gnu-as --with-as=/usr/bin/as --disable-libssp --with-libiconv-prefix=/usr/local --with-gmp=/usr/local --with-mpfr=/usr/local
 /usr/local/bin/make
 /usr/local/bin/make install

 # Precompiled GCC
 I have precompiled this and uploaded it.
 
 
