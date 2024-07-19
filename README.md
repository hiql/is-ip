# is-ip

Check if a string is an IP address

## Install

```toml
[dependencies]
is-ip = "0.1.0"
```

## Usage

```rust
use is_ip::{is_ip, is_ipv4, is_ipv6};

is_ip("1:2:3:4:5:6:7:8");
//=> true

is_ip("192.168.0.1");
//=> true

is_ipv4("1:2:3:4:5:6:7:8");
//=> false
```

## API

### is_ip(string: &str) -> bool

Check if `string` is IPv6 or IPv4.

### is_ipv4(string: &str) -> bool

Check if `string` is IPv4.

### is_ipv6(string: &str) -> bool

Check if `string` is IPv6.

### ip_version(string: &str) -> Option&lt;u8&gt;

Returns `Some(6)` if `string` is IPv6, `Some(4)` if `string` is IPv4, or `None` if `string` is neither.

```rust
use is_ip::ip_version;

ip_version("1:2:3:4:5:6:7:8");
//=> Some(6)

ip_version("192.168.0.1");
//=> Some(4)

ip_version("abc");
//=> None
```

This lib inspired by [is-ip](https://www.npmjs.com/package/is-ip) a nodejs package!
