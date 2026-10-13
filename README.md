# Set-Theoretic-Text-Manipulation-Engine
A high-performance text extraction and parsing engine written in C, leveraging hierarchical Binary Search Trees (BST) and mathematical set operations.

# Set-Theoretic Text Manipulation Engine (C-CLI)

A high-performance command-line interface (CLI) application written in C, designed to perform complex text extraction, tokenization, and parsing using mathematical set theory. 

The project evaluates and processes text data extracted from specific files and paragraphs by modeling textual elements as mathematical sets.

## 🚀 Key Features & Operations

The application supports **5 core set-theoretic operations** over text contents:
1. **Union:** Combines and aggregates textual elements from selected files or paragraphs without duplicates.
2. **Intersection:** Extracts common text data that exists across all selected files or paragraphs.
3. **Difference (\(A - B\) and \(B - A\)):** Isolates elements present in one specific text segment but completely absent from the other.
4. **Subset Verification (\(A \subseteq B\)):** Evaluates if a text segment's content is entirely included within another, explicitly checking for set equality.
5. **Complement (\(U - A\)):** Determines the relative complement of a file's content with respect to the universal set (\(U\)) of all loaded data.

## ⚙️ Granular Extraction Modes

You can dynamically configure the extraction criteria based on 4 different structural types:
- **Letters:** Character-by-character set distribution.
- **Words:** Standard text tokenization.
- **Consecutive Words (\(N\)-Grams):** Extracts sequences of \(N\) consecutive words, managing linguistic boundaries through smart separator priorities (e.g., punctuation like `.`, `!`, `?` break word adjacency).
- **Sentences:** Sentence-level extraction based on standard grammatical end-markers.

## 🛠️ Advanced Data Structures & Architecture

This engine is built entirely from scratch in **Pure C (C11)**, featuring custom low-level memory management and avoiding high-level library overhead. It uses a unique hierarchical data structure:
- **Files BST (Binary Search Tree):** Stores and sorts loaded filenames alphabetically.
- **Paragraphs BST:** Imbued inside each File node to track selected paragraph sequences.
- **Words BST:** Imbued inside each Paragraph node to store extracted tokens, ensuring fast \(O(\log n)\) search, intersection, and insertion times.
- **Iterative Stack-based Traversal:** Implements manual, non-recursive Inorder tree traversals using a custom Stack structure to optimize memory and prevent stack overflows on large files.
- **Singly Linked Lists:** Utilized as temporary sliding windows to parse and validate consecutive words.

## 📦 Getting Started

### Prerequisites
Ensure you have a C compiler (`gcc` or `clang`) and the Windows environment (the UI leverages `winapi` for console color mapping).

### Compilation
Clone the repository and compile the source files using GCC:
```bash
gcc G_05_AITMESSAOUD_SEDDARI.c -o textops
```

### Usage
1. Make sure your source text files are placed inside a folder named `File_Texts/` in the root directory.
2. Run the compiled executable:
   ```bash
   ./textops
   ```
3. Use the interactive menu to toggle case sensitivity, customize separator characters, add files, and perform set operations.

---
*Developed by Yanis AIT MESSAOUD & Mohamed Louay SEDDARI.*
