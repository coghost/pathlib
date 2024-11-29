# pathlib

`pathlib` is a Go package that provides an object-oriented interface for working with filesystem paths. It's inspired by Python's `pathlib` module and aims to simplify file and directory operations in Go.

## Features

- Object-oriented path manipulation
- Cross-platform path handling
- Easy file and directory operations
- Support for glob patterns
- CSV and TSV file reading
- Path expansion (environment variables and user home directories)

## Installation

To install the `pathlib` package, use the following command:

```bash
go get github.com/coghost/pathlib
```

## Usage

Here are some examples of how to use the `pathlib` package:

```go
import "github.com/coghost/pathlib"

// Create a new path
p := pathlib.Path("/home/user/documents/file.txt")

// Get path components
fmt.Println(p.Name)  // "file.txt"
fmt.Println(p.Stem)  // "file"
fmt.Println(p.Suffix)  // ".txt"

// Path operations
parent := p.Parent()
newPath := p.WithName("newfile.txt")
relativePath, _ := p.RelativeTo("/home/user")

// File operations
content, _ := p.ReadText()
p.WriteText("Hello, World!")
p.AppendText("\nNew line")

// Directory operations
p.MkDirs()
files, _ := p.ListFilesWithGlob("*.txt")

// CSV/TSV operations
data, _ := p.CSVGetSlices()
```

## Main Types and Functions

- `FsPath`: The main type representing a file system path
- `Path(string) *FsPath`: Create a new FsPath instance
- `Home() (*FsPath, error)`: Get the user's home directory
- `Cwd() (*FsPath, error)`: Get the current working directory
- `Expand(string) string`: Expand environment variables and user home directory in a path

## Contributing

Contributions to `pathlib` are welcome! Please submit issues and pull requests on GitHub.

## License

This project is licensed under the MIT License - see the LICENSE file for details.
