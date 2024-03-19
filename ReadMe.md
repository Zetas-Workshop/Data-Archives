# Data Archives

This repo contains the latest `data.i` file for GranBlue Fantasy: Relink along with some previous versions. The main purpose of this is to serve as an easy to access source of clean `data.i` files for restoring to if a user no longer has a clean file on their machine.

Files are sorted by date (`YYYY-MM-DD`) they were last updated. Not every client update includes a `data.i` update so they are not associated with any specific version. Additionally, a `Files.json` file exists at the root of the directory. This contains the relative path (`File`) to each `data.i` file and the CRC32 Big Endian Hash (`Hash_CRC32`) of the file. Parsing this file can help programmatically locate the latest desirable file and ensure the user has a clean copy to work with prior to modding.

## Note

Since the CRC32 is in Big Endian the following example will result in the expected ordering:

```csharp
var fileBytes = System.IO.File.ReadAllBytes("data.i");
var hash = System.IO.Hasing.Crc32.Hash(fileBytes);
Array.Reverse(hash);
var str = System.Convert.ToHexString(hash);
```
