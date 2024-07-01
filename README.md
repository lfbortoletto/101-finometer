# 101-finometer

This tutorial guides you through the data analysis of the Finometer Model-2, a commercial peripheral vascular monitor developed by Finapres Medical Systems.

### Useful Resources
1. **Heart Cycle Dynamics Explanation**: [Watch Video](https://www.youtube.com/watch?v=IS9TD9fHFv0)
2. **Simulation of Blood Dynamics through a Valve Passage**: [Watch Video](https://www.youtube.com/watch?v=S2vZtPXV7A0)
3. **Cardiovascular Parameters Description Animation**: [Watch Video](https://www.youtube.com/watch?v=vFRkSB46bl8)
4. **TED-Ed on Blood Pressure and Vascular Dynamics**: [Watch Video](https://www.youtube.com/watch?v=Ab9OZsDECZw)

### Tasks

**1. Monitoring Metrics**
The Finometer is widely used in clinical settings and scientific research for non-invasive blood pressure monitoring, measuring beat-to-beat variations. It employs the Modelflow methodology (DOI: 10.1046/j.0001-6772.2003.01211.x) to provide hemodynamic parameters such as stroke volume, total peripheral resistance, and cardiac output. For more details, please refer to the Finometer User's Guide included in this repository.
- Provide a clear and concise description of each metric captured by the Finometer, included in the waveforms, beats, and BRS files.

**2. Peripheral Vascular Dynamics Display**
Despite the high volume of data captured by the Finometer, three key metrics for understanding peripheral vascular dynamics are heart rate, mean arterial pressure, and cardiac output.
   - Load the data from the Finometer files and display these three metrics.

**3. Signal Processing**
Vascular dynamics are slow, with responses taking up to 10 seconds after a given stimulus. High frequencies in vascular signals are generally of no interest.
   - Apply a low-pass frequency filter to remove frequencies higher than 0.5 Hz.
   - Update the previously displayed physiological data and describe the changes observed in the time series.

**4. Vascular Dynamics Perturbation**
One possible cause of vascular dynamics perturbations is alterations in the autonomic nervous system (ANS) due to sympathetic or parasympathetic dominance.
   - Using the previously displayed metrics, identify the timings of possible ANS perturbations and determine which ANS branch (sympathetic or parasympathetic) is most dominant during each perturbation.

**5. Stressful Stimuli Alterations in Vascular Dynamics**
ANS perturbations can be induced through experimental stimuli, such as psychosocial or physical stressors. In the stressor.csv file, you will find two arrays: (1) "timestamp (s)" refers to the elapsed time from the beggining of the experimental (already synchronized with "Time (s)" in the Finometer files), and; (2) "stimuli" that specifies timings out of stress (zeros) and under stress (ones).
   - Compare the visually identified ANS perturbations with the actual stimuli from the stressor.csv file.
   - Display the cropped time series around twenty seconds before and sixty seconds after the stimulus. Repeat this process for each stimulus and each metric.

**6. Understanding the Average Response**
Gathering multiple samples of the same stimulus can help understand the average dynamics of the physiological responses associated with that stimulus.
   - Store the cropped segments of the time series and calculate the mean response for each stimulus.
   - Display the mean and the standard error of the mean for each metric.
