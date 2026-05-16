# @crypto/ripemd

RIPEMD-160 hash function for Zeta — self-contained, no external dependencies.

## Why This Exists

RIPEMD-160 is a critical component of Bitcoin address generation. Combined with SHA256 (the Hash160 construction), it produces 20-byte hashes used in P2PKH and P2SH addresses.

This is a clean-room implementation based on the RIPEMD-160 specification by Hans Dobbertin, Antoon Bosselaers, and Bart Preneel.

## Usage

```zeta
use @crypto/ripemd::{Ripemd160, ripemd160};

// Using the function directly
let hash: [u8; 20] = ripemd160(data);

// Using the struct
let hash = Ripemd160::hash(data);
let bytes = hash.to_byte_array();
```

## API

### Functions

```zeta
pub fn ripemd160(data: &[u8]) -> [u8; 20]
```

### Types

```zeta
pub struct Ripemd160 {
    fn hash(data: &[u8]) -> Self;
    fn from_slice(bytes: &[u8]) -> Result<Self>;
    fn to_byte_array(self) -> [u8; 20];
}
```

## Implementation Notes

- Fully self-contained — no byteorder or other dependencies
- Little-endian internal representation (per RIPEMD-160 spec)
- Big-endian output bytes

## License

MIT

For nour. For Dark Factory. For BSV.
