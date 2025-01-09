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
        <li><strong>Operations:</strong> Use the input field to select various operations, such as Signal addition, subtraction, multiplication, and convolution.</li>
        <li><strong>Input Signal(s):</strong> Specify and input the frequency values of the signal(s).</li>
        <li><strong>Sampling Frequency (Hz):</strong> Enter the sampling frequency (in Hz) in the input field.</li>
        <li><strong>SNR (in dB):</strong> Enter the desired Signal-to-Noise Ratio (SNR) in decibels (dB).</li>
      </ul>
    </li>
    <li>
      <strong>Generate Input Signal(s):</strong> 
      Click the <em>“Generate Input Signal”</em> button to create the input signals.
    </li>
    <li>
      <strong>Generate Combined Signal:</strong> 
      Click the <em>“Generate Combined Signal”</em> button to create the combined signal, if applicable.
    </li>
    <li>
      <strong>Generate Noisy Signal:</strong> 
      Click the <em>“Generate Noisy Signal”</em> button to add Additive White Gaussian Noise (AWGN) to the input signal and generate the noisy signal.
    </li>
    <li>
      <strong>Display Power Spectral Density (PSD):</strong> 
      Click the <em>“Generate PSD”</em> and <em>“Generate PSD for Noisy Signal”</em> buttons to visualize the PSD of both input and noisy signals.
    </li>
  </ul>
</body>
</html>