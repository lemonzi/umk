Universal MaKe
=============

Universal MaKe (`umk`) is a Makefile that allows easily transpiling, or converting, between different file formats. It has a syntax for the targets that allows things like:

```bash
umk pdf[README.md]
umk mp3[~/audio/recording.wav]
umk zip[~/data]
umk c[src/]
```

From there, modifiers can be appended:

```bash
umk pdf[README.md] open
umk mp3[~/audio/recording.wav] out[~/audio/mySong.mp3]
umk c[src/] out[myapp]
```

Most of the times it's just easier to type the original command, indeed. UMK targets two main use cases:

- Complex commands that are not that easy to type (out of laziness, most of the times). Especially if you type them often.
- Automatic compilation from programs that support Make, such as vim.

This syntax of `command[path]` was designed to be easy to type, clear, and not interfere with filenames or special characters. However, it disables path autocompletion. It could be better specify the command as a suffix, so that it's possible to autocomplete the path and then add it. Any suggestions?

Pull requests with more commands and converters are welcome! By design, new formats will introduce new dependencies. To see the available commands, have a look at the source.

Dependencies
-----------

- `pandoc`, for most document conversions
- `ffmpeg`, for most audio and video conversions
- `zip`, for zipping folders
- a valid `$(CC)`, for compiling C and C++
- `open`, an OSX built-in, for the open modifider

How to use it?
--------------

There are two possible ways:

- Link to `umk` from somewhere in your PATH and run it as a standalone, or
- Use make with `make -f path/to/umk`.

