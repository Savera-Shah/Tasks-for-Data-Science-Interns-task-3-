# Tasks-for-Data-Science-Interns-task-3-

# **Code Explanation:**
 
 **1. Import Libraries & Dataset**
- Upload and load creditcard.csv using Pandas.

- Used libraries like sklearn, imblearn, pandas, numpy, and warnings.

 **2. Check for Imbalance**
- Found 492 fraud transactions vs 284,315 legitimate ones → highly imbalanced.

 **3. Data Preprocessing**
- Dropped the Class column (target) to make X (features) and stored Class in y (labels).

- Scaled features using StandardScaler.

- Handled imbalance using SMOTE (Synthetic Minority Oversampling Technique) to generate fake samples of the minority class (fraud).

**4. Model Training**
- Split resampled data into train and test sets.

- Used Random Forest Classifier with 100 trees to train the model.

 **5. Model Evaluation**
- Predicted test data and calculated:

- Precision, Recall, F1-score using classification_report.

- Accuracy using accuracy_score.

- **Output:** Nearly perfect performance (accuracy = 99.99%) — thanks to balanced data and strong model.

**6. Testing Interface**

- Created a function test_transaction(data) that:

- Takes a list of 30 features as input (Time, V1–V28, Amount).

- Scales the input and predicts with trained model.

- Returns whether it’s a "Legitimate Transaction" or "Fraudulent Transaction Detected!"

**You can test:**

- With a real row from dataset

- By manually entering your own 30 values.

# **How to Run the Code:**
 
**1. Upload & Setup**

   from google.colab
   
   import files
   
   uploaded = files.upload()
   
Then upload creditcard.csv.

**2. Install Required Package**

   - !pip install -q imbalanced-learn

**3. Run Code in Order:**

1. Load data

2. Preprocess using SMOTE

3. Train the Random Forest model

4. Evaluate

5. Use test_transaction() function

6. Try manual testing with 30 input values

4. Manual Testing
   
- print("\n Enter 30 values (Time, V1-V28, Amount):")
   
- user_input = [float(input(f"Enter feature {i+1}: ")) for i in range(30)]
   
- print("Result:", test_transaction(user_input))
   
- Example input:
  
  Enter feature 1: 10000  

  Enter feature 2: -1.359807 

  Enter feature 3: -0.072781   ...  feature 30

 - Output:

 --Result: Legitimate Transaction  

OR  

-- Result: Fraudulent Transaction Detected!

 # **Observation :**
 
1. Credit card fraud detection is highly imbalanced, and SMOTE helps solve that.

2. Random Forest is a great model choice due to its robustness and accuracy.

3. The model achieved ~100% accuracy after balancing.

4. The testing interface is user-friendly, allowing real-time predictions using actual or manual input.
