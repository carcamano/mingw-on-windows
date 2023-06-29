# How to Install Mingw on Windows to use Libxml2 with Go Lang

## Step 1

Download files:
```
msys2-x86_64-20230127.exe
mingw-w64-x86_64-gcc-10.2.0-11-any.pkg.tar.zst
mingw-w64-x86_64-go-1.16-1-any.pkg.tar.zst
mingw-w64-x86_64-iconv-1.16-2-any.pkg.tar.zst
mingw-w64-x86_64-libxml2-2.9.10-8-any.pkg.tar.zst
```

## Step 2
Install:
```
msys2-x86_64-20230127.exe
```

## Step 3
Add Mingw dir to path:
```
C:\msys64\mingw64\bin
```

## Step 4
![image](https://github.com/carcamano/mingw-on-windows/assets/11354012/ee17920e-01b4-485c-a74a-eb068974cf85)

"MSYS2 UCRT64" should be auto open after instal, if you close it, reopen.

Switch to repo download directory, eg:
```
cd /c/Users/MyUser/Downloads/mingw-on-windows-master
```

Now run the following commands:
```shell
$ pacman -S mingw-w64-x86_64-gcc
$ pacman -S mingw-w64-x86_64-pkg-config
$ pacman -S mingw-w64-x86_64-go
$ pacman -U mingw-w64-x86_64-iconv-1.16-2-any.pkg.tar.zst
$ pacman -U mingw-w64-x86_64-libxml2-2.9.10-8-any.pkg.tar.zst
```

## Important Notes
This guide was created to simplify the installation of gcc, libxml2 and other dependencies for use in Golang together with the library https://github.com/jbussdieker/golibxml

The above mentioned package uses the "xmlGetFeaturesList" method which has been removed in newer versions of libxml2. For this reason we define the use of packages above.

If the author stops using this method, the installation can use the latest version of the libraries, making step 3 simpler as follows:
```shell
$ pacman -S mingw-w64-x86_64-{gcc,go,libxml2,iconv}
```

The command mingw-w64-x86_64-{gcc,go,libxml2,iconv} gets expanded by Bash into the following list of packages:
```
mingw-w64-x86_64-gcc
mingw-w64-x86_64-go
mingw-w64-x86_64-libxml2
mingw-w64-x86_64-iconv
```
