# PDDPsystem *Please Download at ‘Release’*
Data preprocessing Tool system for Pupil Core-pupil diameter Raw Data

🎉 Pupil Diameter Data Processing System (PDDP) Version: V.1.0🎉 Handbook
Developed by Ge Song, James Watt School of Engineering, University of Glasgow
📌 Welcome to use this system!
This system has been developed for the pre-processing of pupil diameter data, mainly raw data collected by Pupil Core (Pupil Lab).
Warning!!! Before using this system, please make sure that your raw data has been converted to a Fixed Format (see Example.csv provided). Opening the .exe program may take a few seconds but going from the import .csv file to the final export is just a click away and will take from only 1 to a few seconds depending on the amount of data you have.

⚙ System Processing Flow
The data will be processed in a left and right eye separation manner, and the main steps are as follows:

🧹 Cleaning the data:
	Removal of data with a confidence level parameter
	Removal of data with pupil diameter size interval
	Recommended parameters: Confidence ≥ 0.8, Pupil Diameter ∈ [2, 8]

📈 Interpolation:
	Optional: Cubic Hermite Spline or PCHIP
	Interpolation can be limited to a maximum and minimum value
	Recommended method: Cubic Hermite Spline, interpolation range 2~8mm.

📡 Filtering: 
	Use Zero-Phase Butterworth Low-pass Filter
	Filter order and cutoff frequency can be set
	Recommended parameters: 3rd order, 10Hz or 4Hz

⏬ Downsampling:
	Use the Scipy: resample_poly method
	Built-in window=‘boxcar’ to prevent over filtering
	Downsample From= your data sampling rate
	Recommended frequency: Downsampling to 100Hz or 50Hz
📂 Exported Files:
The system will export the following files in the directory specified by the user:
	Filtered_left.csv
	Filtered_right.csv
	Contains the complete data processing procedure: Raw → Cleaning → Interpolation → Filtering

	Processed (Downsampled)_left.csv
	Processed (Downsampled)_right.csv
	Contains the final downsampled results

	summary_stats.txt
	Descriptive Statistics (Left Eye, Right Eye): Mean, Maximum, Minimum, Standard Deviation, Variance, Median, Q1, Q3, IQR
	Binocular Mean after combining both eyes

📬If you experience problems during use, please feel free to give feedback! Email: g.song.1@research.gla.ac.uk
Thank you for your support and hope this system will help you to perform pupil data preprocessing more efficiently! 😊

Ge Song
ICE Research Group
James Watt School of Engineering
University of Glasgow
ge-song-quantum-immersive-learning.owlstown.net
www.iceresearch.org
