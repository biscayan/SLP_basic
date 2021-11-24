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

## Linear Prediction Cepstral Coefficients (LPCC)

## Line Spectrral Frequencies (LSF)

## Discrete Wavelet Transform (DWT)

## Perceptual Linear Prediction (PLP)