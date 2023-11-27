# PyTorch-Kepler-Wheels

For people who want to use their old Kepler GPUs (3.5) for machine learning but don't want to deal with compiling PyTorch from source, here's the solution! Currently (Nov. 2023) the prebuilt PyTorch package only supports CUDA Capability 3.7 and later, so only the GK210 (Tesla K80) from the Kepler generation. If you're using a GPU newer than 3.5, just use the offical package. First gen Kepler (3.0) builts are far more challenging, because they DO NOT support CUDA 11.x and therefore not the C++17 standard, which is used in PyTorch, you can still try to build older PyTorch versions that used an older C++ standard. But first gen Kepler cards are pretty much useless, because of the lack of high memory buffers, way fewer cuda cores and missing features compared to 3.5, better stick to Colab or CPU :-D.

I am the proud owner of a Tesla K20 and a Tesla K40. The second card in particular is still quite suitable for basic ML tasks, as the card is equipped with a 12 GB GDDR5 memory buffer and can be found quite cheaply on sites like eBay or Aliexpress. So if you're on a budget or want to look back at Kepler for ML tasks, you've come to the right place.

Keep in mind that Kepler is now a decade old and doesn't support new features like accelerated FP16 or INT4/INT8 training/inference, but unlike Pascal (except GP100), you get the same FP16 performance as FP32 and you got still basic INT32 support, which is great. The FP64 is pretty good on the GK110 too, but not used in ML, so not a big deal for our usecase.

Note that my versions are not compiled with AVX-2 in mind as I use IvyBridge server CPUs when running my Teslas. So this can lead to a small performance hit when computing on the CPU if your CPU supports AVX2.

![nvidia-smi_torch](https://github.com/jeremistderechte/PyTorch-Kepler-Wheels/assets/116145963/21a02a3c-264a-41a1-905f-fef3145892b4)


![torch2](https://github.com/jeremistderechte/PyTorch-Kepler-Wheels/assets/116145963/01558537-9e72-467e-9f4d-c69d59f834b3)



## Currently supported architectures
- Kepler (only CUDA Compatibility 3.5, not 3.0 nor 3.7)

### Compatibility table

| CUDA Capability  | GPUs | Graphics Cards |
| ------------- | ------------- | ------------- |
| 3.5  | GK110, GK208  | GeForce GTX TITAN Z, GeForce GTX TITAN Black, GeForce GTX TITAN, GeForce GTX 780 Ti, GeForce GTX 780, GeForce GT 640 (GDDR5), GeForce GT 630 v2, GeForce GT 730, GeForce GT 720, GeForce GT 710, GeForce GT 740M (64-bit, DDR3), Quadro K6000, Quadro K5200, Tesla K40, Tesla K20x, Tesla K20  |

Source: [Wikipedia][cuda-list]


## Downloads

Check the [releases][download-link] page for downloads!

[download-link]: https://github.com/jeremistderechte/PyTorch-Kepler-Wheels/releases
[cuda-list]: https://de.wikipedia.org/wiki/CUDA
