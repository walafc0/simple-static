# simple-static-nojs



## Why another static site generator

Because [simple-static](https://github.com/wlangstroth/simple-static) use Google
API (see
[here](https://github.com/wlangstroth/simple-static/blob/master/ss#L47)), and I
hate Google. Also, I've made little changes:

* I create a `site` directory, and I add a ready-to-use `Makefile` for local
  generation
* There is the last modifcation date on the footer, and the machine where
  content was generated



## Installation

    $ make install

Or if you want to specify the installation path

    $ make install PREFIX=/usr/local

**There may be a conflict with the `ss` binary provided by `iproute2` package
  (on Debian, Archlinux). Be sure this program isn't installed on your machine
  before proceeding, or change the installation path.**



## Configuration

Copy the `site/` folder to your working directory, and edit files to fit your
needs.

 * If you have installed `ss` in another path than `/usr/local`, then change the
   `SS` variable in Makefile
 * Set the remote server and folder for the deployment


A method for converting markdown to html is provided (md2html.awk), but if you
need a more sophisticated markdown processor, you can use something like
[sundown](https://github.com/tanoku/sundown). Follow its installation guide and
change `MDHANDLER` line in your `ss.conf` file to sundown, like so:

    MDHANDLER="sundown"



## Static web generation

From your working directory:

    $ make local
    or
    $ make

The static version of the website is created under 'src.static'.

For example, if you want to create a site with a subdirectory for projects, you
make an index page `index.md` under `src/`, along with a `projects/`
subdirectory, which has its own `index.md`.



## Generate and Upload

The whole process (clean, generation and upload) can be achieve with:

    $ make deploy



## Original Authors

sw was written by:

- Nibble <develsec.org>
- pancake <nopcode.org>
- Andrew Antle

simple-static was writter by:

- Will Langstroth ([wlangstroth](https://github.com/wlangstroth))



## Licence

Since there is no licence on this project, I choose to use a BSD licence. Maybe
I'm wrong, so feel free to contact me for any abuse.
