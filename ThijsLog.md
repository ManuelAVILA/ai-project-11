Friday 7th
Reading papers, started working on HMM and pipeline

Saturday 8th
Continued working on the HMM and started a GMM we can possibly use.

Monday 10th
Meeting to discuss what we have done, continue working on the implementation.

Tuesday 11th
Finished GMM implementation yesterday evening, continued working on HMM.

Wednesday 12th
Finished Viterbi algorithm and training methods, started testing and debugging for discrete scalar observations. Started writing some formulas in Latex. Started extending the model to higher dimensional observations, worked on adding the Gaussian mixture class to the code.

Thursday 13th
Included higher dimensional observations and did testing for forward/backward probabilities. Read some papers on using GMM in HMM.

Friday 14th
Started implementing GMM update step and EM functions in GMM class.

Saturday 15th
Worked a bit further on some LA functions and the GMM update steps.

Monday 16th
Hope to have finished the complete implementation of the HMM and GMM, but still needs debugging, testing and optimising, hope to do that tomorrow. Started working on a filereader that reads observations, and transition functions for testing. I plan to study the use of C++ within matlab tomorrow and start helping with feature extraction on Thursday.

Tuesday 17th
Still stuck on the update step of Gaussian function, something strange is happening and havent been able to figure it out by the end of the day.

Wednesday 18th
Did a tutorial on mex funtions in Matlab and worked on a wrapper function to include the C++ code in the Matlab pipeline. Read articles on how to extract features and how to use the features in the HMM. Hopefully fixed the bug for the covariance update.

Thursday 19th
Made some extra routines in the code for the HMM, started reading up and working on feature extraction.

Friday 20th
The code finally works, except for some singularity issues still. Compared the code to HMM toolkit implementation and shockingly found out its much faster than the c++ code. The toolkit uses log-probabilities and is heavily optimised by a guy from MIT. We have therefore decided to use the toolkit instead of the C++, such that I can completely focus on feature extraction and getting a pipeline to work this weekend. The past two weeks of getting the software to work resulted sadly in a slow piece of code and it still needs checks for singularities and log-probabilities, but at least my C++ skills have drastically increased and I can safely say I understand all the details about HMM's and GMM's now.