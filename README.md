# Huffman Coding File Compressor

A complete and efficient implementation of the Huffman coding algorithm in Java for lossless data compression and decompression. This project demonstrates core computer science concepts like greedy algorithms, priority queues, binary trees, and bit-level file I/O.

## Features

- **Lossless Compression & Decompression:** Compresses text files and perfectly reconstructs the original file.
- **Efficient Bit-Packing:** Uses custom `BitInputStream` and `BitOutputStream` classes to read and write individual bits, achieving true compression.
- **Tree Serialization:** Intelligently stores the Huffman tree as a compact codebook for decoding.
- **Robust Exception Handling:** Gracefully handles file errors and invalid inputs.
- **Command-Line Interface:** Simple CLI tools for easy use (`MakeCode`, `Encode`, `Decode`).




## How It Works

1.  **Analysis (`MakeCode`):** Reads an input file, builds a frequency table, and constructs an optimal Huffman tree using a priority queue (min-heap).
2.  **Codebook Generation:** The tree is serialized to a `.code` file, storing the variable-length codes for each character.
3.  **Compression (`Encode`):** Translates the original text into a stream of bits using the codebook and writes them to a compact `.short` file.
4.  **Decompression (`Decode`):** Rebuilds the Huffman tree from the `.code` file and decodes the `.short` bitstream back into the original text.

## Getting Started

### Prerequisites
*   Java JDK 11 or higher

### Compilation and Execution

1.  **Compile all Java files:**
    ```bash
    javac src/*.java
    ```

2.  **Generate a Codebook:** (e.g., for `hamlet.txt`)
    ```bash
    java -cp src MakeCode
    # Follow prompts to enter input.txt and output codefile.code
    ```

3.  **Compress a File:**
    ```bash
    java -cp src Encode
    # Follow prompts to enter input.txt, codefile.code, and output compressedfile.short
    ```

4.  **Decompress a File:**
    ```bash
    java -cp src Decode
    # Follow prompts to enter compressedfile.short, codefile.code, and output decompressed.txt
    ```

5.  **Run Full Integration Test:** (Compresses and decompresses `hamlet.txt`)
    ```bash
    java -cp src HuffmanTesting
    ```

## Technical Highlights

- **Algorithm:** Huffman's greedy algorithm for building an optimal prefix-free binary tree.
- **Data Structures:** Priority Queue (Min-Heap), Binary Trees, Hash Maps (for code lookup).
- **Key Concepts:** Bit-level Manipulation, Recursive Tree Traversal.
- **Java Features:** `Comparator`, `PriorityQueue`, `FileInputStream`, `PrintStream`.

## Results
Successfully compresses text files, achieving significant size reduction for non-random data. The decompressed file is verified to be identical to the original, proving lossless compression.
