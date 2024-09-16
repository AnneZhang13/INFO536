# Individual Project 3
# Sequence Classification with Deep Neural Networks
#### Due Date
* Thursday Oct 3, 2024 (23:59)

#### Total Points
* 100 (One Hundred)

## Goal
In this project, you will try a sequence classification task using deep learning. A training dataset (which can be found at [Google Drive](https://drive.google.com/open?id=1xfyxupoE1C5z7w1Bn5oPRcLgtfon6xeT)) containing five taxi drivers' daily driving trajectories in 6 months is provided, and the goal is to build a deep neural networks to predict which driver a trajectory belongs to using the testing dataset (you can find the testing data test.pkl in the GitHub folder). You can use Keras or PyTorch for this project.


## Project Guidelines

#### Dataset Description
| plate | longitute | latitude | time | status |
|---|---|---|---|---|
|4    |114.10437    |22.573433    |2016-07-02 0:08:45    |1|
|1    |114.179665    |22.558701    |2016-07-02 0:08:52    |1|
|0    |114.120682    |22.543751    |2016-07-02 0:08:51    |0|
|3    |113.93055    |22.545834    |2016-07-02 0:08:55    |0|
|4    |114.102051    |22.571966    |2016-07-02 0:09:01    |1|
|0    |114.12072    |22.543716    |2016-07-02 0:09:01    |0|


Above is an example of what the data look like. In the data/ folder, each .csv file is trajectories for 5 drivers in the same day. Data can be found at [Google Drive](https://drive.google.com/open?id=1xfyxupoE1C5z7w1Bn5oPRcLgtfon6xeT)
#### Feature Description 
* **Plate**: Plate means the taxi's plate. In this project, we change them to 0~5 to keep anonymity. Same plate means same driver, so this is the target label for the classification. 
* **Longitude**: The longitude of the taxi.
* **Latitude**: The latitude of the taxi.
* **Time**: Timestamp of the record.
* **Status**: 1 means taxi is occupied and 0 means a vacant taxi.

#### Hints
Each trajectory is composed of consecutive GPS records of a driver. You can view a driver's all GPS records within one day (which should be sorted based on the **Time** and **Status**) as a long trajectory.
You can do whatever you want to preprocess the data (i.e., long trajectories) before feeding the data to the neural network, such as extracting features, getting sub-trajectory based on the status, trajectory embedding and so on. 

#### Evaluation 
Evaluation goal: given a full-day long trajectory of a taxi, you need to predict which taxi driver it belongs to. 
During the testing, five days of trajectories collected from 5 drivers will be used to evaluate your submission. You can find the testing data test.pkl in the GitHub folder

#### Submission Guideline
To help better and fast evaluate your model, please submit a separate python file named "evaluation.py". This file should contain two functions.
* **Data Processing**
  ```python
  def processs_data(traj):
    """
    Input:
        Traj: a list of list, contains one trajectory for one driver 
        example:[[114.10437, 22.573433, '2016-07-02 00:08:45', 1],
           [114.179665, 22.558701, '2016-07-02 00:08:52', 1]]
    Output:
        Data: any format that can be consumed by your model.
    
    """
    return data
  ```
* **Model Prediction**
    ```python
    def run(data,model):
        """
        
        Input:
            Data: the output of process_data function.
            Model: your model.
        Output:
            prediction: the predicted label(plate) of the data, an int value.
        
        """
        return prediction
  ```

## Deliverables & Grading
* PDF Report (50%) [template](https://www.acm.org/binaries/content/assets/publications/taps/acm_submission_template.docx)
    * proposal
    * methodology
    * empirical results and evaluation
    * conslusion
    
* Python Code (50%)
    * Code is required to avoid plagiarism.
    * The submission should contain a python file named "evaluation.py" to help evaluate your model. 
    * The evluation.py should follow the format in the above Guideline. 
    * Evaluation criteria.
      | Percentage | Accuracy |
      |---|---|
      | 100 | 0.6 |
      | 90 | 0.55 |
      | 80 | 0.5 |
      | 70 | 0.45|
      | 60 | 0.4 |
* Grading:
  * Total (100):
    * Code (50) + Report (50)

  * Code (50):
    * accuracy >= 0.60: 50
    * accuracy >= 0.55: 45
    * accuracy >= 0.50: 40
    * accuracy >= 0.45: 35
    * accuracy >= 0.40: 30

  * Report (50):
    1. Introduction & Proposal (5)
    2. Methodology (20):
        a. Data processing (5)
        b. Feature generation (5)
        c. Network structure (5)
        d. Training & validation process (5)
    3. Evaluation & Results (20):
        a. Training & validation results (10)
        b. Performance comparing to your baselines (maybe different network structure) (5)
        c. Hyperparameter (learning rate, dropout, activation) (5)
    4. Conclusion (5)
   
