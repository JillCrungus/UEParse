## Unreal Engine 4 Asset Parser

Generic Unreal Engine 4 asset parser.

Based on an earlier commit of https://github.com/SirWaddles/JohnWickParse from before Fortnite-specific code was added that broke compatibility with other games.

Designed to be generic but has explicit support for various games. Track compatibility here:
https://github.com/JillCrungus/UEParse-Game-Support

## Original README:

This program is able to parse pak, uexp and uasset files, and offers way to manage them.

It offers four commands that can read these files
 * `serialize <asset_path>` will turn a uexp/uasset pair into a .json file, reading the UObject properties. `<asset_path>` has no extension.
 * `filelist <pak_path>` will create a text file, listing all of the files contained in a .pak file.
 * `extract <pak_path> <pattern>` will extract all of the files where `<pattern>` is in the internal path name, into the corresponding directory in the current working folder.
 * `texture <asset_path>` will convert a DXT5 asset file into a png image file.

Any operations on a pak file require that the `key.txt` file contains the encryption key for the pak file, as a hexadecimal string and no leading newline.

Note however that there is limited support for all of the properties that can be serialized, and the parser may panic if it attempts to parse an unknown tag type.
