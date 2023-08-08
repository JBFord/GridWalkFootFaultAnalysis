# GridWalkFootFaultAnalysis
Code to analyze grid walk data to log foot faults

version 0.01

Prerequisites:
MATLAB version 2022 or newer must be installed. May be compatible with earlier versions, but this is not guaranteed.


General:
This GUI has been designed to score side view videos of a mouse or rat walking on a grid surface. The user must define which video is to be scored. Once analysis is completed, the user can export results to an excel file.

Functions:

	"Select Video" - Pushing this button launches a dialog box to allow the user to select the video of interest
 
	"Video Progress" bar - Visualizes the progress of the video. Clicking and draggin the tab changes the current time frame in the video
 
	"Playback Rate" spinner - Select the playback rate (from 0.25x to 4x). Note, running the video above 1x may result in a delayed response from matlab in the "Play","Pause","Step Forward","Step Backward" features. If the video continues to play after "Pause" is selected, allow MATLAB a few seconds to catch up.
	"Play" - Pushing this button plays the video at the defined Playback Rate
	"Pause" - Pause the video playback
	"Step Forwards" - Move forward 1 frame. This can also be accomplished by pushing the right arrow key. The video image must be selected for the arrow key to work.
	"Step Backwards" - Move backwards 1 frame. This can also be accomplished by pushing the left arrow key. The video image must be selected for the arrow key to work.

	"Detected Faults" List - A running list of the defined foot faults. This list is clickable. Selecting a particular fault will jump to the time point in the video that is defined.
	"Fault Location" radio buttons - define where a given fault comes from
	"Add Fault" - Adds a fault to the Defined Faults list where the time is the current video time of the frame displayed and the fault location is the currently selected Fault Location radio button.
	"Remove Fault" - Remove a fault from the Detected Faults list if the current video frame has a fault defined. The easiest way to ensure that you are on the correct video frame is to first select the foot fault from the Defined Faults list before selecting Remove Fault.

	"Export Faults" - Creates an excel file with a summary of the identified foot faults. The first column is the time of each fault in seconds. The second column is the human readable relative time ("minute:seconds") of each fault (e.g. "2:30" instead of "150"). The third column is the location value of each fault. The fourth column is the human readable location of each fault. Each foot fault is defined in a separate row. In the columns to the right of these 4 are summary statitstics: Total_Faults, Total_FrontLeft, Total_FrontRight, Total_HindLeft, Total_HindRight, Total_LeftFaults, Total_RightFault.


*TIP*
	Using the arrow keys allows for easy fine interrogation of frames when trying to determine the occurence or location of a fault. Holding down the right or left arrow key will allow for video playback that will stop when the arrow key is released. Matlab functions execute faster that frames can be plotted, so holding these key for extended periods will cause the video to fall behind such that playback will continue for some time after the arrow key is released.
