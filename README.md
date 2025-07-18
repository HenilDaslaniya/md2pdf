# Markdown to PDF Converter

This Python script converts Markdown files into professionally formatted, OCR-friendly PDF documents. It uses a custom CSS stylesheet to ensure clean, elegant, and readable output, making it suitable for documentation, reports, and publishing. Whether you're a developer, writer, student, or technical professional, this tool streamlines the process of turning Markdown into print-ready PDFs with minimal effort.

## Features

* Converts `.md` Markdown files into PDF
* Professional styling via custom or built-in CSS
* Ensures compatibility with Optical Character Recognition (OCR)
* Automatically sets up a virtual environment and installs dependencies
* Supports advanced Markdown features like code blocks, tables, footnotes, blockquotes, and inline HTML
* Provides a flexible command-line interface with support for output naming, custom styles, and document titling
* Uses WeasyPrint to generate high-quality, standards-compliant PDF output
* Automatically manages output directories if they do not exist

## Requirements

* Python 3.x
* Linux/macOS (WeasyPrint dependency may require additional system packages such as `libffi-dev`, `libpango`, or `libcairo2`)
* Internet access for initial virtual environment setup (only required once)

## Dependencies

Installed automatically via virtual environment:

* [`markdown`](https://pypi.org/project/Markdown/) – Converts Markdown to HTML
* [`weasyprint`](https://weasyprint.org/) – Converts HTML to PDF with CSS support

## Usage

### 1. **Download** the script:

Save `md_to_pdf.py` to your desired directory.

### 2. **Run the script:**

```bash
python3 md_to_pdf.py path/to/input.md
```

Optional arguments:

```bash
python3 md_to_pdf.py input.md \
  -o output.pdf \
  -c custom.css \
  -t "Custom PDF Title"
```

* `-o`, `--output`: Specify a custom output path for the PDF
* `-c`, `--css`: Apply a custom CSS file for layout and styling
* `-t`, `--title`: Add a custom title to the HTML metadata and PDF

### 3. **Output:**

* The script generates a PDF in the same folder as the input `.md` file unless specified otherwise.
* Your generated PDFs will be styled for clean layout, OCR-readability, and print-friendliness.

## Customization

You can easily customize the visual appearance using your own CSS file. This allows full control over fonts, colors, margins, headers, and other visual elements. If you do not provide a CSS file, the script uses a built-in professional stylesheet optimized for readability and clean output.

To use your own styles, pass the `-c` flag followed by the path to your CSS file:

```bash
python3 md_to_pdf.py doc.md -c style/custom.css
```

## Example

```bash
python3 md_to_pdf.py notes.md -o notes.pdf -t "My Notes"
```

This command will take `notes.md`, convert it into a stylized PDF named `notes.pdf`, and embed the title "My Notes" into the document metadata.

## Troubleshooting

### Missing System Packages

If you encounter errors when running WeasyPrint (e.g., related to Cairo or Pango), install the necessary system dependencies:

#### Debian/Ubuntu

```bash
sudo apt-get install libpango1.0-0 libgdk-pixbuf2.0-0 libcairo2 libffi-dev
```

### Manual Environment Setup

If the virtual environment setup fails, you can install dependencies manually:

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install markdown weasyprint
```

Then rerun the script within the virtual environment.

## License

This project is open source and available under the [MIT License](https://opensource.org/licenses/MIT). You are free to use, modify, and distribute this software in both personal and commercial projects.

## Author

Created by Henil Daslaniya. Contributions and suggestions are welcome!
