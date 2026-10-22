
# Linear vs Circular Convolution in Practical Audio Filtering

A Digital Signal Processing (DSP) mini-project by **Aryan Kulkarni**, ECE-AIML, DES Pune University.

## 📌 Project Overview

This project compares linear convolution with circular convolution and demonstrates how zero-padding helps FFT-based convolution produce the correct linear-convolution output.

Convolution is an important operation in Digital Signal Processing and is widely used in digital filtering and signal processing applications.

## 🎯 Objectives

- Compare direct linear convolution and FFT-based convolution.
- Understand wraparound error in circular convolution.
- Demonstrate the importance of zero-padding.
- Find the minimum FFT length required for an accurate result.
- Compare execution times of direct and FFT-based convolution.

## ⚙️ Technologies Used

- Python
- NumPy
- SciPy
- Pandas
- Matplotlib
- Jupyter Notebook / Google Colab

## 🧪 Methodology

1. Generate an input signal containing two sinusoidal components with 64 samples.
2. Define a five-sample impulse response: `[1.0, 0.5, 0.25, -0.1, 0.05]`.
3. Calculate the reference output using direct linear convolution.
4. Compare it with 64-point circular convolution.
5. Apply zero-padding and repeat the FFT calculation using 68 points.
6. Evaluate the errors and compare execution times.

## 📊 Key Results

| Experiment | Result |
|---|---|
| Input signal length | 64 samples |
| Impulse response length | 5 samples |
| Full linear output length | 68 samples |
| Circular convolution at N = 64 | Wraparound error observed |
| Zero-padded FFT at N = 68 | Matches linear convolution to numerical precision |
| Larger FFT lengths tested | 79, 96 and 128 |

The RMSE for the 64-point circular convolution was approximately **0.0259**. After zero-padding to 68 points, the RMSE fell to approximately **2.69 × 10⁻¹⁶**, which is effectively zero for practical purposes.

In the recorded runtime experiment, direct convolution was faster than FFT-based convolution for all tested input lengths. Execution times depend on the hardware and implementation.

## 💡 Conclusion

This project demonstrates that an insufficient FFT length can cause circular wraparound error. Zero-padding to at least the full linear-convolution length solves this problem. It also shows that FFT-based convolution is not always faster for short signals.

## 🚀 Future Improvements

- Test the methods using a real audio recording.
- Explore low-pass, high-pass and band-pass filters.
- Compare frequency spectra before and after filtering.
- Test longer signals and impulse responses.
- Explore overlap-add and overlap-save methods.

## 📚 References

- Oppenheim and Schafer, *Discrete-Time Signal Processing*, 3rd Edition, 2010.
- Cooley and Tukey, *An Algorithm for the Machine Calculation of Complex Fourier Series*, 1965.
- NumPy documentation: https://numpy.org/doc/
- SciPy documentation: https://docs.scipy.org/doc/scipy/

---

**Author:** Aryan Kulkarni  
**Branch:** ECE-AIML  
**Institution:** DES Pune University

