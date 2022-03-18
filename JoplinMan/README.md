# JoplinMan

No not a note taking superhero, just an attempt to see what a Joplin (CLI) manpage would look like.

Created in Markdown (with some odd formatting choices because of 1) the conversion process and 2) some potentially reserved names (like `name` which refused to have proper formatting when converted).

The .md is then converted with [pandoc](https://pandoc.org/), compressed, placed in the local man dir and the man db updated.

If you want you don't have to use the `.md` file and pandoc at all, the `groff` (.1) file can be edited directly but isn't the friendliest thing to read or edit, hence doing it in markdown and converting.

Most of this was from following [this guide](https://www.howtogeek.com/682871/how-to-create-a-man-page-on-linux/)

## Installation

If starting with the .md file:

- To test: `pandoc joplin.md -s -t man | /usr/bin/man -l -` will use `man` to display the man page from `stdin`
- To write: `pandoc joplin.md -s -t man -o joplin.1`
- Once you have the `.1` file, follow the below instructions

If starting with the `.1` file

- Run `manpath` which will show where `man` looks.
    - e.g. `/usr/local/man:/usr/local/share/man:/usr/share/man`
- Check if the correct path exists and, if not, make it with `mkdir`
    - `/usr/local/man/man1`
- Copy `joplin.1` to the above path
    - `sudo cp joplin.1 /usr/local/man/man1`
- Compress the file
    - `sudo gzip /usr/local/man/man1/joplin.1`
- Update the `man` database
    - `sudo mandb`
- Check to see if it worked
    - `man joplin`

If starting with the `.gz` file
- Run `manpath` which will show where `man` looks.
    - e.g. `/usr/local/man:/usr/local/share/man:/usr/share/man`
- Check if the correct path exists and, if not, make it with `mkdir`
    - `/usr/local/man/man1`
- Copy `joplin.1.gz` to the above path
    - `sudo cp joplin.1.gz /usr/local/man/man1`
- Update the `man` database
    - `sudo mandb`
- Check to see if it worked
    - `man joplin`
