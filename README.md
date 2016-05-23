Convert bitmaps into Unicode Braille dot patterns.
===

This program converts bitmaps into Braille dots and takes advantage
of the fact that the entire 256 possible pattern of dots is in the
Unicode Code Page U+2800.

For a tweet the maximum size is 140 chars and each 2x4 dot is a single
"character".  As a 32x32 square it is about right.

Roughly square that is almost 19x7 chars + 7 newlines = 38x28 dots

Sample tweets are at https://twitter.com/unicodedots

    ⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⠿⠛⠛⠛⠻⢿⣿⣿⣿⢿ ⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢀⣠⣤⣤⣤⣀⠀⠀⣀⡀
    ⣿⡏⠙⢿⣿⣿⣿⣿⣿⣿⣿⣿⡿⠁⠀⠀⠀⠀⠀⠀⠉⠉⣠⣿ ⠀⠀⣾⣷⣄⠀⠀⠀⠀⠀⠀⠀⣴⣿⣿⣿⣿⣿⣿⣿⣿⣟⡤
    ⣿⡄⠀⠀⠙⢿⣿⣿⣿⣿⣿⣿⠃⠀⠀⠀⠀⠀⠀⠀⠀⠀⢡⣾ ⠀⠀⢿⣿⣿⣷⣦⣄⣀⠀⠀⢰⣿⣿⣿⣿⣿⣿⣿⣿⣿⠋
    ⣿⣧⠀⠀⠀⠀⠈⠙⠛⠿⠿⣿⠀⠀⠀⠀⠀⠀⠀⠀⠀⢰⣿⣿ ⠀⠀⣌⣻⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⡿
    ⣿⡛⠷⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢸⣿⣿ ⠀⠀⠻⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⡇
    ⣿⣧⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣼⣿⣿ ⠀⠀⠀⢙⣻⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⡟
    ⣿⣿⣷⣄⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢰⣿⣿⣿ ⠀⠀⠀⠀⠻⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⠟
    ⣿⣿⣿⡍⠉⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢠⣿⣿⣿⣿ ⠀⠀⠀⠀⠀⢈⣩⣿⣿⣿⣿⣿⣿⣿⣿⣿⠿⠃
    ⣿⣿⣿⣿⣦⣀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣠⣿⣿⣿⣿⣿ ⠀⠐⠲⢾⣿⣿⣿⣿⣿⣿⣿⣿⣿⠿⠛⠁
    ⣿⣿⣿⣿⣿⡿⠟⠁⠀⠀⠀⠀⠀⠀⠀⠀⢀⣼⣿⣿⣿⣿⣿⣿ ⠀⠀⠀⠀⠀⠉⠉⠉⠉⠉⠉
    ⣿⣟⡛⠉⠁⠀⠀⠀⠀⠀⠀⠀⠀⢀⣤⣶⣿⣿⣿⣿⣿⣿⣿⣿
    ⣿⣿⣿⣷⣶⣤⣤⣤⣤⣤⣴⣶⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿

Tools like `jp2a` can be used to convert the images into a format
suitable for `bitmap2braille` to convert them.

    jp2a --invert --size=48x48 twitter.jpg | ./bitmap2braille
