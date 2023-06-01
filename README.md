# JPEG-image-compression
This repo contains JPEG image compression program implmented in Jupyter Notebook. 

1. It first applies $8 \times 8$ Standard quantization Matrices on DFT of the input image to have more reptetive
values (fewer number of unique values).
2. Then uses ZigZag encodning such that $8\times8$ block is converted to $1\times64$ array containing DC values on the left side, and AC values (mostly zeros) on the right bottom corner.

