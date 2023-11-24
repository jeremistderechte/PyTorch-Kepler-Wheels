# PyTorch-Kepler-Wheels

For people who want to use their old Kepler GPUs for machine learning but don't want to deal with compiling PyTorch from source, here's the solution!

I am the proud owner of a Tesla K20 and a Tesla K40. The second card in particular is still quite suitable for basic ML tasks, as the card is equipped with a 12 GB GDDR5 memory buffer and can be found quite cheaply on sites like eBay or Aliexpress. So if you're on a budget or want to look back at Kepler for ML tasks, you've come to the right place.

Keep in mind that Kepler is now a decade old and doesn't support new features like accelerated FP16 or INT4/INT8 training/inference, but unlike Pascal (except GP100), you get the same FP16 performance as FP32 and you got still basic INT32 support, which is great. The FP64 is pretty good on the GK110 too, but not used in the ML, so not a big deal for our usecase.

Note that my versions are not compiled with AVX-2 in mind as I use IvyBridge server CPUs when running my Teslas. So this can lead to a small performance hit when computing on the CPU if your CPU supports AVX2.

## Currently supported architectures
- Kepler (only CUDA Compatibility 3.5, not 3.0 or 3.7)

## Downlaods

Ceck the [releases][download-link] page for downloads

[download-link]: https://github.com/jeremistderechte/PyTorch-Kepler-Wheels/releases
