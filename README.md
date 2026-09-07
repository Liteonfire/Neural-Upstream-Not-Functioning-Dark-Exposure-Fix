# Neural Upstream - Not Functioning / Dark Exposure Fix

Sharing a Neural Upstream (`nvngx.dll`) build that fixed an issue for me where DLSS5 Neural Upstream (w/ DLSS5 Autopilot) would cause a dark screen without any other visible effects from DLSS5.

While debugging, ChatGPT found a mismatch between the DLSS render subrect (1708x961) and the actual Color resource (1708x964) causing the issue.

I recompiled Neural Upstream so `setup_nr()` uses the dimensions of the actual Color resource instead of the DLSS render subrect.

The resolution is **not hardcoded**, so this may also work in other games with the same issue.

### Tested on
- RTX 3070ti
- Star Wars Zero Company
- Neural Upstream v0.3.0

### Installation
Back up your existing Neural Upstream `nvngx.dll` and replace it with the provided `nvngx.dll`.

**Do not replace `nvngx_dlssnr.dll`.**

Original project:
https://github.com/matiasLombo/neural-upstream

Based on the fix discussed here:
https://github.com/matiasLombo/neural-upstream/issues/3
