### 2.0.0 (Apr 14, 2026)

LOD System (details coming soon)

> **Personal note:** Keeping an eye on this release — LOD support could be huge for large scene performance. Will test once details drop.

### 0.1.10 (Oct 24, 2025)

[SOG v2](https://blog.playcanvas.com/playcanvas-open-sources-sog-format-for-gaussian-splatting/) support, new examples and bug fixes

> **Personal note:** The `minPixelRadius` property looks handy for culling tiny splats on mobile. Also want to dig into the interactive holes example — could be useful for masking effects. Tested the interactive ripples effect — works great, though I bumped the default ripple strength slightly for more visible results. The logarithmic depth buffer support (#199) is also worth testing — could help with z-fighting in scenes that mix splats with traditional geometry. **Update:** Tested logarithmic depth buffer with a mixed scene (splats + glTF geometry) — z-fighting is basically gone. Definitely enabling this by default in my projects.

### Enhancements

- SOGSv2 (SOG) compression format support (#179) (@mrxz)
- Use DecompressionStream for decompressing .spz files for faster loading times (#181) (@mrxz)
- Make WASD default control for viewer (#6d7d801) (@dmarcos)
- Add `minPixelRadius` property to discard splats during vertex shader (#184) (@mrxz)
- Docs enhancements (@querielo)
- Interactive holes example (#189) (@kali-shade)
- Interactive ripples effect (#194) (@kali-shade)
- Support logarithmic depth buffer (#199) (@Philipp-M)

### Bug fixes

- Issue preventing the splats from being updated when they should. (#191) (@mrxz)
- Make bash script conform to "standard" (#197) (@Philipp-M)
- Fix issue with splats rendered at incorrect position for a few frames (#200) (fix #192, #193) (@mrxz)

### 0.1.9 (Sep 22, 2025)

Performance improvements, SPZ v3 support, new splat transition and reveal effects, brush painting / erasing splat example.

> **Personal note:** The `.ply` parsing speed improvements here are noticeable on larger scenes. Also excited to try the brush painting example for interactive demos. Worth noting: the ortographic rendering support (#157) is useful for top-down architectural previews — tested with a building scan and it works cleanly.

### Enhancements

- New splat transition effects (#172) (@kali-shade)
- New splat reveal effects (#153, #149) (@kali-shade)
- Add support for SPZ v3 (fix #151) (#171) (@gwegash, @dmarcos)
- Reduce small memory allocations when loading ply files (#147) (@mrxz)
- Improve .ply parsing speed using compiled parser function (#150) (@mrxz)
- Add support for ortographic rendering (#157) (@mrxz)
- Make sure all examples resize when the window is resized (#155) (@mrxz)
- Call gl.flush() to encourage eager execution. SparkRenderer.updateInternal was not immediately executed (#156) (@mrxz)
- Use child mesh in `SplatMesh` to auto-inject `SparkRenderer` instead of monkey-patching (#158) (@mrxz)
- Pre-compute lookup tables when parsing SOGS files (#159) (@mrxz)
- Avoid allocating THREE.Quaternion instances in `setPackedSplat` (#160) (@mrxz)
- Use native `Float16Array` to encode a number as a float16 if available. (#161) (@mrxz)
- Spl