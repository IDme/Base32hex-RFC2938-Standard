Base32hex-RFC2938-Standard
======

This is TroopSwap's Objective-C implementation of the [Base32hex (RFC2938 standard) encoder and decoder][rfc2938]. Originally, this repository was created by [MightyKan](https://github.com/mightykan/base32), and featured [Douglas Crockford][dc-website]'s Base32 encoding.

*Note*: This library should not be mistaken for the [RFC4648][rfc4648] data encoding 
specifications.

**IMPORTANT NOTE**: This library can only encode decimal values with ten or *less* digits. If you require the ability to encode and decode very large number please see the [Base32 Large Number][mightykan-base32-ln] project, which uses the [OpenSSL][openssl-website] [bn(3)][openssl-docs-bignum] facilities.

[rfc2938]: http://tools.ietf.org/html/rfc2938#section-3.1.2 "RFC2938"
[dc-website]: http://www.crockford.com "Douglas Crockford's Wrrld Wide Web"
[dc-base32-encoding]: http://www.crockford.com/wrmg/base32.html "Base32 Encoding"
[rfc4648]: http://tools.ietf.org/html/rfc4648 "The Base16, Base32, and Base64 Data Encodings"
[mightykan-base32-ln]: http://github.com/mightykan/base32-ln "Base32 Large Number"
[openssl-website]: http://www.openssl.org "OpenSSL: The Open Source toolkit for SSL/TLS"
[openssl-docs-bignum]: http://www.openssl.org/docs/crypto/bn.html#NAME "OpenSSL: Documents, bn(3)"

OS Compatibility
----------------
- The actual library (`Base32.h` and `Base32.m`) should be usable on iOS 4 or later, or OS X v10.7 or later. Since NSRegularExpression ([iOS][apple-doc-nsregularexpression-ios], [OS X][apple-doc-nsregularexpression-osx]) is used for encoding, iOS 4 or OS X v10.7 is required.
- The demo project requires iOS 5 or higher, since a Storyboard is used for the main user interface.

[apple-doc-nsregularexpression-ios]: https://developer.apple.com/library/ios/#documentation/Foundation/Reference/NSRegularExpression_Class/Reference/Reference.html#//apple_ref/doc/uid/TP40009708 "NSRegularExpression Class Reference (iOS)"
[apple-doc-nsregularexpression-osx]: https://developer.apple.com/library/mac/#documentation/Foundation/Reference/NSRegularExpression_Class/Reference/Reference.html#//apple_ref/doc/uid/TP40009708 "NSRegularExpression Class Reference (OS X)"


ARC Compatibility
-----------------
Base32 can automatically detect whether your project is using [ARC][clang-docs-arc], and generate the correct code using conditional compilation. Therefore, it will work regardless of your project's ARC settings.

[clang-docs-arc]: http://clang.llvm.org/docs/AutomaticReferenceCounting.html "Objective-C Automatic Referencing Counting (ARC)"

Dependencies
------------
None.

*Note*: To have a self-contained library, this implementation does not require any external dependencies, however this limitation forces an upper limit of ten or less digits on the length the decimal number to be encoded. For another implementation that is capable of encoding and decoding very large numbers, see [Base32 Large Number][mightykan-base32-ln].

Installation
------------
To use the Base32 category in your project, just drag the header and implementation files (`Base32.h` and `Base32.m`) into your project and import the header file into any class where you wish to use the Base32 functionality.

Usage
-----
To encode a number, for example '1234':

	NSLog(@"%@", [Base32 encode:@"1234"]);
	
which will yield:
	
	16I

To decode a Base32 string, for example 'TOQQG0'

	NSLog(@"%@", [Base32 decode:@"TOQQG0"]);

which will yield:

	999123456

License
-------
	MIT License (MIT)

	Copyright (c) 2012 Ashkan Farhadtouski

	Permission is hereby granted, free of charge, to any person obtaining a copy
	of this software and associated documentation files (the "Software"), to deal
	in the Software without restriction, including without limitation the rights
	to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
	copies of the Software, and to permit persons to whom the Software is
	furnished to do so, subject to the following conditions:

	The above copyright notice and this permission notice shall be included in
	all copies or substantial portions of the Software.

	THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
	IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
	FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
	AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
	LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
	FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS
	IN THE SOFTWARE.
