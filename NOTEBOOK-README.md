## 🙏 Credits/Contributions
- Inspired from [alembics Notebook](https://colab.research.google.com/github/alembics/disco-diffusion/blob/main/Disco_Diffusion.ipynb) and others.

- Contributions welcomed at [https://github.com/entmike/disco-diffusion-1](https://github.com/entmike/disco-diffusion-1)

- Questions?  Feedback?  Please hunt me down on Discord (`entmike#1926`), or open an Issue in GitHub!

## Links
- [Zippy's DD Cheatsheet](https://docs.google.com/document/d/1l8s7uS2dGqjztYSjPpzlmXLjl5PM3IGkRWI3IiCuK7g)

- [EZ Charts](https://docs.google.com/document/d/1ORymHm0Te18qKiHnhcdgGp-WSt8ZkLZvow3raiu2DVU)


## Changes/Enhancements
- **July 9, 2022**
  - Catch up some DD 5.3 features from alembics
  - Horizontal and Vertical symmetry functionality by nshepperd. Symmetry transformation_steps by huemin (https://twitter.com/huemin_art). Symmetry integration into Disco Diffusion by Dmitrii Tochilkin (https://twitter.com/cut_pow)
- **May 28, 2022**
  - Turbo Mode after frame 10 fixed.  (https://github.com/entmike/disco-diffusion-1/issues/8)
- **May 20, 2022**
  - Voronoi Diagram introduced as an alternative to perlin noise and init_image as a starting point.  To use, set `init_generator` to `voronoi` (Default is `perlin` to honor default noise behavior)  `voronoi_points` controls how many regions the voronoi procedure creates.  You can also optionally control the palette by specifying a different file in `voronoi_palette`.  Refer to the 2 example yaml files in the new `palettes` folder.  There are currently two modes (`generated` and `static`.)  For static, you specify all your values in the yaml file as in the example in `static.yaml`.  For randomly generated color ranges, refer to `default.yaml` to see how you can control what random color hue ranges will be picked.
  - Other minor bug fixes and code cleanup.
- **May 16, 2022**
  - `prompt_salad` feature implemented.  Make Mad Libs out of a `prompt_salad_template`!
- **May 14, 2022**
  - Make this README shared across notebooks (`NOTEBOOK-README.md`)
- **May 13, 2022**
  - Implement (very) experimental vertical symmetry.  (Credit: **`aztec_man#3032`** on Discord)
  - Add GPU detection warning for T4 and V100 GPUs.  (I cannot implement the `!pip install torch==1.10.2 torchvision==0.11.3 -q` patch because it breaks `pytorch3d`, sorry guys, I'll keep trying to find another solution.
- **May 11, 2022**
  - Discord link fixed
- **May 10, 2022**
  - Fix, then break, then fix again, pytorch3d and 3d animations
- **May 6, 2022**
  - Twilio SMS alerts (optional, disabled by default)
- **May 5, 2022**
  - sqlite3 DB support to store your params and images for future query/display/searching.
- **May 4, 2022**
  - Add fallback URLs to model downloads
  - Add `init_images` and `images_out` parameters to control directory locations
  - Add `save_metadata` (Default = `False`) parameter to optionally embed DD params into your .PNGs
  - Add `multiplier` support.
- **May 3, 2022**
  - Add Symmetry Parameters
  - Modifier Support for Art Studies!
- **May 2, 2022**
  - Add initial support for YAML load/export
  - Add initial logging support

- **April 2022**
  - All functions moved to `dd.py` that are not needed in the Notebook to reduce clutter and hopefully improve readibility.

  - All other Git repos that used to get cloned and dumped in your Google Drive are now referenced as pip packages.

## Command-Line Support

  After running the **Set Up Environment** cell, from your Google Colab Terminal you can run your Disco Diffusion workload from a terminal or make a `bash` script to do multiple different batches.  Example:

  ```bash
  cd /content/gdrive/MyDrive/disco-diffusion-1
  python disco.py --steps=50 --batch_name="CommandLineBatch" --RN50=False \
  --text_prompts='{"0":["A beautiful painting of a dolphin","ocean theme"]}'
  ```
## YAML Support from Terminal

  Use a YAML file to save/change your settings.  (See `examples/configs/lighthouse.yml` for an example structure.)
   ```bash
   cd /content/gdrive/MyDrive/disco-diffusion-1
   python disco.py --config_file=examples/configs/lighthouse.yml
   ```