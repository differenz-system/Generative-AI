# Overview

The Stable Diffusion WebUI, based on the Stable Diffusion model, provides a user-friendly interface for generating high-quality images using text prompts or image-to-image processing. The model utilizes state-of-the-art techniques to produce diverse and realistic images across various domains. With features like attention control, inpainting, and stable diffusion upscaling, the WebUI offers a versatile platform for creative image generation.

## Key Features:

1. Versatile Modes: The WebUI supports original txt2img and img2img modes, catering to both text-based prompts and image-to-image processing.

2. Easy Installation: A one-click install script streamlines the setup process, making it accessible for users to get started quickly.

3. Diverse Image Generation:

    - Outpainting and Inpainting: Create images by extending or filling in details.
    - Color Sketch: Generate artistic color sketches from prompts.
    - Prompt Matrix: Matrix-based input for exploring various prompt combinations.
    - Stable Diffusion Upscale: Produce high-quality upscaled images.
    - Attention Control: Fine-tune image generation by specifying parts of the text that the model should pay more  attention to. This includes alternative syntax and dynamic adjustment using keyboard shortcuts.

4. Image-to-Image Processing: Users can perform image-to-image processing, allowing them to transform and enhance images based on their needs.

5. Upload Image for Prompt: If users don't have a prompt in mind, they can upload an image to generate a prompt. This option enhances accessibility for users who prefer a visual approach.

6. Additional Neural Network Tools: The WebUI integrates various neural network tools such as GFPGAN, CodeFormer, RealESRGAN, ESRGAN, SwinIR, Swin2SR, LDSR, and more for face restoration, upscaling, and other image enhancement tasks.

7. Customization and Settings: Users can customize defaults, min/max values, and step values for UI elements. The UI supports tiling, negative prompts, variations, seed resizing, and more.

8. Batch Processing: Process multiple files using img2img, providing efficiency for handling multiple images simultaneously.

9. Extensive Documentation: The project includes comprehensive documentation on installation, usage, and customization, available on the dedicated wiki.

# Use Cases
1. **Textile Design Exploration**
- Scenario: A designer in the textile industry wants to explore new design concepts for fabrics. Using Stable Diffusion WebUI, they input text prompts describing desired patterns, colors, and textures. The model generates a variety of textile design options, allowing the designer to experiment with creative ideas and find inspiration for their next collection.

2. **Image Enhancement for Product Photography**
- Scenario: An e-commerce business needs to enhance product images for a visually appealing online store. The WebUI's image-to-image processing feature is used to refine and improve the quality of product photos. Users can experiment with different prompts to achieve the desired aesthetic, making product images more attractive to potential customers.

3. **Prompt-Free Image Generation**
- Scenario: A user doesn't have a specific prompt in mind but has an image that inspires them. They upload the image to the WebUI, which automatically generates a prompt from the uploaded image. This allows users to explore creative possibilities without the need for explicit text prompts.

4. **Customized Textile Pattern Upscaling**
- Scenario: A textile manufacturer wants to upscale existing textile patterns for use in high-resolution printing. The Stable Diffusion WebUI, with its stable diffusion upscaling feature, is employed to enhance the resolution of textile patterns while maintaining visual coherence. This ensures that the upscaled patterns retain their intricate details and clarity.

5. **Batch Processing for Image Transformation**
- Scenario: A user has a collection of images that need uniform transformation, such as applying a specific filter or style. The batch processing capability of the WebUI's img2img mode is utilized to efficiently process multiple images in one go, saving time and effort in the image transformation workflow.

The Stable Diffusion WebUI's flexibility, ease of use, and powerful features make it a valuable tool across various domains, including textile design, e-commerce, and creative image exploration.

## Demo Video
![Alt text](asset/demo.gif "Optional title")

