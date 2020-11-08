# M_path

## parse mathematical expressions

   The M_path(3f) module contains a module that creates an OOP interface
   to other modules in the 
   [GPF ](https://github.com/urbanjost?tab=repositories)
   (General Purpose Fortran) package.

```back
    git clone https://github.com/urbanjost/general-purpose-fortran
```

   It requires other modules from the package. You should get and build
   the GPF package for a conventional way of accessing this module. This
   repository is intended for allowing access to the module and its
   dependencies via the fpm (Fortran Package Manager). Specifically,
   the Fortran version (not the Haskell version).

## DOWNLOAD

   To create a copy for alteration using `fpm` use or download the github
   repository and build it with fpm ( as described at
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
   just add the following:

```toml
     [dependencies]
     M_path = { git = "https://github.com/urbanjost/M_path.git" }
```

## DOCUMENTATION

   The [documentation](https://urbanjost.github/io/M_path.3.html)
   is included as a manpage(1) and as HTML.
