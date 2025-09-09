<script src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>
# Spectral Estimation Methods

## Windowed Periodogram

The **windowed periodogram** is a widely used technique for estimating the _Power Spectral Density (PSD)_ of a signal. It enhances the classical periodogram by mitigating spectral leakage through the application of a windowing function. This technique is essential in signal processing for accurate frequency-domain analysis.

### Classical Periodogram

The periodogram is a non-parametric PSD estimation method based on the Discrete Fourier Transform (DFT):

\[
P_x(f) = \frac{1}{N} \left| X(f) \right|^2
\]

Where:

- \(X(f)\) : DFT of the signal \(x[n]\)  
- \(N\) : Signal length  

However, the classical periodogram suffers from **spectral leakage** due to abrupt truncation of the signal.

### Windowing to Mitigate Spectral Leakage

Spectral leakage can be minimized by applying a **window function** \(w[n]\) to the signal before computing the DFT. The resulting PSD estimate is called the _windowed periodogram_:

\[
P_w(f) = \frac{1}{N \cdot U} \left| X_w(f) \right|^2
\]

Where:

- \(w[n]\) : Window function  
- \(X_w(f)\) : DFT of the windowed signal \(x[n] \cdot w[n]\)  
- \(U = \frac{1}{N} \sum_{n=0}^{N-1} |w[n]|^2\) : Normalization factor

### Common Window Functions

- **Rectangular Window:** Equivalent to the classical periodogram  
\[
w[n] =
\begin{cases}
1, & 0 \le n \le N-1 \\
0, & \text{otherwise}
\end{cases}
\]

- **Hamming Window:** Reduces sidelobe amplitudes  
\[
w[n] = 0.54 - 0.46 \cos\left(\frac{2 \pi n}{N-1}\right), \quad 0 \le n \le N-1
\]

- **Hanning Window:** Provides smoother transitions  
\[
w[n] = 0.5 \left(1 - \cos\left(\frac{2 \pi n}{N-1}\right)\right), \quad 0 \le n \le N-1
\]

### Implementation Steps

1. **Segment the Signal:** Divide the signal into overlapping or non-overlapping segments of length \(N\).  
2. **Apply a Window Function:** Multiply each segment by a window function \(w[n]\).  
3. **Compute the DFT:** Calculate the DFT of the windowed segments.  
4. **Average the Periodograms:** For overlapping segments, average the periodograms to reduce variance.

### Applications

- Signal Processing: Analyzing frequency content of time-varying signals.  
- Communications: Evaluating spectrum occupancy in wireless systems.  
- Bioinformatics: Investigating periodicities in biological signals (e.g., EEG, ECG).  
- Seismology: Characterizing seismic wave frequencies.



## Correlogram

The **Correlogram** method estimates the PSD based on the Fourier Transform of the estimated autocorrelation function.

### PSD via Autocorrelation

\[
S_x(f) = \sum_{k=-N+1}^{N-1} R_x[k] e^{-j 2 \pi f k}
\]

Where \(R_x[k]\) is the autocorrelation function of the discrete-time signal.

### Autocorrelation Function

For a discrete-time signal \(x[n]\):

\[
R_x[k] = \frac{1}{N} \sum_{n=0}^{N-1-k} x[n] x^*[n+k]
\]

Where \(k\) is the lag.

### Implementation Steps

1. Estimate autocorrelation.  
2. Apply a window to the autocorrelation sequence.  
3. Compute the Fourier Transform to estimate the PSD.

### Windowing in Correlogram

- **Rectangular Window:** No additional processing.  
- **Hamming Window:** Reduces sidelobes.  
- **Hanning Window:** Smooth transitions at edges.

### Advantages

- Simple to implement.
- Provides insight into the frequency-domain characteristics of signals.

### Limitations

- Limited frequency resolution due to finite data length.
- Potential for spectral leakage if no windowing is applied.

### Applications

- Analyzing stationary signals in time-series data.
- Frequency-domain analysis in communication systems.
- Studying periodic patterns in biological signals.



## Bartlett Method

Estimate PSD by segmenting the signal, computing periodograms, and averaging:

\[
P_x(f_k) = \frac{1}{M} \sum_{m=0}^{M-1} |X_m[k]|^2
\]

Where \(X_m[k]\) is the DFT of the m-th segment, \(M\) is the number of segments.

### Implementation Steps

1. Segment the signal into M non-overlapping parts.
2. For each segment, calculate the periodogram.
3. Average the periodograms of all segments:

### Advantages

- Reduces variance in PSD estimation compared to a single periodogram.
- Simple to implement.

### Limitations

- Loss of frequency resolution due to segmenting the signal.
- Bias may remain if the signal is not stationary within segments.

### Applications

- Analyzing frequency content in stationary signals.
- Estimating PSD in communication systems.



## Blackman-Tukey Method

Estimate PSD using autocorrelation and windowing:

\[
P_x(f) = \text{FFT}\{ R_x[k] \cdot w[k] \}
\]

Where \(w[k]\) is the window function applied to autocorrelation \(R_x[k]\).

### Implementation Steps

1. Compute the Autocorrelation
2. Apply a Window Function
3. Perform Fourier Transform

### Advantages

- Reduces spectral leakage through windowing.
- Smoothens the power spectral estimate, reducing variance.
- Flexibility in choosing different window functions (e.g., Hamming, Hanning, Blackman).

### Limitations

- Lower frequency resolution due to windowing effects.
- Computationally expensive for large signals.
- Accuracy depends on the choice of window length and type.

### Applications

- Analysis of radar and sonar signals.
- Audio and speech signal processing.
- Power spectral density estimation in communications systems.



## Welch Method

Improves periodogram estimation by segmenting, windowing, and averaging:

\[
P_{xx}(f) = \frac{1}{K} \sum_{k=0}^{K-1} \left| \text{FFT}\{ x_k[n] \cdot w[n] \} \right|^2
\]

Where:

- \(K\) : Number of segments  
- \(L\) : Length of each segment  
- \(w[n]\) : Window function  
- \(x_k[n]\) : kth segment of the signal

### Implementation Steps

1. Divide the signal into overlapping segments (typically 50% overlap)
2. Apply a window (e.g., Hamming or Blackman) to each segment to reduce spectral leakage.
3. For each segment, compute the periodogram using the Fast Fourier Transform (FFT).
4. Average the periodograms of all segments to obtain the final PSD estimate.

### Advantages

- Reduces variance by averaging multiple segments.
- Allows flexibility in segment length, overlap, and window choice.
- Minimizes spectral leakage with windowing.

### Limitations

- Lower frequency resolution due to overlap and windowing.
- Increased computational cost for larger signals.

### Applications

1. Communications & Wireless Systems
2. Biomedical Signals (EEG, ECG, EMG)
3. Audio & Speech Processing
4. Mechanical & Vibration Analysis
5. Radar & Sonar
