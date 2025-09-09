<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
</head>
<body>
  <ul>
    <li>
      <strong>Input Parameters:</strong>
      <ul>
        <li><strong>Input Signal(s):</strong> Enter the signal frequency (Hz), sampling frequency (Hz), and the signal length. For rectangular or triangular pulse signals, also specify the pulse width in seconds.</li>
        <li><strong>Window Type:</strong> Select a window type (e.g., Rectangular, Hann, Hamming) from the dropdown menu, and provide the window size.</li>
        <li><strong>SNR (in dB):</strong> Enter the desired Signal-to-Noise Ratio (SNR) in decibels (dB).</li>
      </ul>
    </li>
    <br/>
    <h3><strong>Steps:</strong></h3>
    <li>
      <strong>1. Generate Input Signal(s):</strong> 
      Click the <em>“Generate Input Signal”</em> button to create the input signal. Choose a base signal (e.g., sine or cosine), and provide the frequency (Hz), sampling frequency (Hz), signal length, window type, and window size.
    </li>
    <li>
      <strong>2. Display the PSD Plot:</strong> 
      Click the <em>“Simulate”</em> button to view the power spectral density (PSD) plot of the noisy input signal.
    </li>
  </ul>
</body>
</html>

