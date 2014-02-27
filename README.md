# Base32hex-RFC2938-Standard

## Backgroubd Information
This is ID.me's Objective-C implementation of the [Base32hex (RFC2938 standard) encoder and decoder][rfc2938]. Originally, this repository was created by [MightyKan](https://github.com/mightykan/base32), and featured [Douglas Crockford][dc-website]'s Base32 encoding.

**Note**: This library should not be mistaken for the [rfc4648](RFC4648) data encoding specifications.

[rfc2938]: http://tools.ietf.org/html/rfc2938#section-3.1.2 "RFC2938"
[dc-website]: http://www.crockford.com "Douglas Crockford's Wrrld Wide Web"
[dc-base32-encoding]: http://www.crockford.com/wrmg/base32.html "Base32 Encoding"
[rfc4648]: http://tools.ietf.org/html/rfc4648 "The Base16, Base32, and Base64 Data Encodings"


## Installation
```
pod 'Base32hex'
```

or manually install it by draggubg (`Base32.h` and `Base32.m`) into your project and import the header file into any class where you wish to use the Base32 functionality.

## Usage (Encoding)
To encode a number, for example '1234':

	NSLog(@"%@", [Base32 encode:@"1234"]);
	
which will yield:
	
	16I

## Usage (Decoding)
To decode a Base32 string, for example 'TOQQG0'

	NSLog(@"%@", [Base32 decode:@"TOQQG0"]);

which will yield:

	999123456