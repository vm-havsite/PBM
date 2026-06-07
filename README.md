# PBM
Core idea: A closed-loop photobiomodulation (red/IR light therapy) device that reads pulse, determines stress level in real-time, and automatically adjusts LED therapy output to try to bring you back to a calmer state.


Signal processing:
Rolling 8-second buffer of raw pulse samples
Peak detection → RR intervals → HR in BPM and RMSSD (root mean square of successive differences) as the HRV metric

Stress classification:
Gaussian Naive Bayes classifier over [HR, RMSSD]
I am using my own personal reading as abseline because i found no major study that had proven widespread data on teenagers and on checking i found that my values do not accurately match the values in recognized adult studies.

LED protocol:
Three output states: stressed (IR:204, Red:102, 8Hz pulse), normal (IR:153, Red:77, 5Hz), relaxed (IR:102, Red:51, steady)
The idea being that PBM at different intensities/frequencies may modulate autonomic nervous system tone
