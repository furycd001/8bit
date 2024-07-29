![alt text](8bit.png "8bit")

This is a bash script that uses ImageMagick to convert images to 8-bit color palettes. It defines several color palettes and applies these palettes to all `.jpg`, `.jpeg`, and `.png` images in the current directory. The remapped images are saved in the `output_images` directory.

## Prerequisites

[ImageMagick](https://imagemagick.org) **MUST** be installed on your system.  

**Please ensure `~/.local/bin` is in your `PATH`.  
If not, add the following line to your `~/.bashrc` or `~/.zshrc` and reload the shell:**  

    ```bash
    export PATH=$PATH:~/.local/bin
    ```

## Script Details

The script performs the following steps:

1. Defines a set of color palettes with corresponding hex colors. *(These colors can be changed !!)*
2. Creates an `output_images` directory to store the processed images.
3. Generates palette images based on the defined color palettes.
4. Remaps each image in the current directory using each of the generated palettes.
5. Saves the remapped images in the `output_images` directory with filenames indicating the palette used.
6. Cleans up the generated palette images.


## Usage

### Running from PATH

1. Ensure the script is executable and located in a directory included in your PATH.
    ```bash
    chmod +x 8bit
    mv 8bit ~/.local/bin/
    ```
2. Navigate to the directory containing your images (`.jpg`, `.jpeg`, `.png`).
3. Run the script:
    ```bash
    8bit
    ```
4. Find the remapped images in the `output_images` directory.

### Running without copying to PATH

1. Copy the script to the directory containing your images.
2. Ensure the script is executable:
    ```bash
    chmod +x 8bit
    ```
3. Run the script:
    ```bash
    ./8bit
    ```
4. Find the remapped images in the `output_images` directory.


## Notes

- The script uses Floyd-Steinberg dithering for remapping the images.
- If no images are found in the current directory, the script will simply create an empty `output_images` folder.
- The color palettes are by no means perfect, but they can be easily changed.
