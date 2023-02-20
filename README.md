# Extract-extension-from-filename
 
get_extension('') // ""
get_extension('name') // ""
get_extension('name.txt') // "txt"
get_extension('.htpasswd') // ""
get_extension('name.with.many.dots.myext') // "myext"
The following solution may extract file extensions from full path:
function get_extension(path) {
 var basename = path.split(/[\\/]/).pop(), // extract file name from full path ...
 // (supports `\\` and `/` separators)
 pos = basename.lastIndexOf('.'); // get last position of `.`
 if (basename === '' || pos < 1) // if file name is empty or ...
 return ""; // `.` not found (-1) or comes first (0)
 return basename.slice(pos + 1); // extract extension ignoring `.`
}
get_extension('/path/to/file.ext'); // "ext"
