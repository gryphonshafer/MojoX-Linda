# NAME

MojoX::Linda - Plausibly helpful (and probably drunk) wrapper around morbo

# VERSION

version 1.04

[![test](https://github.com/gryphonshafer/MojoX-Linda/workflows/test/badge.svg)](https://github.com/gryphonshafer/MojoX-Linda/actions?query=workflow%3Atest)
[![codecov](https://codecov.io/gh/gryphonshafer/MojoX-Linda/graph/badge.svg)](https://codecov.io/gh/gryphonshafer/MojoX-Linda)

# SYNOPSIS

    linda [OPTIONS]
        -s, --silent
        -a, --app        APPLICATION
        -p, --production
        -b, --backend    MOJO_MORBO_BACKEND
        -l, --listen     LISTEN_PATTERN    # can be repeated
        -w, --watch      DIRECTORY_OR_FILE # can be repeated
        -h, --help
        -m, --man

# DESCRIPTION

`linda` is a plausibly helpful (and probably drunk) wrapper around `morbo`,
provided by [Mojo::Server::Morbo](https://metacpan.org/pod/Mojo%3A%3AServer%3A%3AMorbo). Like `morbo`, `linda` will accept various
configuration settings for server operation; but unlike `morbo`, `linda` will
hallucinate settings that aren't set explicitly.

In theory, if you just call `linda` without any settings, `linda` will call
`morbo` in the way you want. In practice, `linda` will probably act inebriated.

## -s, --silent

This is the inverse of the `morbo` "verbose" flag. If not set, `linda` assumes
you want verbose.

## -a, --app

This is the Mojolicious application you'd like to startup. If not set explicitly,
`linda` will look around (from your current working directory) for an
executable file that has code in it that looks like it's probably a
Mojolicious application.

`linda`'s judgement here should not be trusted.

## -p, --production

Set MOJO\_MODE to "production".

## -b, --backend

See [Mojo::Server::Morbo](https://metacpan.org/pod/Mojo%3A%3AServer%3A%3AMorbo).

## -l, --listen

One or more locations you want to listen on. If not set explicitly, `linda`
will look for open ports starting with 3000 and going up to 3999. The first
open port will be used.

## -w, --watch

See [Mojo::Server::Morbo](https://metacpan.org/pod/Mojo%3A%3AServer%3A%3AMorbo).

# CONFIGURATION

`linda` will initially try to find and load a configuration file via a call to
[Config::App](https://metacpan.org/pod/Config%3A%3AApp). If that returns a configuration, `linda` will look in that
configuration under `mojolicious/linda` for settings. Any settings will be
overwritten by any explicit command-line settings.

# SEE ALSO

You can also look for additional information at:

- [GitHub](https://github.com/gryphonshafer/MojoX-Linda)
- [MetaCPAN](https://metacpan.org/pod/MojoX::Linda)
- [GitHub Actions](https://github.com/gryphonshafer/MojoX-Linda/actions)
- [Codecov](https://codecov.io/gh/gryphonshafer/MojoX-Linda)
- [CPANTS](http://cpants.cpanauthors.org/dist/MojoX-Linda)
- [CPAN Testers](http://www.cpantesters.org/distro/M/MojoX-Linda.html)

# AUTHOR

Gryphon Shafer <gryphon@cpan.org>

# COPYRIGHT AND LICENSE

This software is Copyright (c) 2023-2050 by Gryphon Shafer.

This is free software, licensed under:

    The Artistic License 2.0 (GPL Compatible)
