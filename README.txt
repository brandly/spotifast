Sonos Connect visual review

Open index.html in a browser. All captures are included locally; no server
or Spotify credentials are needed. Select theme, window size, state, and
Before/After. The HTML identifies the revisions and coverage limits.

Baseline: 7048219716fb8bbf2f1af0934f545801f52cb29b, with only the paired
demo fixture from baseline-fixture.patch applied. No playback or UI logic
was changed in that baseline.
Candidate: 34520a6ed1533951f85a9e1d4817f0015ba1e41a.
Platform: macOS ARM64, Retina 2x, app zoom 100%.
Normal inner window: 1280x800 points (2560x1600 pixels).
Narrow inner window: 760x620 points (1520x1240 pixels).

Reproduction, after building with cargo build --locked --all-features:
target/debug/spotifast --demo --demo-data /path/to/disposable-demo-data \
  --demo-page playlist:pl1 --demo-show sonos-idle,dark \
  --demo-size 1280x800 --demo-shot-delay 1000 --demo-shot /path/to/shot.png

Repeat with sonos-active, light, and 760x620 for the other matched states.
Use separate disposable demo-data directories for baseline and candidate.
