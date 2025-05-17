## Workflow of the `Binary Image` Function

1. **Load and Convert the Image**

   * Open the file `Foto/gambar.jpeg` using PIL’s `Image.open()`.
   * Convert the image to grayscale mode (`'L'`) so each pixel has a single intensity value (0–255).

2. **Access the Pixel Data**

   * Call `.load()` on the grayscale image to get `PIXEL_GRAYSCALE`, a 2D array-like object that lets you read and write individual pixel values.

3. **Get Image Dimensions**

   * `width  = CITRA_GRAYSCALE.size[0]` → number of columns (horizontal size).
   * `height = CITRA_GRAYSCALE.size[1]` → number of rows (vertical size).

4. **Iterate Over Every Pixel**

   * Use two nested `for` loops:

     ```python
     for x in range(width):
         for y in range(height):
             # process pixel at (x, y)
     ```
   * Read the current grayscale value with `PIXEL_GRAYSCALE[x, y]`.

5. **Apply Thresholding (Binarization)**

   * Compare each pixel’s intensity to the given `nilai_ambang` (threshold):

     * If the value is **less** than `nilai_ambang`, set it to `0` (black).
     * If the value is **greater or equal**, set it to `255` (white).
   * After this step, the image contains only two colors: black and white.

6. **Save the Result**

   * Construct an output filename that includes the threshold, e.g.

     ```python
     hasil_biner = f"gambar_biner_{nilai_ambang}.jpeg"
     ```
   * Save the modified image with `.save(hasil_biner)`.

7. **Notify the User**

   * Print a confirmation message to the console, for example:

     ```
     Binarized image with threshold 128 saved as gambar_biner_128.jpeg
     ```

---

### Example Usage

```python
# Binarize the image with three different thresholds:
citra_biner(50)
citra_biner(128)
citra_biner(200)
```

This README section walks a beginner through each step of the `citra_biner` function, from loading the image to saving the binarized output.
