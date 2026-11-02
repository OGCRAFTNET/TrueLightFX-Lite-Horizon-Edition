# TrueLightFX Lite (Horizon Port) v5.6.3

Ported using the built-in Iris-to-Horizon translator.

Designed specifically for Horizon. Not compatible with OptiFine or standalone Iris.

---

## Requirements

Horizon must be configured to use Vulkan before launching.

```ini
graphicsApi:vulkan
```

Vulkan is required for the depth buffer features used by this shader.

---

## Feature Compatibility

| Setting / Feature | Status | Details |
|---|---|---|
| `ENABLE_SHADOWS` | Working | Sunlight shadow projection using the Vulkan depth map. |
| `FLAT_LIGHTING` | Working | Disables vanilla directional shading. |
| `SUN_BRIGHTNESS` | Working | Controls sunlight intensity. |
| `SUN_RAYS` | Working | 32-tap screen-space raymarching in `final.fsh`. |
| `SHADOW_DARKNESS` | Working | Controls minimum shadow darkness. |
| `SHADOW_BLUENESS` | Working | Adds ambient sky color to shadowed areas. |
| `shadowMapResolution` | Working | Supports resolutions from 256 to 4096. |
| `shadowDistance` | Working | Controls shadow rendering distance. |
| `shadowIntervalSize` | Working | Controls shadow map refocusing. Recommended value: 7.0. |
| `SHADOW_PIXEL` | Working | 0 for smooth shadows, higher values for pixelated shadows. |
| `SHADOW_ENTITY` | Working | Enables shadows for players and entities. |
| `WATER_BRIGHTNESS / B / A` | Working | Controls water brightness, blueness and transparency. |
| `REALISTIC_WAVES` | Working | Adds vertex-based wave displacement to water. |
| `REFLECTIONS` | Working | Screen-space reflections on water surfaces. |
| `WATER_CAUSTICS` | Working | Animated underwater lighting patterns on the seafloor. |
| `RAIN_INTENSITY` | Working | Screen-space rain effects. |
| `ENABLE_FOG` | Working | Atmospheric and underwater fog blending. |
| `FOG_ENHANCEMENT` | Working | Adds warm horizon fog during daytime. |
| `BLOOM / BLOOM_STRENGTH` | Working | Soft bloom effect in the composite and final passes. |
| `CLOUD_STYLE` | Working | 0 for classic TrueLightFX clouds, 1 for procedural volumetric clouds. |
| `VIBRANCE` | Working | Adjusts saturation during post-processing. |
| `FXAA` | Working | Fast Approximate Anti-Aliasing in the final pass. |
| `TAA` | Unsupported | Horizon does not currently provide the required sub-pixel camera jitter (`taaOffset`). |
| `MOTION_BLUR` | Working | Velocity-based motion blur in `composite.fsh`. |
| `WAVY_PLANTS` | Working | Adds wind-based movement to foliage. |
| `HAND_DYNAMIC_LIGHTING` | Working | Adds lighting from held light sources. |
| `HIGHLIGHT_WAXED` | Working | Highlights waxed copper when holding honeycomb. |
| `GLOWING_ORES` | Working | Adds self-illumination to ores and flowers. |
| `OUTLINE_MODE / R / G / B` | Broken | Horizon handles outlines through its internal Vulkan line shaders rather than `gbuffers_basic`. |

---

## Known Limitations

### TAA

Temporal Anti-Aliasing is currently unsupported because Horizon does not provide the camera jitter functionality required by the shader. `taaOffset` is currently zero in `gbuffers_terrain`.

### Outlines

Custom outline rendering is broken. Horizon handles outlines through its internal Vulkan rendering system rather than `gbuffers_basic`.

---

## Configuration Notes

- Use Vulkan as the graphics API.
- Set `shadowIntervalSize` to `7.0` for more stable shadow rendering.
- Set `SHADOW_PIXEL` to `0` for smooth shadows.

---

## Compatibility

This port is intended exclusively for Horizon.

It is not designed for OptiFine or standalone Iris.
