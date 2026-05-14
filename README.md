# docx2txt

> 日本語のREADMEはこちらです: [README.ja.md](README.ja.md)

A command-line tool to extract plain text from Microsoft Word (`.docx`) files.

## Features

- Extracts raw text content from `.docx` files.
- Saves extracted text to a new `.txt` file with the same base name.
- Includes a Deno script for batch processing all `.docx` files in a directory.
- Powered by [mammoth](https://www.npmjs.com/package/mammoth) for robust conversion.

## Requirements

- [Node.js](https://nodejs.org/)
- [Deno](https://deno.land/)

## Installation

1.  Clone this repository and navigate into the directory.
2.  Install the Node.js dependencies:
    ```sh
    npm install
    ```

## Usage

This project includes two scripts for different use cases. The core conversion logic is in `docx2txt.js` (Node.js), which is called by the batch processing wrapper `docx2txt_r.js` (Deno).

### Convert a Single File

To convert a single `.docx` file, use the Node.js script:

```sh
node docx2txt.js path/to/your/document.docx
```

This will create `path/to/your/document.txt` in the same directory.

### Batch Convert a Directory

To convert all `.docx` files within a directory, use the Deno script:

```sh
deno run -A docx2txt_r.js path/to/your/directory/
```

This script will find and convert every `.docx` file in the target directory.

#### Example

To convert the included sample file:

```sh
# Note: The '&' in the filename may need to be escaped in your shell
node docx2txt.js sample/惣so\&BOB.docx
```

To process all files in the `sample/` directory:

```sh
deno run -A docx2txt_r.js sample/
```

## License

MIT License — see [LICENSE](LICENSE).