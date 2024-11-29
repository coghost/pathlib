## TODO
add new func has same function with python pathlib.Path
`mkdir()`, `touch()`, `chmod()`

## todo

https://docs.python.org/zh-cn/3/library/pathlib.html#pathlib.PurePath.suffixes
To compare the functionality of your Go implementation with Python's `pathlib.Path`, I'll list the main methods available in Python's `pathlib.Path` and indicate which ones are missing or partially implemented in your Go version. Here's a comparison:

```
Enhance pathlib: Add new methods and improve existing functionality

- Implement Mkdir, Touch, Chmod, Unlink, and Rmdir methods
- Add WithRenamedParentDir and WithSuffixAndSuffixedParentDir methods
- Improve Parents method to return all parent directories
- Update JoinPath to handle absolute paths correctly
- Add comprehensive test cases for new and existing methods
- Update README with new features and usage examples
- Add TODO list for future improvements and Python pathlib compatibility
```


Missing or not fully equivalent:
1. `__truediv__` (/ operator for path joining)
2. `anchor`
3. `drive`
4. `root`
5. `as_posix()`
6. `as_uri()`
7. `is_absolute()`
8. `is_reserved()`
9. `match()`
10. `glob()`
11. `rglob()`
12. `absolute()`
13. `resolve()`
14. `stat()`
15. `owner()`
16. `group()`
17. `open()`
18. `read_text()`
19. `read_bytes()`
20. `write_text()`
21. `write_bytes()`
22. `touch()`
23. `mkdir()`
24. `chmod()`
25. `lchmod()`
26. `unlink()`
27. `rmdir()`
28. `lstat()`
29. `symlink_to()`
30. `hardlink_to()`
31. `readlink()`
32. `rename()`
33. `replace()`
34. `samefile()`
35. `iterdir()`

Some methods that are missing in your Go implementation might not be directly applicable or necessary in Go due to language differences. However, adding some of these methods could make your `FsPath` type more feature-complete and closer to Python's `pathlib.Path`.

Key areas to consider implementing:
1. File system operations (mkdir, chmod, touch, etc.)
2. File reading and writing methods
3. Path resolution and normalization
4. Glob and pattern matching
5. Symlink handling
6. Directory iteration

Remember that some of these operations might already be available through the `afero.Fs` interface that your `FsPath` type uses, so you may just need to add wrapper methods to expose this functionality.
