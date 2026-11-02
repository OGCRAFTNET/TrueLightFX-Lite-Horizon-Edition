This pack is ported using the Iris to Horizon translator built into Horizon.
This pack is based on TrueLightFX Lite v5.6.3

Note for Horizon users:
Make sure to set `graphicsApi:vulkan` in your graphics settings (Vulkan is required for depth buffer features).

THIS IS NOT WORKING WITH OPTIFINE OR IRIS ONLY USE THIS SHADER WITH HORIZON!


WORKING AND NOT WORKING RN: 
   Setting / Feature        │      Status in Horizon       │ Details
  ──────────────────────────┼──────────────────────────────┼────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
   ENABLE_SHADOWS           │           Working            │ Sunlight shadow projection via Vulkan depth map.
   FLAT_LIGHTING            │           Working            │ Disables vanilla directional shading so TrueLightFX lighting works properly.
   SUN_BRIGHTNESS           │           Working            │ Modulates sunlight radiance.
   SUN_RAYS (God Rays)      │           Working            │ Implemented via 32-tap screen-space raymarching in final.fsh.
   SHADOW_DARKNESS          │           Working            │ Controls shadow darkness floor.
   SHADOW_BLUENESS          │           Working            │ Tints shadowed regions with ambient sky color.
   shadowMapResolution      │           Working            │ Supports 256 up to 4096.
   shadowDistance           │           Working            │ Max distance for shadow rendering.
   shadowIntervalSize       │           Working            │ Shadow map refocus step (set to 7.0 for stability).
   SHADOW_PIXEL             │           Working            │ 0 = smooth shadows, >0 = retro grid snapping.
   SHADOW_ENTITY            │           Working            │ Full shadow casting for players and entities.
   WATER_BRIGHTNESS / B / A │           Working            │ Controls water luminosity, blueness, and transparency.
   REALISTIC_WAVES          │           Working            │ Vertex wave displacement on water blocks.
   REFLECTIONS              │           Working            │ Screen-space reflection sampling on water surfaces.
   WATER_CAUSTICS           │           Working            │ Animated underwater light patterns on seafloor blocks.
   RAIN_INTENSITY           │           Working            │ Screen-space rain streak blending.
   ENABLE_FOG               │           Working            │ Atmospheric and underwater fog distance blend.
   FOG_ENHANCEMENT          │           Working            │ Warm golden horizon fog tinting during daytime.
   BLOOM & BLOOM_STRENGTH   │           Working            │ Soft bloom pass in composite/final.
   CLOUD_STYLE              │           Working            │ 0 = classic TrueLightFX clouds, 1 = volumetric procedural clouds.
   VIBRANCE                 │           Working            │ Saturation enhancement curve in post-processing.
   FXAA                     │           Working            │ Fast Approximate Anti-Aliasing (edge-detected in final pass).
   TAA                      │   ⚠ Unsupported by Horizon   │ Horizon's logs state gbuffers_terrain: zero for now: taaOffset. Sub-pixel camera jitter is not yet provided by Horizon's engine
   MOTION_BLUR              │           Working            │ Velocity-based motion blur in composite.fsh.
   WAVY_PLANTS              │           Working            │ Foliage swaying using wind noise in vertex stage.
   HAND_DYNAMIC_LIGHTING    │           Working            │ Lighting from held light sources.
   HIGHLIGHT_WAXED          │           Working            │ Highlights waxed copper when holding honeycomb.
   GLOWING_ORES             │           Working            │ Self-illumination emission for ores and flowers.
   OUTLINE_MODE / R / G / B │ ❌ Not Functional in Horizon │ Horizon renders block outlines natively with internal Vulkan line shaders rather than routing through gbuffers_basic.
