# multilabel_classification

# Approach followed
First i tried applying RF,DT but they were not time efficient. I tried reducing dimensions using PCA and then using DT,RF but it wasnt giving good accuracy. then i moved to Logistic regression. Couldnt feed entire data at once because it was big. hence created chunks of data and then fed to logistic regression, It gave decent F1 score (0.84+). 
How to run the code?
= The code requires more memory and time to run hence it is better to run on IEOR server (Tirandaz or Paspoli).
Upload text file of train data and text file of test data on IEOR server jupyter notebook. After uploading, run the code directly (run all). The code will keep uploading pickle files of trained models on the server as soon as they are trained. The code will automatically create a submission.csv file which will be stored in the folder named ‘prediction’ . This folder will be created by the code itself. At this stage if we submit the csv file, it will give more than 0.84 score.
How the score is further improved?
I had multiple submission.csv files which I had got as output of multiple approaches. Best submission file out of these had 0.84 + score (output of code which is uploaded). But still this file had many blank predictions which didn’t contribute anything in the score. I decided to fill these blank predictions using other submission.csv files which I had got through earlier approaches. Those csv files might have predicted those labels which are not predicted in my current csv file . Hence I filled those blank predictions by taking majority voting from the predictions of previous csv files for the labels of the same samples. For this other code was written. At the output of this score was 0.86+.


final F1 score i got was using XGBoost approach. it gave 0.866 f1 score.
