# Speech feature
Feature extraction is the front-end process of automatic speech recognition.  
Extracting good speech feature is very important because this process significantly affects the subsequenct process such as acoustic modelling  
There are lots of speech features in automatic speech recognition, and it is also important to extract feature which is appropriate to the task.  
In this part, I will explain six speech features based on the paper [Some Commonly Used Speech Feature Extraction Algorithms](https://prod-com-bibliolabs-nuvique-app-content.s3.amazonaws.com/SID-0000000594821/SID-0000000594821.pdf?X-Amz-Security-Token=IQoJb3JpZ2luX2VjEHwaCXVzLWVhc3QtMSJGMEQCIGRS1byTpIvu329LpHbamSzOTWRk0%2FsWt3ytNwvHxkoIAiB7HqihBzDqrt7qhkTMNljHFOQNt2d044fs%2FDkTj3%2BZwyr3AwhFEAAaDDAwNjg0ODA5MTAxNCIM4KeikocHjSowAryZKtQDmjnJBaM50%2FuAc1S6geOT4e%2BTBA3h5k4SeKDALToO8cpgdDiCZgo61p0c9Pdacya38to2X8ooQZEJD%2BqA5g0U4oUIiprOy4GIfY834rdPBZKgqswxz8CPSQPiQc6rMjf6jO%2BMQV%2Fbxx6JXnWAXNCAXslY9eQ7E7aMfo%2BEplTBbR2BLcxFz58oJfmXHQq%2Bn0GnoxmexQSSIPjLnggwJz%2F2bvaDlvULf1NZtzle4cqRBhLmqV%2FYW9Vy%2FAgAhw8I%2BYdMTRSWqMsb8GrynBfL9L5HhvB%2Bil2h%2BCcISoeEpc5YXZfsG8haUZMrxiQhAjfpJ7qRsGm7%2BBrxxEoGtCmEz1ky7azv896C6ny276NS44pxChLUzjxzhxz7bTtvjCHp2n7b3R4hDHcyeLxIFcTqyze8OODyseFPib4NfAluQStM1RwlVlavo%2FpoFyCZ4NdwIZgiMuogfnHd554zE7XkRMYnltiQORcbBa8lyq3ISRKmidgd0VlJAYJj8%2B0qsUkU%2BZE5CqwLiqASe4D88ALTKtuK5btyFFs13H%2BRQlEp2XuiX873y37uSE9Uj2F%2BEX44ysAyd513LnbhIwfvB7snYcDmaGp5SXwQIvIVa8FlbSPj%2FM60O1H0MNSh84wGOqYBjz1idVsh4NBaOXyNAypk8%2B9FbTeCVPzyW0i7AleB9eOI%2F3NcgxH4ICBi%2B%2BgdU1m1nBfiO%2BlktpLYKrxoAVsgFvBxCn%2BTOvEwxeipdYurQdMFjwpmERI8cGtftGUSbQ4hN6N0E4qeaLTAsiSUrbqPtN7Hc2MRk4byrGF4y%2BAb%2FnfRREWEjwEK7aWq25TQMtJUtGfo5ulqzmuwje%2FVJjIrGD59OBnk2w%3D%3D&X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Date=20211123T132511Z&X-Amz-SignedHeaders=host&X-Amz-Expires=120&X-Amz-Credential=ASIAQDGBNSODLSK2GOMK%2F20211123%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Signature=8e7bdc39c8ba4a822a335cd2de84d5b484bbd3950f93cbc0db8bd02badcb2b3a)
1. Mel Frequency Cepstral Coefficients (MFCC)
2. Linear Prediction Coefficients (LPC)
3. Linear Prediction Cepstral Coefficients (LPCC)
4. Line Spectrral Frequencies (LSF)
5. Discrete Wavelet Transform (DWT)
6. Perceptual Linear Prediction (PLP)


## Mel Frequency Cepstral Coefficients (MFCC)
MFCC computation is a replication of the human hearing system.  
MFCC features are rooted in the recognition discrepancy of the human ear's bandwidths with frequency filters spaced linearly at low frequencies and logarithmically at high frequencies. The mel-frequency scale has linear frequency spacing below 1000 HZ and logarithmic spacing above 1000 HZ. MFCC is based on signal disintegration with the help of a filter bank.  
The first step of extracting MFCC is windowing the speech signal to split the speech signal into frames. Since the high frequency formants process reduced amplitude compared to the low frequency formants, hifh frequencies are emphasized to obtain similar amplitude for all the formants.  
After windowing, Fast Fourier Transform (FFT) is applied to find the power spectrum of each frame.  
And then, the filter bank processing is carried out on the power spectrum using mel-scale. After the Mel-filter bank, we can get Mel-spectrogram, and it is also commonly used for the automatic speech recognition  
Discrete Cosine Transform (DCT) is applied to the speech signal after translating the power spectrum to lof domain in order to calculate MFCC.  
MFCC can effectively denote the low frequency region, so it can compute formants that are in the low frequency range and descrive the vocal tract resonances.  

## Linear Prediction Coefficients (LPC)
LPC imitates the human vocal tract and gives robust speech features.  
It evaluates the speech signal by approximating the formants, getting rid of its effects from the speech signal and estimate the concentration and frequency of the left behind residue.  
The positions of the formants in a speech signal are predictable by calculating the linear predictive coefficients and finding the crests in the spectrum of the subsequent linear prediction filter.  
LPC is helpful in the encoding of high quality speech at low bit rate.  
Linear prediction is applied to obtain the filter coefficients equivalent to the vocal tract by reducing the mean square error between the input speech and estimated speech.  
Linear prediction analysis of speech signal forecasts any given speech sample at a specific period as a linear weighted aggregation of preceding samples.  
Each frame of the windowed signal is autocorrelted, and it is followed by the LPC analysis, where each frame of the autocorrelations is converted into LPC parameters set which consists of the LPC coefficients.   

## Linear Prediction Cepstral Coefficients (LPCC)
LPCC are cepstral coefficients derived from LPC calculated spectral envelope. LPCC are the coeffients of the Fourier transform illustration of the logarithmic magnitude spectrum of LPC.  
LPCC are able to perfectly symbolize speech waveforms and characteristics with a limited size of features.  
LPCC analogous to LPC, are computed from sample points of a speech waveform.  
LPCC have low vulnerability to noise. LPCC features yiled lower error rate as compared to LPC features.  

## Line Spectrral Frequencies (LSF)
LSF defines the two resonance situations taking place in the inter-connected tube model of the human vocal tract: nasal cavity and oral cavity.  
LSF has been realized that this illustration has an improved quantization features than the other linear prediction parametric illustrations.  
The LSF illustration has the capacity to reduce the bit-rate by 25-30% for trasmitting the linear prediction without distorting the quality of synthesized speech.  
In order to compute LSF coefficients, an inverse polymonial filter is split into two polynominals P(z) and Q(z), where P(z) is the vocal tract with the glottis closed, Q(z) is the LPC analysis filter of order p.  
The most prominent application of LSF is in the area of speech compression. The advantages of LSF include their ability to localize spectral sensitivities, the fact that they charcterize bandwidths and resonance locations and lays emphasis on the important aspect of spectral peak location.  
LSF plays an important role in the transmission of vocal tract information from speech coder to decoder with their widespread use being a result of their excellent quantization properties.

## Discrete Wavelet Transform (DWT)
Wavelet Transform (WT) theory is centered around signal analysis using varing scales in the time and frequency domains. WT permits high-frequency events identification with an enhanced temporal resolution.  
A wavelet is a waveform of effectively limited duration has an average value of zero. Many wavelets also display orthogonality, and ideal feature of compact signal representation.  
WT is a signal processing technique that can be used to represent resl-life non-stationary signals with high efficiency.  
Continuous WT is used to split a continuous-time function into wavelets. However, there is redundancy of information and huge computational efforts is required to calculate all likely scales and translations of CWT.  
DWT is an extension of the WT that enhances the flexibility to the decomposition process. It was introduced as a highly flexible and efficient method for sub band breakdown of signals.  
WT decomposes a signal into a group of basic functions called wavelets. Wavelets are obtained from a single prototype wavelet called mother wavelet by dilations and shifting.  
The scaling and wavelet functions can be inplemented effectively using a pair of filters, h[n] and g[n].  The input signal is filtered by a low=pass filter and high-pass filter to obtain the approximate components and the detail components respectively.  
The approximate signal at each stage is further decomposed using the same low-pass and high-pass filters to get the approximate and detail components for the next stage. This type of decomposition is called dyadic decomposition.  
The DWT parameters contain the information of different frequeny scales. This enhances the speech information obtained in the corresponding frequency band.  

## Perceptual Linear Prediction (PLP)
PLP combines the critical bands, intensity-to-loudness compression and equal loudness pre-emphasis in the extraction of relevant information from speech.  
PLP gives a representation conforming to a smoothed short-term spectrum that has been equalized and compressed similar to the human hearing making it similar to the MFCC.  
In the PLP approach, several prominent features of hearing are replicated and the consequent auditory like spectrum of speech is approximated by an autoregressive all-pole model.  
PLP gives minimized resolution at high frequencies that signifies auditory filter band based approach, yet gives the orthogonal outputs that are similar to the cepstral analysis. It uses linear predictions for pectral smoothing. PLP is a combination of both spectral analysis and linear prediction analysis.  
In order to compute PLP features, the speech is windowed by Hamming window, then the FFT and the square of the magnitude are computed. A trapezoidal filter is applied at 1-bark interval to integrate the overlapping critical band filter responses in the power spectrum.  
This effectively compresses the higher frequencies into a narrow band. The symmetric frequency domain convolution on the bark warped frequency scale then permits low frequencies to mask the high frequencies, concurrently smoothing the spectrum. The spectrum is subsequently pre-emphasized to approximate the uneven sensitivity of human hearing at a variety of frequencies.  
The spectral amplitude is compressed, this reduces the amplitude variation of the spectral resonances. An Inverse Discrete Fourier Transform (IDCT) is performed to get the autocorrelation coefficients. Spectral smoothing is performed, solving the autoregressive equations. The autoregressive coefficients are converted to cepstral variables.