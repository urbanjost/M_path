# M_path

## Fortran OOP interface for a  POSIX pathname 

   The M_path(3f) module creates an OOP (Object Oriented Programming) interface to other modules in the 
   [GPF ](https://github.com/urbanjost?tab=repositories)
   (General Purpose Fortran) package found at

```back
    git clone https://github.com/urbanjost/general-purpose-fortran
```
   It allows the typical components of a pathname on a POSIX system (Such as GNU/Linux, Unix
   and Cygwin) to be accessed easily, to render the full pathname of the path and to get basic
   file properties (permissions, size, ownership, ...). The type defined is
```fortran
       type path

             ! COMPONENTS:
             character(len=:),allocatable :: name
       contains

             ! METHODS:
             procedure    :: branch
             procedure    :: leaf
             procedure    :: stem
             procedure    :: bud
             procedure    :: init
             procedure    :: is_dir
             procedure    :: stat
             procedure    :: readable
             procedure    :: writable
             procedure    :: executable
             procedure    :: exists
             procedure    :: realpath

             ! OVERLOADED OPERATORS FOR TYPE(path)
             procedure,private :: eq
             generic           :: operator(==)  => eq
       end type path
```

   It requires other modules from the package (_Note that you can get and build
   the GPF package with just a Fortran compiler and make(1)_). This
   repository is intended for allowing access to the module and its
   dependencies via the `fpm` (Fortran Package Manager). Specifically,
   the Fortran version (not the Haskell version).
## DOCUMENTATION   ![docs](docs/images/docs.gif)

   The [man-page](https://urbanjost.github.io/M_path/index.html)

## DOWNLOAD

   To create a copy for alteration using `fpm` use or download the github
   repository and build it with `fpm` ( as described at
   [Fortran Package Manager](https://github.com/fortran-lang/fpm) )
   use

```bash
    git clone https://github.com/urbanjost/M_path.git
     cd M_path
     fpm build
     fpm test
     fpm run -- .
```

   but to use this as intended as a dependency in your fpm.toml project file
   just add the following into your `fpm` manifest file:

```toml
     [dependencies]
     M_path = { git = "https://github.com/urbanjost/M_path.git" }
```

