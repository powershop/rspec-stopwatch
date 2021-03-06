# rspec-stopwatch

[![Build Status](https://travis-ci.org/powershop/rspec-stopwatch.svg?branch=master)](https://travis-ci.org/powershop/rspec-stopwatch)
[![Release](https://img.shields.io/github/release/powershop/rspec-stopwatch.svg)](https://github.com/powershop/rspec-stopwatch/releases/latest)

RSpec matcher to help with writing performance specs.

## Setup

Add the following line to your Gemfile: `gem 'rspec-stopwatch'`

Include the gem in your spec file (or helper): `require 'rspec/stopwatch'`

## Usage examples

Calling the gem requires passing a block to an expect target and specifying how long you expect it
to run for.

```ruby
expect { ... }.to run_for < 1.second
```

Supported operations on `run_for` are `<`, `<=`, `>` and `>=`.

Currently the matcher runs and averages the block over 10 iterations.
It also treats the first iteration as a warmup and drops it (so 11 iterations total).

## Future work

* Allow the user to specify the number of runs for averaging over
* Allow the user to specify the number of warmup runs to drop
* Allow the user to specify a rough run time (e.g., `run_for =~ 5.seconds`)

