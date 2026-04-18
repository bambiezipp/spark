### 2.0.0 (Apr 14, 2026)

LOD System (details coming soon)

> **Personal note:** Keeping an eye on this release — LOD support could be huge for large scene performance. Will test once details drop.

### 0.1.10 (Oct 24, 2025)

[SOG v2](https://blog.playcanvas.com/playcanvas-open-sources-sog-format-for-gaussian-splatting/) support, new examples and bug fixes

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
- Splat brush painting / brush erasing example (#165) (@winnie1994)

### 0.1.8 (July 31, 2025)

Bug fix + SplatMesh bounding box calculation.

### Bug fixes

- Fix SH encoding scale factors (#142) (@asundqui, @mrxz, @heimeii)
- Calculate a SplatMesh's bounding box! `SplatMesh.getBoundingBox()` (#126) (@winnie1994)

### 0.1.7 (July 30, 2025)

Image quality and performance improvements.

### Enhancements

- Customizable splat encoding ranges (rgb, sh1, sh2, sh3) for wider range of colors and scales support improving contrast and color reproduction. Expose `premultipliedAlpha` flag to use when accumulating splat RGB (#134) (@asundqui)
- [Experimental Stochastic splat ordering option](https://sparkjs.dev/examples/stochastic/). Faster rendering since sorting no longer needed but with some v

> **Personal note:** The `minPixelRadius` property added in 0.1.10 looks really useful — going to experiment with setting it to ~0.5 by default in my scenes to cull tiny splats and squeeze out some extra frame time.