## Features
[Detailed feature showcase with images](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Features):
- Original txt2img and img2img modes
- One click install and run script (but you still must install python and git)
- Outpainting
- Inpainting
- Color Sketch
- Prompt Matrix
- Stable Diffusion Upscale
- Attention, specify parts of text that the model should pay more attention to
    - a man in a `((tuxedo))` - will pay more attention to tuxedo
    - a man in a `(tuxedo:1.21)` - alternative syntax
    - select text and press `Ctrl+Up` or `Ctrl+Down` (or `Command+Up` or `Command+Down` if you're on a MacOS) to automatically adjust attention to selected text (code contributed by anonymous user)
- Loopback, run img2img processing multiple times
- X/Y/Z plot, a way to draw a 3 dimensional plot of images with different parameters
- Textual Inversion
    - have as many embeddings as you want and use any names you like for them
    - use multiple embeddings with different numbers of vectors per token
    - works with half precision floating point numbers
    - train embeddings on 8GB (also reports of 6GB working)
- Extras tab with:
    - GFPGAN, neural network that fixes faces
    - CodeFormer, face restoration tool as an alternative to GFPGAN
    - RealESRGAN, neural network upscaler
    - ESRGAN, neural network upscaler with a lot of third party models
    - SwinIR and Swin2SR ([see here](https://github.com/AUTOMATIC1111/stable-diffusion-webui/pull/2092)), neural network upscalers
    - LDSR, Latent diffusion super resolution upscaling
- Resizing aspect ratio options
- Sampling method selection
    - Adjust sampler eta values (noise multiplier)
    - More advanced noise setting options
- Interrupt processing at any time
- 4GB video card support (also reports of 2GB working)
- Correct seeds for batches
- Live prompt token length validation
- Generation parameters
     - parameters you used to generate images are saved with that image
     - in PNG chunks for PNG, in EXIF for JPEG
     - can drag the image to PNG info tab to restore generation parameters and automatically copy them into UI
     - can be disabled in settings
     - drag and drop an image/text-parameters to promptbox
- Read Generation Parameters Button, loads parameters in promptbox to UI
- Settings page
- Running arbitrary python code from UI (must run with `--allow-code` to enable)
- Mouseover hints for most UI elements
- Possible to change defaults/mix/max/step values for UI elements via text config
- Tiling support, a checkbox to create images that can be tiled like textures
- Progress bar and live image generation preview
    - Can use a separate neural network to produce previews with almost none VRAM or compute requirement
- Negative prompt, an extra text field that allows you to list what you don't want to see in generated image
- Styles, a way to save part of prompt and easily apply them via dropdown later
- Variations, a way to generate same image but with tiny differences
- Seed resizing, a way to generate same image but at slightly different resolution
- CLIP interrogator, a button that tries to guess prompt from an image
- Prompt Editing, a way to change prompt mid-generation, say to start making a watermelon and switch to anime girl midway
- Batch Processing, process a group of files using img2img
- Img2img Alternative, reverse Euler method of cross attention control
- Highres Fix, a convenience option to produce high resolution pictures in one click without usual distortions
- Reloading checkpoints on the fly
- Checkpoint Merger, a tab that allows you to merge up to 3 checkpoints into one
- [Custom scripts](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Custom-Scripts) with many extensions from community
- [Composable-Diffusion](https://energy-based-model.github.io/Compositional-Visual-Generation-with-Composable-Diffusion-Models/), a way to use multiple prompts at once
     - separate prompts using uppercase `AND`
     - also supports weights for prompts: `a cat :1.2 AND a dog AND a penguin :2.2`
- No token limit for prompts (original stable diffusion lets you use up to 75 tokens)
- DeepDanbooru integration, creates danbooru style tags for anime prompts
- [xformers](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Xformers), major speed increase for select cards: (add `--xformers` to commandline args)
- via extension: [History tab](https://github.com/yfszzx/stable-diffusion-webui-images-browser): view, direct and delete images conveniently within the UI
- Generate forever option
- Training tab
     - hypernetworks and embeddings options
     - Preprocessing images: cropping, mirroring, autotagging using BLIP or deepdanbooru (for anime)
- Clip skip
- Hypernetworks
- Loras (same as Hypernetworks but more pretty)
- A separate UI where you can choose, with preview, which embeddings, hypernetworks or Loras to add to your prompt 
- Can select to load a different VAE from settings screen
- Estimated completion time in progress bar
- API
- Support for dedicated [inpainting model](https://github.com/runwayml/stable-diffusion#inpainting-with-stable-diffusion) by RunwayML
- via extension: [Aesthetic Gradients](https://github.com/AUTOMATIC1111/stable-diffusion-webui-aesthetic-gradients), a way to generate images with a specific aesthetic by using clip images embeds (implementation of [https://github.com/vicgalle/stable-diffusion-aesthetic-gradients](https://github.com/vicgalle/stable-diffusion-aesthetic-gradients))
- [Stable Diffusion 2.0](https://github.com/Stability-AI/stablediffusion) support - see [wiki](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Features#stable-diffusion-20) for instructions
- [Alt-Diffusion](https://arxiv.org/abs/2211.06679) support - see [wiki](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Features#alt-diffusion) for instructions
- Now without any bad letters!
- Load checkpoints in safetensors format
- Eased resolution restriction: generated image's dimensions must be a multiple of 8 rather than 64
- Now with a license!
- Reorder elements in the UI from settings screen
- [Segmind Stable Diffusion](https://huggingface.co/segmind/SSD-1B) support

### Automatic Installation on Linux
1. Install the dependencies:
```bash
# Debian-based:
sudo apt install wget git python3 python3-venv libgl1 libglib2.0-0
# Red Hat-based:
sudo dnf install wget git python3 gperftools-libs libglvnd-glx 
# openSUSE-based:
sudo zypper install wget git python3 libtcmalloc4 libglvnd
# Arch-based:
sudo pacman -S wget git python3
```
2. Navigate to the directory you would like the webui to be installed and execute the following command:
```bash
wget -q https://raw.githubusercontent.com/AUTOMATIC1111/stable-diffusion-webui/master/webui.sh
```
3. Run `webui.sh`.
4. Check `webui-user.sh` for options.
### Installation on Apple Silicon

Find the instructions [here](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Installation-on-Apple-Silicon).

## Contributing
Here's how to add code to this repo: [Contributing](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Contributing)

## Documentation

The documentation was moved from this README over to the project's [wiki](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki).

For the purposes of getting Google and other search engines to crawl the wiki, here's a link to the (not for humans) [crawlable wiki](https://github-wiki-see.page/m/AUTOMATIC1111/stable-diffusion-webui/wiki).


