# Huffman Compression Program

This program implements Huffman coding for file compression and decompression. It provides an efficient way to compress files using variable-length encoding based on character frequency.

## Features

- File compression using Huffman coding
- File decompression
- Progress indicators during compression/decompression
- Timing information for compression/decompression operations

## Requirements

- C++ compiler

## Building the Program

To compile the program, use the following command:

```bash
g++ huffman.cpp -o huffman
```

## Usage

The program supports two operations: compression and decompression.

### Compression

To compress a file:

```bash
./huffman -c <filename>
```

This will create a compressed file with the extension `.abiz`

### Decompression

To decompress a file:

```bash
./huffman -dc <filename.abiz>
```

This will create a decompressed file with the prefix "output" added to the original filename.

## Examples

1. Compressing a text file:
```bash
./huffman -c example.txt
```
This will create `example.txt.abiz`

2. Decompressing the compressed file:
```bash
./huffman -dc example.txt.abiz
```
This will create `outputexample.txt`

## Output Information

The program provides the following information during operation:

- For compression:
  - Original file size
  - Compressed file size (without header)
  - Compression progress percentage
  - Compression time

- For decompression:
  - Decompression progress percentage
  - Decompression time

## Technical Details

- The program uses a binary tree structure for Huffman coding
- Header format includes:
  1. Total unique characters (1 byte)
  2. For each unique character:
     - Character (1 byte)
     - Length of code (1 byte)
     - Huffman code (variable length)
  3. Padding information

## Notes

- The compressed file extension is `.abiz`
- Decompressed files are prefixed with "output"
- Progress is displayed during compression/decompression
- Timing information is provided upon completion

## Error Handling

The program includes basic error handling for:
- Invalid command-line arguments
- File not found errors
- Incorrect usage
