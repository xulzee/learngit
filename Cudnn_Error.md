**CUDNN_STATUS_INTERNAL_ERROR**
**CUDNN_STATUS_BAD_PARAM**
**Check failed: stream->parent()->GetConvolveAlgorithms(&algorithms)**

Just for those who are driven mad by this:

I occasionally got a CUBLAS error as well. So I did this:
```bash {.line-numbers}
cd /usr/local/cuda/samples/7_CUDALibraries/simpleCUBLAS
sudo make
./simpleCUBLAS
```
and discovered that I could not initialise CUBLAS

So next I did this (based on advice)
```bash {.line-numbers}
sudo rm -rf ~/.nv
```
And it worked. Cheers.....thats 4 days wasted. Hope this saves someone else
