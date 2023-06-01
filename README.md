# JPEG-image-compression
This repo contains JPEG image compression program implmented in Jupyter Notebook. 

1. It first applies $8 \times 8$ _Standard quantization Matrices_ on DFT of the input image to have more reptetive
values (fewer number of unique values).
2. Then uses _ZigZag_ encodning such that $8\times8$ block is converted to $1\times64$ array containing DC values on the left side, and AC values (mostly zeros) on the right bottom corner.
3. Apply _RLE encoding_ on the _zigZag_ encoded array such that repeting neighbouring points are stored with their value and its number of occurances (frequencies).
  _E.g._ $[2,2,2,2,2]$ is stored as $[5,2]$ implying that there are $5$ $2s$. <span style="color:blue">some *blue* text</span>
4. Apply Huffman coding on the RLE encoded array.
5.  

