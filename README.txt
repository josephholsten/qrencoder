qrencoder
    by Jacob Harris
    http://www.nimblecode.com/
    http://nycrb.rubyforge.org/qrencoder

== DESCRIPTION:

This Gem is a wrapper around an useful open-source library for creating QR
Codes, a two-dimensional bar code format popular in Japan (and readable by cell
phones even) created by the Denso-Wave Corporation in 1994. These bar codes look
like the following:

http://www.denso-wave.com/qrcode/images/qrcode.gif

The specification for QR codes is readable at
http://www.denso-wave.com/qrcode/index-e.html. QR Code is not the only 2-D
barcode standard in existence, and it is in wider use in Japan than elsewhere.
Notable competitors include PDF417, Semacode/DataMatrix, and Maxi Code (seen on
UPS labels) in North America; ShotCode in the UK; and an additional format used
in Korea. All vary in look and capacity, but QR code has one of the largest
information densities and capacities among them with the following maximum data

* Numeric	7,089
* Alphanumeric 4,296
* 8-Bit 2,953
* Kanji 1,817

All of these in a square that may range from 21 to 177 pixels a side (there are
40 different "versions" of the code that specify different sizes). In addition,
multiple levels of error correction are possible which might also influence the
final size.

== FEATURES/PROBLEMS:
  
* This gem requires you to build and install an external C library
* The QREncode lib this GEM is built around is NOT thread-safe!

== SYNOPSIS:

There are 4 initialization methods for creating a QR code, two for strings, two
for data. Both of these come in a simpler variant which take the string/data to
be encoded. The second argument is a QR Code version (used to pick the size of
the final QR Code); this version is adjusted upwards if the data is too large to
fit within the specified version.

  require 'qrencoder'
  img = QRCode.encode_string(text, 1)
  puts "#{img.version}"  #=> 7
  puts "#{img.width}"    #=> 34
  img.save_png("/tmp/foo.png")

You can retrieve the pixels of the output image directly or use the included
methods to save a PNG file directly.

== REQUIREMENTS:

This gem requires you to build the C library lib <tt>libqrcode.a</tt> available
from http://megaui.net/fukuchi/works/qrencode/index.en.html. 

This gem is built against libqrcode version qrencode-3.1.0 only.

Normally, the build process also expects you to install <tt>libpng</tt>, but
this is only used for the <tt>qrenc</tt> command-line utility and can be avoided
if you run the following build sequence:

  ./configure --without-tools
  make
  sudo make install

This gem also requires the following gems to be installed:

* ruby-inline
* png

== INSTALL:

* First build the <tt>libqrencode</tt> library following the instructions above.
* Then <tt>sudo gem install qrencoder --include-dependencies</tt>

== QRCODE LICENSE:

The QR Code specification was created and patented by the Denso Corporation of
Japan. Although the Denso Corporation retains their patent, it is "open in the
sense that the specification of QR Code is disclosed and that the patent right
owned by Denso Wave is not exercised." according to their website.

== LICENSE:

(The MIT License)

Copyright (c) 2007

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
'Software'), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
