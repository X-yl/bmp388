# bmp388

> no_std driver for the bmp388 (pressure sensor).

## Basic usage

Include [library](https://crates.io/crates/bmp388) as a dependency in your Cargo.toml
[![crates.io](http://meritbadge.herokuapp.com/bmp388)](https://crates.io/crates/bmp388):

```
[dependencies.bmp388]
version = "<version>"
```

Use [`embedded-hal`](https://crates.io/crates/embedded-hal) implementation to get I2C handle and delay then create bmp388 handle:

```rust
extern crate bmp388; // or just use bmp388; if 2018 edition is used.

// to create sensor with default configuration:
let mut ps = bmp388::BMP388::new(i2c)?;
// to get pressure:
let pres = ps.sensor_values();
println!("{:?}", pres);
```


## Documentation

API Docs available on [docs.rs](https://docs.rs/bmp388).

## Features

- default: none enabled by default
- `defmt-03` - enable [`defmt@0.3`](crates.io/crates/defmt) formatting for structs and enums
- `serde` - enable [`serde`](crates.io/crates/serde) Deserialize and Serialize implementations on structs and enums
- `asynch` - enable [`embedded-hal-async`](https://crates.io/crates/embedded-hal-async) implementation for the Asynchronous API.
- `config-builder` - enable the typed config builder `ConfigBuilder` for setting up the sensor and initializing it.

## Minimum supported Rust version (MSRV)
For the blocking API the MSRV is `1.65`, however, for the asynchronies API, enabled with the feature `asynch`, the MSRV is `1.75`.

## ToDo:

* Implement FiFo Buffer support

## Origin

Based on the [bmp280 crate](https://github.com/copterust/bmp280) by Roma Sokolov and Alexander Zhuravlev.

## License

- MIT license ([LICENSE-MIT](LICENSE-MIT) or http://opensource.org/licenses/MIT)
