Download Link: https://assignmentchef.com/product/solved-ece210-homework-6
<br>
Before we get started, a few quick reminders about homework format: • I didn’t emphasize this much before, but place a header at the top of each file. This is just good general coding practice. Some points may be taken off if this is missing in future assignments. E.g., something like the following is fine:

% ECE210B HW6 % John Doe clc; clear; close all;

%% … start rest of code here

For function files, a comment describing the function in the file is also a good idea.

•   You may have to produce a lot of plots, which may become a little repetitive. However, don’t get lazy and forget to label axes and title each plot! Labels don’t have to be too long, but they should be enough to give an idea of each plot. This is an important skill for any technical report, so it’s good to get in the practice now.

•   Make sure your code runs without errors before submitting it. E.g., clear your workspace and run all the sections in a row from the top as a last check before submitting it.

(The real HW begins on the next page.)

This homework deals with digital filters in a low-level sense. You are expected to know a bit about the z-transform, but if you are not in ECE211 Signals and Systems, please contact me separately for some additional information on this homework if you need it. Also consult the extra materials posted in the Teams.

1.    For this question, you will work with the discrete-time system described by the following transfer function:

(a)    Store the transfer function in coefficient vectors b and a for the numerator and denominator, respectively.

Be very careful setting this up. See help zplane to see the format that zplane expects the polynomial functions to be in. (Hint: you may need to left-pad one of a or b with zero(s).)

(b)    Plot the poles and zeros of this system using a MATLAB function and the transfer function coefficients.

(For those taking ECE211.) List the ROCs (regions of convergence) and for each state if it is causal and/or stable.

(c)    Compute the poles and zeros of this system using a MATLAB function. (Make sure to choose the one for discrete systems, not for continuous-time systems.) Do these poles and zeros match what you saw in the previous question?

(Optional.) Calculate the poles and zeros by hand and verify once again that these are correct.

(d)   Compute the first 32 samples of the impulse response of this transfer function using a MATLAB function and save this to a variable h.

(e)    Generate a 64-length vector  64. This is an arbitrary discrete-time signal. Show the result of applying the filter with transfer function H(z) to this signal by:

i.         Using filter.

ii.       Convolution in the time-domain with the impulse response. iii. (Optional.) Multiplication in the z-domain. Show your work. (Note that you can use impz to take inverse Z-transform of a

rational function.)

Do your output signals match? (Note that conv will produce a vector of different length than x – this is inconsequential and you can truncate it to the correct length.)

2.    We’re going to be exploring a filter by placing its poles and zeros in specific locations. Last question you converted a system description from its transfer function (tf form) to its zeros and poles (zp(k) form). Now we will do the opposite.

(a)    Compute numerator and denominator vectors for a transfer function with k = 0.01 and these poles and zeros:

Poles: exp(±2.056j), exp(±1.4261j)

Zeros: 0.7375exp(±0.7601j), 0.9589exp(±1.2360j)

(b)    Create a pole-zero plot using the numerator and denominator vectors and a MATLAB function.

(c)    Use freqz as shown in lecture to find the frequency response of this filter. This will return two vectors: H (complex frequency response vector) and ω (digital frequencies corresponding to H).

Do not use the default plot created by freqz – you will be manually creating the plot. (The default plot is shown if you do not use the return value of freqz, so make sure to save the values [H, w] for the next question.)

(d)   H is complex: it has a magnitude and a phase. Plot these in two subplots similar to what was shown in lecture. Make sure to:

•   Convert the magnitude gain (magnitude of H) in decibels and label accordingly.

•   Plot the delay (phase of H) in degrees. Use unwrap to make it look nicer.

(Note that for this particular filter, there are jagged edges even with unwrap because it is a sharp filter. However, without unwrap you get some additional unwanted jagged edges.) • Show units in axis labels. (Remember that the frequency vector w is in digital units of radians, not radians per second.)

•   Remember that the frequency vector w goes only from 0 to π. Properly scale and limit and label the x-axis using xlim, xticks, and xticklabels.

(e)    Using the information from the frequency response, what kind of filter is this (high/low/band-pass)? Can you see this from the pole-zero plot as well?

(f)     (Optional.) Choose a sampling frequency fs and sample sinusoids at f ∈ {0.1fs/2,0.5fs/2,0.9fs/2} and see that this indeed attenuates frequencies as you expect.