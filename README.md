# project-1-eheffernan

## Experiment Overview
The purpose of this experiment is to study category learning. Participants are presented with flower stimuli, which they must learn to sort (through trial and error) into two categories ("prefers sun" and "prefers shade"). Stimuli are either category prototypes, rule-following items (which differ from their category prototype along one dimension), and exception items (which are more similar to the prototype from the opposite category than the prototype of their own category). 
This experiment is divided into three parts. The first contains three learning blocks in which the participants receive feedback as they categorize the stimuli (each block contains 48 images). In each of the three blocks, the proportion of prototype, rule-following, and exception items differs. Part two comprises a "no feedback" block to assess how much participants have learned. This block is identical to those of part one, but no feedback is provided. Finally, in part three participants complete a recollection block in which they must indicate if the presented flowers are new or old. They are then asked to indicate their learning strategy. All participant data is saved in a .csv file. 

## Submission File Breakdown
I have included a "lite" version of this experiment, in which each block contains 2 trials instead of 48. The "Images" folder contains the flower stimuli, the "Params" folder defines the images per trial, and the "Instructions" folder contains the images that are presented to guide the participant through the experiment. I've been having some issues with different versions of PsychoPy not working since I updated my computer; the submitted version was created using PsychoPy 3.1.2. As this experiment was designed to be run online, it was built entirely using the PsychoPy builder, and its functionality is augmented using code blocks. A full online version of the experiment (containing the full number of trials) can be found at [this link](http://thedrsmack.com/psych/participate/8462154cad26). 

## Routine-by-routine Breakdown
### Pt1_Instr
Here, the participant is presented with the task instructions.
### TaskBlocks Loop
This loop assigns a parameter file that contains the correct parameter file for each of the three blocks in part one.
### LearningTask Loop
This loop assigns the respective parameter file from the TaskBlocks loop for each block in part one.
### tbOne
In this routine, stimuli are presented, and the participant is prompted to respond. Participants have to categorize each image as "Prefers Sun" or "Prefers Shade". If they do not respond within 3 s, a warning message appears. At the end of this routine, a code block is used to assign the proper feedback routine based on the participant's response. This is done by setting the number of reps for the loop containing the correct feedback to one. All other feedback loops are set to zero.
###  rep_sc, rep_si, rep_shc, rep_shi and fb_sc, fb_si, fb_shc, fb_shi
These loops (rep_x) each house a routine (fb_x) for one of four feedback options (sun, correct; sun, incorrect; shade, correct; and shade, incorrect). In each feedback routine, the correct response and the flower image from the present trial are displayed. Only one of these loops is displayed based on performance in the present trial. 
### break
At the end of each trial block in part one, the participant is given the opportunity to rest.
### Pt2_Instr
Here the participant receives instructions for completing the second part of the experiment, which is identical to part one but without feedback
### nf_trials and NoFeedback
The nf_trials loop defines the 48 images and respective parameters to be displayed in the NoFeedback routine. 
### Pt3_Instr
The participant receives instructions to complete a surprise recollection task.
### Mem_loop and MemTest
Mem_loop defines the parameters for the recollection task. In this routine, participants have to identify whether the presented images are new or old. 
### Strategy
The participant is asked to record their strategy. The code block in this routine was adapted from [this site](https://gitlab.pavlovia.org/demos/textinput/).
### DONE
The last routine! The participant is thanked and prompted to exit the experiment.
