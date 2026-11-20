# Status

Historical project, March 2012. Not maintained. Checked 2026-11-20 on Ruby 3.3.6 with nokogiri 1.19 and minitest 5 (not the 2012 toolchain).

## Works
- `require 'fiat_navigator'` loads once `nokogiri` is installed.
- `FiatNavigator.translate_to_gold 500, :dollars` returns `0.3009 ounces gold`, using the fixed constant $1,661.50 per ounce.
- `Stash`, `do_business_with_the_federal_reserve`, and the stash and navigator tests (with a shim for the old `MiniTest::Unit::TestCase` name; see below).

## Broken
- `translate_to_dollars` and silver: described in the README, never implemented.
- `Gold.dollars_per_ounce` and `dollars_per_gram`: scrape goldmoney.com, which has changed or gone; `open` on a URL also no longer works on Ruby 3 (use `URI.open`). Their tests hard-code 2012 prices and error out.
- `previous_translation` returns the **first** translation, not the latest, so the original README's "last translation" claim is wrong.
- `test_all_previous_translations` fails on current Ruby: the class variable keeps state across tests, so the order assumption breaks.
- Tests use `MiniTest::Unit::TestCase`, removed in minitest 5.19+. Without a shim, `rake test` does not start.
- The gemspec author email is not Steven's (probably copied from another gemspec), and the gem was never published.

## Unknown
- Whether the gem builds and installs on a current RubyGems (not tried).

## Next (only if revived)
Decide the profile first (a rewrite is likely). Implement the reverse conversion, take the price from a live source, fix `previous_translation`, port tests to `Minitest::Test`.

## Not yet from the repo standard
Profile: `legacy`. Still missing: CONTRIBUTING.md, SECURITY.md, LICENSE (Steven's choice), CHANGELOG.md, .github/ (templates, CODEOWNERS, Dependabot, CI), docs/ARCHITECTURE.md, API docs, events/CATALOG.md (waits for revival), `master` to `main`.
