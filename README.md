# SFND_Radar_Target_Generation_and_Detection
## Criteria Fulfillment
 - [x] FMCW Waveform Design
  * Description: Using the given system requirements, design a FMCW waveform. Find its Bandwidth (B), chirp time (Tchirp) and slope of the chirp.
  * Implementation: The code can be found between `Line 31 and Line 33`.
 - [x] Simulation Loop
  * Description: Simulate Target movement and calculate the beat or mixed signal for every timestamp.
  * Implementation: The code can be found between `Line 60 and Line 78`.
 - [x] Range FFT (1st FFT)
  * Description: Implement the Range FFT on the Beat or Mixed Signal and plot the result.
  * Implementation: The code can be found between `Line 82 and Line 114`.
 - [x] 2D CFAR
  * Description: Implement the 2D CFAR process on the output of 2D FFT operation, i.e the Range Doppler Map.
  * Implementation steps:
    1. Iterate over each Cell Under Test (CUT).
    2. Sum the values in the traing cells.
    3. Compute the averatge of these values.
    4. Determine the threshold by adding the offset to the average.
    5. Compare the CUT value with the threshold and assign a value of 1 if the CUT value is higher than the threshold.
    6. Visualize the results.
  * Parameters:
    * Training Band Rows = 2
    * Training Band Columns = 2
    * Guard Band Rows = 1
    * Guard Band Columns = 1
    * Offset = 5 dB
  * Steps taken to suppress the non-thresholded cells at the edges:
    1. Initialize the `threshold_RDM` matrix with zeros, matching the size of the `RDM`.
    2. Assign a value of 1 to a cell only if its value exceeds the threshold.
