plugin: growth-booster-second-brain
plugin_version: 0.1.0
started: null
last_session: null
next_phase: 0
setup_complete: false
uses_gb_os: null                  # true when claude.md and about-me/business.md from Growth Booster OS exist
basics_file: null                 # about-me/business.md, or _sb/basics.md when Growth Booster OS isn't set up
customer_word: customers
update_day: null                  # e.g. "Friday 4:00 PM"
health_day: null                  # e.g. "first Monday of the month, 9:00 AM"

vaults:
  # One entry per vault. Most owners have exactly one. The one with default: true is used
  # whenever the owner doesn't name a vault.
  - name: null                    # short name the owner uses, e.g. "Business"
    path: null                    # full path, always inside the Cowork workspace folder
    mode: null                    # fresh | on-top | as-is
    area: null                    # on-top only: the sub-folder that holds inbox/ and wiki/
    default: true

phases:
  0: { name: welcome,     status: pending, completed: null }
  1: { name: plan,        status: pending, completed: null }
  2: { name: obsidian,    status: pending, completed: null }
  3: { name: build,       status: pending, completed: null }
  4: { name: connect,     status: pending, completed: null, read_test: null, write_test: null }
  5: { name: settings,    status: pending, completed: null }
  6: { name: first-pages, status: pending, completed: null }
  7: { name: routines,    status: pending, completed: null }
  8: { name: sync,        status: pending, completed: null, optional: true, choice: null }
  9: { name: claude-chat, status: pending, completed: null, optional: true }
