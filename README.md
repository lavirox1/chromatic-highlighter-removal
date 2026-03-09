# Chromatic Highlighter Removal

A signal and image processing project that removes colored highlighter marks from scanned documents while preserving the underlying text.

## What It Does

Ever scanned a page with highlighter on it and wished you could remove the highlighting? This project does exactly that using computer vision techniques.

The algorithm:
1. Converts the image to HSV color space (which separates color from brightness)
2. Identifies highlighted regions based on saturation levels
3. Applies image processing techniques (blur, threshold, dilation) to create a clean mask
4. Removes the highlight color while keeping the text readable
5. Restores proper paper brightness to avoid gray patches

## Example Results

| Original | Simple Mask | Better Mask | Final Result |
|----------|-------------|-------------|--------------|
| Input image with highlights | Basic saturation removal | Improved with blur + dilation | Brightness correction applied |

Check the `data/` folder for actual before/after examples.

## Project Structure

```
chromatic-highlighter-removal/
├── data/
│   ├── sample1.jpeg              # Input image
│   ├── result_simple_mask.jpg    # Basic approach
│   ├── result_better_mask.jpg    # Improved masking
│   └── result_final.jpg          # Final with brightness fix
├── notebooks/
│   └── process.ipynb             # Main processing notebook
├── src/
│   └── __init__.py              
├── .gitignore
├── README.md
└── requirements.txt
```

## Setup

1. Clone the repository:
```bash
git clone https://github.com/lavirox1/chromatic-highlighter-removal.git
cd chromatic-highlighter-removal
```

2. Create and activate a virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

4. Run the Jupyter notebook:
```bash
jupyter notebook notebooks/process.ipynb
```


## Technologies Used

- **OpenCV**: Image processing operations
- **NumPy**: Fast array operations
- **Matplotlib**: Visualization

## Current Status

This is a working prototype for a Signal and Image Processing course project. The algorithm works well on most highlighter colors but still has room for improvement:

- Different highlighter intensities might need different thresholds
- Very light or very dark highlighters can be tricky
- Multi-colored highlights on the same page need individual tuning

## Future Improvements

- Automatic threshold detection
- Support for multiple highlighter colors simultaneously
- Convert notebook code to a standalone Python script
- Add a simple UI for batch processing

