# ExtFit

[![Actions Status](https://github.com/arathunku/ext_fit/actions/workflows/elixir-build-and-test.yml/badge.svg)](https://github.com/arathunku/ext_fit/actions/workflows/elixir-build-and-test.yml) 
[![Hex.pm](https://img.shields.io/hexpm/v/ext_fit.svg?style=flat)](https://hex.pm/packages/ext_fit)
[![Documentation](https://img.shields.io/badge/hex-docs-lightgreen.svg?style=flat)](https://hexdocs.pm/ext_fit)
[![License](https://img.shields.io/hexpm/l/ext_fit.svg?style=flat)](https://github.com/arathunku/ext_fit/blob/main/LICENSE.md)

> **Fork for kyop.** Branch `kyop` is ext_fit 0.1.0 (tag `v0.1.0`) with three decoder
> fixes: components of an all-invalid array are not expanded, nested components are cut
> from the parent component's value, and strings that are not valid UTF-8 are read as
> Latin-1. Upstream: https://github.com/arathunku/ext_fit

<!-- @moduledoc -->

`.fit` file decoder. See `ExtFit.Decode` module for more details and usage.

It's still in alpha-release and there's a slim chance that the format of returned
structs will change but if possible, will be avoided.

Currently used FIT profile can be seen in `ExtFit.Profile.Types` file.

## Installation

If [available in Hex](https://hex.pm/docs/publish), the package can be installed
by adding `ext_fit` to your list of dependencies in `mix.exs`:

```elixir
def deps do
  [
    {:ext_fit, "~> 0.1.0"}
  ]
end
```

## Usage

```elixir
{:ok, records} =
  "my-file.fit"
  |> File.read!()
  |> ExtFit.Decode.decode()

# print first record
hd(record)
```

The docs can be found at <https://hexdocs.pm/ext_fit>.

FIT structs are very large, you might want to take a look at
[examples](https://github.com/arathunku/ext_fit/tree/main/examples) first!

https://github.com/arathunku/ext_fit/assets/749393/4c16c3ff-ba47-472b-9323-c9285842c2a8

(may not be visible on hexdocs, see [GitHub README](https://github.com/arathunku/ext_fit/tree/main?tab=readme-ov-file#usage))

## Contributing

Before contributing to this project, please read the CONTRIBUTING.md.

## License

Copyright © 2024 Michal Forys

This project is licensed under the MIT license.
