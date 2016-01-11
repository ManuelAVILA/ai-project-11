## 24/01/2011 ##
  * Downloaded the dataset from http://www.iam.unibe.ch/~fkiwww/iamDB/data/
  * Though about how to use it
    * Decided to do word recognition without character segmentation. In this way instead of training one HMM for every character we train an HMM for every word.
  * Wrote a script in python to extract useful annotation for the dataset
  * Worked on dividing the dataset in training and test test

## 22/01/2011 ##
  * Continued working on the implementation of feature extraction part
    * Now instead of retrieving the number of loops, dots, junctions and endpoints, we retrieve also their position.
    * Intensity pixels
    * Ascender, centre and descender high
  * Tested the entire pipeline. It works, and the HMM seems to work. The more features we add the more reliable its decision is.

## 21/01/2011 ##
  * Attended the meeting with Albert
  * Though about how to use the sliding window
  * Optimized skew and slant correction. The optimization is needed to clean the images after the transformations applied.

## 20/01/2011 ##
  * Read again  "Morphological Image Processing" chapter from _"**Digital Image Processing Using MATLAB**"_
  * Started working on the implementation of feature extraction part
    * Dots detection finished
    * Junctions detection finished
    * Endpoints detection finished
    * Loops detection finished

## 19/01/2011 ##
  * Didn't work because attended the all-day-long congress called: "crime & punishment - a case of biology" (http://www.congocongres.nl/)

## 18/01/2011 ##
  * Optimized word segmentation
    * Added an extra 2-means clustering step in order to be able to segment words with a small white space between them
  * Wrote a function to extract the word from the entire image. In this way we have more control of the words, of its position and its length and high.
  * Read again  _"**An Off-Line Cursive Handwriting Recognition System**"_, focusing mainly on the feature extraction part.

## 17/01/2011 ##
  * Continued with pre-processing implementation
    * Modified upperBaselineEstimation function  (even though I am still not really satisfied)
    * Created a new function for ascender and descender Baselines

## 15/01/2011 ##
  * Changed the entire structure of the pipeline. Now:
    * We segment lines
    * We correct skew and slant
    * We segment words
    * For every word:
      * We correct skew and slant
      * We estimate the baselines (upper and lower)
  * Resulting words seems pretty good

## 14/01/2011 ##
  * Continued with pre-processing implementation
    * Modified word segmentation (small bug)
    * Modified skew and slant functions. Now instead of a black and white picture they work with the original one. I avoided the problem of the black pixels created by matlab transformation functions increasing the dimension of the images before using transformations
    * Skeleton estimation finished

## 13/01/2011 ##
  * Continued with pre-processing implementation
    * Words segmentation finished
  * Attended the meeting with Albert

## 12/01/2011 ##
> Read the following papers:
  * _"**Improving Offline Handwritten Text Recognition with Hybrid HMM/ANN Models**"_ (2010) by Boquera, Castro-Bleda, Gorbe-Moya and Zamora-Martinez
    * The papers describes Hybrid HMM/ANN (Artificial Neural Network) models for recognizing unconstrained offline handwritten text.
    * The paper presents new techniques to remove slop and slant from handwritten text and to normalize the size of the text images with supervised learning methods.
    * The papers seems pretty interesting

  * Continued with pre-processing implementation
    * Functions for upper and lower baselines estimation finished
    * Optimized skew detection based on the new baseline
    * Changed the entire structure of the system to make it more readable and easier to be understood
    * Skeleton of the words almost finished

## 11/01/2011 ##
  * Continued with pre-processing implementation
    * Skew and slope detection and correction finished
    * Slant detection and correction almost finished

## 10/01/2011 ##
  * Started working on the implementation of pre-processing part
    * Line Segmentation finished
    * Started skew and slope detection

## 08/01/2011 ##

  * Started reading book:  _"**Digital Image Processing Using MATLAB**"_ by R. Gonzales, R. Woods and S. Eddins
    * Chapter 9: A Morphological Image Processing

## 07/01/2011 ##
  * Searched on more paper, especially for those concerning the pre-processing and feature extraction part of the system.

> Read the following papers:
  * _"**Recognition of Off-Line Handwritten Devnagari Characters Using Quadratic Classifier**"_ (2006) by N. Sharma, U. Pal, F. Kimura and S. Pal
    * The paper present a system for recognition of Devnagari numbers and characters.
    * Interesting the feature extraction part: they extract histograms of direction chain of the contour of the characters as feature for recognition. The idea seems to be pretty similar to SIFT features, except that instead of using the orientation they uses the contour information.

  * _"**Unrestricted Off-Line Handwriting Recognition. A preprocessing Approach**"_ (2009) by Ryan E. Leary
    * The paper describes an implementation for the preprocessing of totally unconstrained handwritten text.
    * The paper is pretty nice, and all the pre-processing steps are fully described.
    * Surely and important paper for our project.

  * _"**Comparison of Different Preprocessing and Feature Extraction Methods for Off-line Recognition of Handwritten Arabic Words**"_ (2007) by Haikal El Abed
    * The paper describes some pre-processing steps that seems to be interesting in general handwritten recognition, and not only on arabic.
    * The paper will probably be useful


## 06/01/2011 ##
  * Checked and reviewed the code from last year project:
    * Out of all the functions maybe 3 or 4 are usable
    * The rest are either incomplete or a mess
    * No description is available

  * Consideration: now that we have a better idea of what the system covers, we prefer to concentrate our effort on the visual part of the system (pre-processing and feature extraction)

  * Attended the meeting with Albert. Interesting points emerged:
    * Start with an easy pipeline
    * Have an HMM working
    * Spend all the rest of the time on the pre-processing and feature extraction parts of the system

## 05/01/2011 ##
> Read the following papers:
  * _"**An Off-Line Cursive Handwriting Recognition System**"_ (1998) by Andrew W. Senior and Anthony J. Robinson
    * The paper describes a complete system for the recognition of off-line handwriting. Preprocessing techniques are described, including segmentation and normalization of word images to give invariance to scale, slant, slope and stroke thickness
    * It is a good paper to start with, and it gives a really good overview of how a full system work.

  * _"**Off-line Cursive Handwriting Recognition**"_ from last year students
    * The paper describes more or less the same system described in the previous paper

  * _"**Using Lexical Similarity in Handwritten Word Recognition**"_ (2000) by J. Park and V. Govindaraju
    * The paper presents a method to capture lexical similarity of a lexicon and realiability of a character recognizer which serve to capture the dynamism of the environment
    * I personally did not find the paper really interesting for what we have in mind

  * _"**A Recognition and Verification Strategy for Handwritten Word Recognition**"_ (2003) by M. Morita, R. Sabourin, F. Bortolozzi and Y. Suen
    * The main contribution of the work presented in the paper lies in the validation of the strategy used to recognition.
    * The paper is not that interesting for our purpose, except for one thing: in the paper they use two features sets: the first based on global features (such as loops, ascenders and descenders), while the second one is based on concavity measurements. Both features sets are combined with space primitives.

## 04/01/2011 ##
  * Attended the meeting with Albert Salah
  * Searched for papers on the topic
  * Talked with all the team members about what we want to restrict our research (the topic is touching an huge amount of sub-topics)