# AGENTS.md

Historical Ruby gem (`fiat_navigator`, repo `fiat`), March 2012. Standard profile: **legacy** (not maintained; nothing here has to meet the modern bar until it is revived).

## Stack
Ruby (written for 1.9), Minitest, Nokogiri, Rake, a hand-written gemspec. No Gemfile, no CI.

## Layout
- `lib/fiat_navigator.rb`, `lib/fiat_navigator/{stash,gold}.rb`
- `test/test_*.rb`
- `Rakefile`, `fiat_navigator.gemspec`, `fiat_navigator-0.0.1.gem` (committed build)
- `docs/STATUS.md`, `docs/readme/banner.svg`

## Commands (as they were in 2012)
```sh
rake test            # default task; needs the old MiniTest::Unit::TestCase
gem build fiat_navigator.gemspec
```
On modern Ruby tests need `gem install nokogiri minitest` and a shim for `MiniTest::Unit::TestCase`. See docs/STATUS.md.

## Rules
- Docs-only changes unless Steven revives the repo and picks a real profile first.
- Do not delete the committed `.gem`.
- Never commit secrets or personal data.
- Conventional Commits (`docs:`, `fix:`, `chore:`).
- Update `docs/STATUS.md` whenever behaviour or status changes.
- Keep the original voice of the README ("debt units"); fix facts, not personality.
