# Creating man Pages

## Introduction

A man page is a manual for a program. It can be called by typing `man <programName>`.  
Man pages are written in the roff language. However, the pandoc tool allows us to write a man page in markdown, which is easier to understand and read.

## Prerequisites

This uses the post "Creating .deb_Packages" as a starting point, as we'll modify its inner structure to add a man page.

1. Inside the package's wd, we basically replicate the Linux file system to determine where our files should be installed.  
Man pages are saved in `/usr/local/man`. So we create the folders, accounting our wd as our "root".
Inside of the man folder, we will create another folder called man1, which will contain our manpage.
2. Write the manpage. There are infos regarding that in the source I will give.
3. Use pandoc to create the roff document
    ```bash
    pandoc <programName>.1.md -s -t man -o <programName>.1
    ```
4. Copy the roff file into the structure
    ```bash
    cp <programName>.1 ./<wd>/usr/local/man/man1/
    ```
5. Man demands compressed files for man pages, so we compress it using gzip.
    ```bash
    gzip <wd>/usr/local/man/man1/<programName>.1
    ```

This is the whole workflow. From here, build your package using dpkg-deb like I described in the other post.

[Source](https://www.howtogeek.com/682871/how-to-create-a-man-page-on-linux/)