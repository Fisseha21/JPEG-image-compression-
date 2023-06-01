# JPEG-image-compression
This repo contains JPEG image compression program implmented in Jupyter Notebook. 
### Compression ###
1. It first applies $8 \times 8$ _Standard quantization Matrices_ on DFT of the input image to have more reptetive
values (fewer number of unique values).
2. Then uses _ZigZag_ encodning such that the $8\times8$ block is converted to $1\times64$ array containing DC values on the left side, and AC values (mostly zeros) on the right bottom corner.
3. Apply _RLE encoding_ on the _zigZag_ encoded array such that repeting neighbouring points are stored with their value and its number of occurances (frequencies).
  _E.g._ $[2,2,2,2,2]$ is stored as $[5,2]$ implying that there are $5$ $2s$. 
4. Apply Huffman coding on the RLE encoded array.
 ### Decompression ###
1. Decode the huffman coded array _(in bytes)_ to reconstruct it to _RLE encoded_ form.
2. Apply _RLE decoding_ on the decoded huffman values to reconstruct to _ZigZag_ array.
3. Apply _ZigZag_ decoding to reconstruct reconstructed DCT frquency values.
4. Apply inverse DCT on each $8 \times 8$ block to reconstruct each $8 \times 8$ image blocks.
5. Merge each reconstructed $8 \times 8$ blocks such that the reconstructed image is formed. 
