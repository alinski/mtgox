mtgox, An Improved version of mtgox-gem with HTTP API v1
========================

| Homepage:      |  https://github.com/GutenYe/mtgox       |
|----------------|------------------------------------------------------       |
| Author:	       | Guten                                                 |
| License:       | MIT-LICENSE                                                |
| Documentation: | http://rubydoc.info/gems/guten-mtgox/frames                |
| Issue Tracker: | https://github.com/GutenYe/mtgox/issues |

An improved version of original [mtgox](https://github.com/sferik/mtgox).

API support: HTTP API v1

Getting started
---------------

	require "mtgox"

	ticker = MtGox.ticker
	p ticker #=> #<MtGox::Ticker:0x51687540 @high=4.86092, @low=4.71083, ...>
	p ticker.high => 4.86092

	# Get raw data
	p ticker.attrs #=> {"high"=>{"value"=>"4.86092", "value_int"=>"486092", ...}

	# Get a hash version data
	p ticker.to_hash #=> {:high => 4.86092, :low => 4.71083, ..}

	# Certain methods require authentication
	MtGox.configure do |c|
		c.key = YOUR_MTGOX_KEY
		c.secret = YOUR_MTGOX_SECRET
	end

	me = MtGox.me

	# Fetch your info
	p me.info

	# multi-currency support

	MtGox.configure do |c|
		c.currency = :eur  # by default is :usd.
	end
	p MtGox.currency

	p MtGox.ticker # in EUR currency
	p MtGox.ticker :usd # in USD currency

Install
-------

	# Gemfile
		gem "guten-mtgox", :git => "git://github.com/GutenYe/mtgox.git"
	
Note on Patches/Pull Requests
-----------------------------

1. Fork the project.
2. Make your feature addition or bug fix.
3. Add tests for it. This is important so I don't break it in a future version unintentionally.
4. Commit, do not mess with rakefile, version, or history. (if you want to have your own version, that is fine but bump version in a commit by itself I can ignore when I pull)
5. Send me a pull request. Bonus points for topic branches.
6. Coding Style Guide: https://gist.github.com/1105334

Credits
-------

* [Contributors](https://github.com/GutenYe/mtgox/contributors)

Resources
---------

* [MtGox/API/HTTP/v1](https://en.bitcoin.it/wiki/MtGox/API/HTTP/v1) MtGox HTTP API Specification

Copyright
---------

(the MIT License)

Copyright (c) 2011 Guten

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the 'Software'), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.  IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
