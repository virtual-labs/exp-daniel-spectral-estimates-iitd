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
        <li><strong>Input Signal(s):</strong> Specify and input the frequency values of the signal(s). In the case of a rectangular or triangular pulse signal, input the pulse width in seconds.</li>
        <li><strong>Window Type:</strong> Select a window type, such as Rectangular, Hann, or Hamming, from the dropdown menu.</li>
        <li><strong>Operations:</strong> Use the input field to select various operations, such as Fourier addition, subtraction, multiplication, and convolution.</li>
        <li><strong>SNR (in dB):</strong> Enter the desired Signal-to-Noise Ratio (SNR) in decibels (dB).</li>
      </ul>
    </li>
    <br/>
    <h3><strong>Steps:</strong></h3>
    <li>
      <strong>1. Generate Input Signal(s):</strong> 
      Click the <em>“Generate Input Signal”</em> button to create the input signals. Choose the base signal, such as a sine wave, cosine wave, and select the operation from the dropdown menus.
    </li>
    <li>
      <strong>2. Display the PSD plot:</strong> 
      Click the <em>“Simulate”</em> button to visualize the power spectral density (PSD) plot of the noisy input signal.
    </li>
  </ul>
</body>
</html>
