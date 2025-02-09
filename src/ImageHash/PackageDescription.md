# ImageHash

Perceptual image hashing using the ImageSharp library. Includes three hashing algorithms (AverageHash, DifferenceHash, and PerceptualHash).
See [github](https://www.github.com/coenm/ImageHash/) for more information.

## Calculate image hash

<!-- snippet: CalculateImageHash -->
<a id='snippet-CalculateImageHash'></a>
```cs
var hashAlgorithm = new AverageHash();
// or one of the other available algorithms:
// var hashAlgorithm = new DifferenceHash();
// var hashAlgorithm = new PerceptualHash();

string filename = "your filename";
using var stream = File.OpenRead(filename);

ulong imageHash = hashAlgorithm.Hash(stream);
```
<sup><a href='/tests/ImageHash.Test/Examples.cs#L14-L26' title='Snippet source file'>snippet source</a> | <a href='#snippet-CalculateImageHash' title='Start of snippet'>anchor</a></sup>
<!-- endSnippet -->

## Calculate image similarity
Note that to calculate the image similarity, both image hashes should have been calculated using the same hash algorihm.

<!-- snippet: CalculateSimilarity -->
<a id='snippet-CalculateSimilarity'></a>
```cs
// calculate the two image hashes
ulong hash1 = hashAlgorithm.Hash(imageStream1);
ulong hash2 = hashAlgorithm.Hash(imageStream2);

double percentageImageSimilarity = CompareHash.Similarity(hash1, hash2);
```
<sup><a href='/tests/ImageHash.Test/Examples.cs#L35-L43' title='Snippet source file'>snippet source</a> | <a href='#snippet-CalculateSimilarity' title='Start of snippet'>anchor</a></sup>
<!-- endSnippet -->
