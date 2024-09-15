# Tempfile

A utility class for managing temporary files. When you create a Tempfile
object, it will create a temporary file with a unique filename. A Tempfile
objects behaves just like a File object, and you can perform all the usual
file operations on it: reading data, writing data, changing its permissions,
etc. So although this class does not explicitly document all instance methods
supported by File, you can in fact call any File instance method on a
Tempfile object.

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'tempfile'
```

And then execute:

    $ bundle install

Or install it yourself as:

    $ gem install tempfile

## Usage

```ruby
require 'tempfile'

file = Tempfile.new('foo')
file.path      # => A unique filename in the OS's temp directory,
               #    e.g.: "/tmp/foo.24722.0"
               #    This filename contains 'foo' in its basename.
file.write("hello world")
file.rewind
file.read      # => "hello world"
file.close
file.unlink    # deletes the temp file
```

## Documentation

[RDoc](https://docs.ruby-lang.org/en/master/Tempfile.html)

## Development

After checking out the repo, run `bin/setup` to install dependencies. Then, run `rake test` to run the tests. You can also run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release`, which will create a git tag for the version, push git commits and tags, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/ruby/tempfile.
