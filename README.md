Ninja Gaiden III – Restored Plus with NG2-Inspired Physics

An unofficial patch for Ninja Gaiden III: The Ancient Ship of Doom (USA), combining previous restoration work with additional physics, collision, and stage-layout changes.

This project builds upon the work of MottZilla and Binarynova, adding Ninja Gaiden II-inspired movement and the stage corrections required to support the new physics.

Original patch content

Ninja Gaiden III – Restored by MottZilla

MottZilla’s original patch restores several elements changed in the North American release:

Enemy damage adjusted to match the Famicom version.

Unlimited continues.

A password system similar to the Japanese release.

Ninja Gaiden III – Restored PLUS by Binarynova

Binarynova’s addendum restores further differences from the North American release:

Enemy positions, quantities, and types changed to match the Famicom version.

Item locations changed to match the Famicom version.

After dying, Ryu restarts at the beginning of the corresponding stage.

Spikes deal three bars of damage.

Quicksand also deals three bars of damage.

Note: the quicksand behavior is not a perfect reproduction of the Famicom version. In the Japanese release, quicksand normally causes Ryu to sink and fall without dealing direct damage. The three-bar damage implementation was retained because of structural differences in the North American maps.

New changes in this project

Ninja Gaiden II-inspired physics

Player gravity modified to produce movement closer to Ninja Gaiden II.

Vertical jump velocities adjusted.

Wall-jump impulse increased.

Approximately 10 additional pixels of height when jumping away from a wall.

The new gravity routine is applied specifically to the player to avoid unnecessary changes to enemies and other objects.

Corrected an earlier implementation that caused Ryu to jitter while standing on the moving platform in Stage 3-1A.

The physics were adjusted to bring Ryu’s movement closer to Ninja Gaiden II. Because this changed the effective range of certain jumps, the wall-jump impulse was increased by approximately 10 pixels. This adjustment makes it possible to clear sections that had become impossible or inconsistent under the new physics, preserving normal stage progression.

Stage changes

Stage 7-2A – yellow beam and climbable wall

Removed the visible yellow electrical-beam obstacle.

Replaced its local map block without globally changing the underlying graphics tile.

Gave the exposed wall behind it climbable-wall collision.

Configured all four wall tiles to behave as a regular physical wall.

Ryu can now grab and climb the exposed wall.

Stage 7 climbing section

Removed the diagonal wall protrusion that extended to the right and blocked upward movement with the new physics.

Replaced the removed section with a background block that has no collision.

Replaced the vertical wall on the left with blocks confirmed to support climbing.

Adjusted the block transition so Ryu can climb upward directly.

Nearby spike blocks were preserved and their graphics and collision were not modified.

Crumbling platform extension

The original sequence contained two 16×16 crumbling platform units.

Two additional crumbling units were added.

The complete platform now contains four 16×16 units and is 64 pixels wide.

Each unit consists of four 8×8 tiles.

The added units retain the original crumbling animation and collision behavior.

An early implementation reused global block 00. That block was also used in the upper-left corner of the Stage 7-5A battle against Clancy’s second form, causing a graphical glitch.

The final implementation:

Fully restores global block 00.

Uses exclusive block 84 for the added platform.

Verifies that block 84 was not referenced by the Stage 7 map data.

Fixes the Stage 7-5A boss-screen graphical corruption.

Avoids modifying other screens that rely on shared block definitions.

Compatibility

Apply the IPS only to the original North American ROM:

Ninja Gaiden III: The Ancient Ship of Doom (USA)

Original ROM hashes:

CRC32: BABD39FA

MD5: 569B3382638A1C9094E2C40B35F359C7

SHA-1: 3F2E6DAC76BA14EFC177B5653AB043E53A04D365

SHA-256: 49846B57FEE22AE0E3AD86DB5B9220F5F78B94317316135CBD71F12DE4FB6458

Resulting testing 11 ROM hash:

SHA-256: FE6AC5A9D521703F9419756CAB216728D50FC4C9DBEC4ADD67EA42D6657FF77A

Do not apply Restored or Restored PLUS separately beforehand. The complete IPS already contains all required changes.

Observed issue

During testing in Stage 5-1B, an occasional issue involving vertical scrolling, enemies, and moving platforms was observed. In some cases, objects may move incorrectly or the game may return to the previous screen.

TASVideos documents a similar original-game glitch involving enemies near the bottom of the screen, vertical movement, and retained momentum from moving platforms. However, it has not been confirmed that the documented glitch is exactly the same issue observed in Stage 5-1B.

This behavior remains under investigation and has not been modified by the current patch.

Testing recommendations

Start the game after a complete emulator reset.

Avoid loading save states created with earlier ROM revisions.

Create new save states for each patch version.

When reporting a problem, try reproducing it from a clean reset to distinguish an actual ROM issue from save-state incompatibility.

Credits

Tecmo – original game.

MottZilla – Ninja Gaiden III: Restored.

Binarynova – Ninja Gaiden III: Restored PLUS.

Dr. Vee - Coding

FuSoYa – Lunar IPS.

Additional modifications: NG2-inspired physics, jump adjustments, collision corrections, wall changes, yellow-beam removal, and crumbling-platform extension.

This is an unofficial, non-commercial fan modification intended for preservation and experimentation. No commercial ROM is distributed; only the patch file should be provided.
