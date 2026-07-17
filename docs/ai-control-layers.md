# Zero-config AI control layers

The Glove80 accelerates Codex CLI and Claude Code without changing either
application's keybindings.  Every key emits a native shortcut or types a
built-in slash command, so another keyboard retains the complete standard CLI
interface.

## Activation and safety

- Tap left `C2R6`: existing one-shot Left Shift.
- Hold left `C2R6`, then press a right-hand key: momentary Codex layer 14.
- Tap right `C2R6`: existing one-shot Right Shift.
- Hold right `C2R6`, then press a left-hand key: momentary Claude layer 23.
- Releasing either trigger returns directly to the base layer.
- The former Gaming toggle is removed, and neither AI layer has a toggle.
- AI operation needs no RGB indicator, host bridge, terminal binding, Codex
  config, or Claude keybinding file.
- The World layer remains available from its existing toggle on the Lower
  layer.

The trigger behaviors use ZMK positional hold-tap.  Each hold resolves only
when a key on the opposite hand is pressed, which preserves same-hand typing
and keeps the trigger finger out of the operative keywell.

## Codex: hold left `C2R6`, operate the right hand

Columns below run from the right hand's inner index column (`C1`) toward the
outer column (`C6`).

| Row | C1 | C2 | C3 | C4 | C5 | C6 |
| --- | --- | --- | --- | --- | --- | --- |
| R2 | Agent `/agent` | Side `/side` | Raw `/raw` | Edit queue `Alt+Up` | Fast `/fast` | Usage `/usage` |
| R3 | Details `Ctrl+T` | Model `/model` | Effort+ `Alt+.` | Effort− `Alt+,` | Permissions `/permissions` | New `/new` |
| R4 | Copy `Ctrl+O` | Accept `Y` | Next `Down` | Previous `Up` | Decline `N` | Status `/status` |
| R5 | Editor `Ctrl+G` | Plan `/plan` | Review `/review` | Diff `/diff` | Compact `/compact` | Resume `/resume` |

| Right thumb | T1 | T2 | T3 | T4 | T5 | T6 |
| --- | --- | --- | --- | --- | --- | --- |
| Action | Submit `Enter` | Newline `Ctrl+J` | Queue `Tab` | Accept `Y` | Decline `N` | Stop `Esc` |

## Claude: hold right `C2R6`, operate the left hand

Columns below run from the left hand's outer column (`C6`) toward the inner
index column (`C1`).  This mirrors the Codex action geometry.

| Row | C6 | C5 | C4 | C3 | C2 | C1 |
| --- | --- | --- | --- | --- | --- | --- |
| R2 | Usage `/usage` | Background `Ctrl+X Ctrl+B` | Stash `Ctrl+S` | Thinking `Alt+T` | BTW `/btw` | Agents `/agents` |
| R3 | New `/clear` | Permissions `/permissions` | Effort− `Alt+P`, `Left` | Effort+ `Alt+P`, `Right` | Model `/model` | Details `Ctrl+O` |
| R4 | Status `/status` | Decline `N` | Previous `Up` | Next `Down` | Accept `Y` | Copy `/copy` |
| R5 | Resume `/resume` | Compact `/compact` | Diff `/diff` | Review `/review` | Plan `/plan` | Editor `Ctrl+G` |

| Left thumb | T1 | T2 | T3 | T4 | T5 | T6 |
| --- | --- | --- | --- | --- | --- | --- |
| Action | Submit `Enter` | Newline `Ctrl+J` | Background `Ctrl+X Ctrl+B` | Accept `Y` | Decline `N` | Stop `Ctrl+C` |

## Composer macros

Slash-command macros use 15 ms key timing.  By default they type the command
directly; defining `AI_VIM_COMPOSER` adds `Esc`, `I` first to normalize a Vim
composer to insert mode.  This keymap enables that option for the configured
Vim workflow.  Comment out the define when building for the standard composer.
Invoke command macros from an idle composer with no draft text; native controls
remain available for interrupting or queueing active work.

The deliberate placement follows the keymap's existing ergonomic philosophy:
frequent navigation and decisions stay on the home row, positive/forward
actions roll inward to stronger fingers, inspect/copy/editor form an inner
index-finger rake, session administration moves outward, and prompt/approval
lifecycle actions occupy the natural thumb arcs.  Stop is separated from
Accept by Decline to reduce accidental interruption.  Usage occupies `C6R2`
above New, Status, and Resume, completing the mirrored outer-column session
administration rake without displacing a stronger-finger control.
