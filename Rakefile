# -*- ruby -*-

require 'rubygems'
require 'hoe'
require './lib/qrencoder.rb'

Hoe.spec 'qrencoder' do
  self.version = QRCode::GEM_VERSION
  self.rubyforge_name = 'nycrb'
  self.author = 'Jacob Harris'
  self.email = 'harrisj@schizopolis.net'
  self.summary = 'A gem for creating 2-dimensional barcodes following the QR Code specification.'
  # self.description = self.paragraphs_of('README.txt', 2..5).join("\n\n")
  self.url = 'http://nycrb.rubyforge.org/qrencoder'
  self.changes = self.paragraphs_of('History.txt', 0..1).join("\n\n")
  self.extra_deps << ['RubyInline', '>=3.6.2']
  self.extra_deps << ['png', '>=1.0.0']
end

# vim: syntax=Ruby
