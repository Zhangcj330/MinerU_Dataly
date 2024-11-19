# PDF Converter using MinerU

This project uses [MinerU](https://github.com/opendatalab/MinerU) to convert PDFs into machine-readable formats (Markdown and JSON). MinerU is a high-quality open-source tool that preserves document structure while extracting content.

## Features

- Converts PDFs to Markdown and JSON formats
- Preserves document structure (headings, paragraphs, lists)
- Extracts images, tables, and formulas
- Supports OCR for scanned PDFs (84 languages)
- Handles complex layouts including multi-column documents
- Removes headers, footers, and page numbers
- Supports both CPU and GPU environments

## Prerequisites

- Python 3.10
## Prerequisites

- Python 3.10

## Installation

1. Create and activate a Python virtual environment

2. Install magic-pdf:
   ```bash
   pip install -U magic-pdf[full] --extra-index-url https://wheels.myhloli.com
   ```

3. Download required models:
   ```bash
   pip install huggingface_hub
   wget https://github.com/opendatalab/MinerU/raw/master/scripts/download_models_hf.py
   python download_models_hf.py
   ```

4. Configure settings:
   - The installation will create a `magic-pdf.json` configuration file in your user directory:
     - Windows: `C:\Users\username`
     - Linux: `/home/username`
     - macOS: `/Users/username`
   - Enable table configuration in this file if needed

## Usage Guide

### Converting PDF to Markdown

#### Using Command Line Interface (CLI)

Basic conversion command:
magic-pdf -p <input.pdf> -o <output_directory> -l <language>

Example:
magic-pdf -p AMP-Elevate-insurance-PDS_10-June-2017.pdf -o . -l en