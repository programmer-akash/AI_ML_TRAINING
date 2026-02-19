<?xml version="1.0" encoding="UTF-8"?>
<readme>

  <!-- =====================================================================
       Project 2: House Price Prediction — Linear Regression
       Author: [Your Name]
       GitHub: [Your GitHub Profile URL]
       ===================================================================== -->

  <project>
    <title>🏠 Project 2: House Price Prediction using Linear Regression</title>

    <badges>
      <badge label="Python"      color="blue"   logo="python"        message="3.x"/>
      <badge label="Scikit-Learn" color="orange" logo="scikit-learn"  message="ML"/>
      <badge label="Pandas"      color="150458" logo="pandas"        message="Data Analysis"/>
      <badge label="NumPy"       color="013243" logo="numpy"         message="Numerical Computing"/>
      <badge label="Matplotlib"  color="red"    logo="matplotlib"    message="Visualization"/>
      <badge label="Jupyter"     color="F37626" logo="jupyter"       message="Notebook"/>
    </badges>

    <overview>
      This project builds a Machine Learning model using Linear Regression to predict
      California house prices based on features like median income, house age, average
      rooms, population, and geographic location. It follows a complete ML pipeline —
      from data loading, exploration, and preprocessing through model training,
      evaluation, feature engineering, and saving predictions.
    </overview>
  </project>

  <!-- ===================================================================== -->

  <dataset>
    <name>California Housing Dataset</name>
    <source>Built-in — sklearn.datasets.fetch_california_housing()</source>
    <note>No download required. Loaded directly via Scikit-Learn.</note>

    <stats>
      <stat key="Total Records"  value="20,640 rows"/>
      <stat key="Features"       value="8 input features + 1 target (Price)"/>
      <stat key="Missing Values" value="None — clean dataset"/>
      <stat key="Target"         value="Median House Price (in $100,000s)"/>
    </stats>

    <features>
      <feature name="MedInc"     description="Median income of block group"/>
      <feature name="HouseAge"   description="Median house age in block group"/>
      <feature name="AveRooms"   description="Average number of rooms per household"/>
      <feature name="AveBedrms"  description="Average number of bedrooms per household"/>
      <feature name="Population" description="Block group population"/>
      <feature name="AveOccup"   description="Average number of household members"/>
      <feature name="Latitude"   description="Geographic latitude"/>
      <feature name="Longitude"  description="Geographic longitude"/>
      <feature name="Price"      description="TARGET — Median house value (in $100,000s)"/>
    </features>
  </dataset>

  <!-- ===================================================================== -->

  <ml_pipeline>

    <step number="1" title="Import Libraries">
      <description>
        Imported NumPy, Pandas, Matplotlib, and Scikit-Learn modules:
        fetch_california_housing, train_test_split, LinearRegression,
        mean_squared_error, and r2_score.
      </description>
    </step>

    <step number="2" title="Load Dataset">
      <description>
        Loaded dataset using sklearn's built-in fetch_california_housing().
        Converted to a Pandas DataFrame and appended the target column "Price".
      </description>
    </step>

    <step number="3" title="Data Understanding">
      <description>
        Explored shape (20,640 × 9), dtypes (all float64), and statistical
        summary. Mean house price: ~$206,855. Mean median income: ~$38,707.
      </description>
    </step>

    <step number="4" title="Check Missing Values">
      <description>
        Verified with df.isnull().sum(). Result: zero missing values across
        all 9 columns. No imputation required.
      </description>
    </step>

    <step number="5" title="Feature and Target Selection">
      <description>
        X (features): All 8 columns excluding "Price" — shape (20640, 8).
        y (target): "Price" column — shape (20640,).
      </description>
    </step>

    <step number="6" title="Train-Test Split">
      <description>
        Split data 80/20 using train_test_split with random_state=42 for
        reproducibility.
      </description>
      <split>
        <train rows="16,512" features="8"/>
        <test  rows="4,128"  features="8"/>
      </split>
    </step>

    <step number="7" title="Train Linear Regression Model">
      <description>
        Instantiated and fit a LinearRegression model on the training set
        using Scikit-Learn's LinearRegression().fit(X_train, y_train).
      </description>
    </step>

    <step number="8" title="Make Predictions">
      <description>
        Generated predictions on the test set using model.predict(X_test).
        Compared first 10 predicted vs actual prices for quick validation.
      </description>
    </step>

    <step number="9" title="Model Evaluation (RMSE + R²)">
      <description>
        Evaluated model performance using two standard regression metrics.
      </description>
      <results>
        <metric name="RMSE"     value="0.7456" interpretation="Average prediction error (lower is better)"/>
        <metric name="R² Score" value="0.5758" interpretation="Model explains ~57.6% of price variance"/>
      </results>
    </step>

    <step number="10" title="Visualization: Actual vs Predicted">
      <description>
        Scatter plot of actual vs predicted prices. Points closer to the
        diagonal line indicate better model accuracy.
      </description>
    </step>

    <step number="11" title="Residual Plot (Error Analysis)">
      <description>
        Plotted residuals (actual - predicted) vs predicted values. A random
        scatter around the zero line indicates no major systematic bias.
      </description>
    </step>

    <step number="12" title="Feature Importance (Coefficients)">
      <description>
        Extracted and ranked model coefficients to understand feature impact.
      </description>
      <coefficients>
        <coef feature="AveBedrms"  value="+0.7831" impact="Increases price"/>
        <coef feature="MedInc"     value="+0.4487" impact="Increases price"/>
        <coef feature="HouseAge"   value="+0.0097" impact="Minor positive effect"/>
        <coef feature="Population" value="-0.0000" impact="Negligible"/>
        <coef feature="AveOccup"   value="-0.0035" impact="Minor negative effect"/>
        <coef feature="AveRooms"   value="-0.1233" impact="Decreases price"/>
        <coef feature="Latitude"   value="-0.4198" impact="Decreases price"/>
        <coef feature="Longitude"  value="-0.4337" impact="Decreases price"/>
      </coefficients>
    </step>

    <step number="13" title="Feature Engineering — Log Transform">
      <description>
        Applied log1p transformation to the target variable (y) to reduce
        skewness and retrained the model for comparison.
      </description>
      <improved_results>
        <metric name="RMSE"     value="0.2244" note="Significant improvement"/>
        <metric name="R² Score" value="0.6006" note="Better variance explained"/>
      </improved_results>
    </step>

    <step number="14" title="Save Model Outputs">
      <description>
        Saved prediction results as a CSV file for further analysis and GitHub upload.
        Output file: house_price_prediction.csv
      </description>
    </step>

  </ml_pipeline>

  <!-- ===================================================================== -->

  <bonus_project>
    <title>🔢 Mini Project: Advanced Calculator</title>
    <filename>calculator.py</filename>
    <description>
      An interactive command-line calculator built with Python using a while-loop
      menu system and the statistics module. Supports user input, type casting,
      and both arithmetic and statistical operations.
    </description>
    <features>
      <feature>Addition, Subtraction, Multiplication, Division</feature>
      <feature>Percentage calculation</feature>
      <feature>Average (mean) of a list of numbers</feature>
      <feature>Median of a list of numbers</feature>
      <feature>Mode of a list of numbers (with error handling)</feature>
      <feature>Division-by-zero guard with informative error message</feature>
      <feature>Clean exit option (choice 9)</feature>
    </features>
    <concepts_used>
      <concept>while True loop with break</concept>
      <concept>User input and type casting (float)</concept>
      <concept>if/elif/else conditional branching</concept>
      <concept>Functions (show_menu)</concept>
      <concept>Python statistics module</concept>
      <concept>Exception handling (try/except)</concept>
      <concept>list() and map() for multi-number input</concept>
    </concepts_used>
  </bonus_project>

  <!-- ===================================================================== -->

  <key_findings>
    <finding>Median income (MedInc) is the strongest positive predictor of house price</finding>
    <finding>Geographic coordinates (Latitude, Longitude) have significant negative coefficients — location matters</finding>
    <finding>Baseline Linear Regression achieved R² of 0.576 — reasonable but improvable</finding>
    <finding>Log-transforming the target variable improved R² to 0.601 and cut RMSE by ~70%</finding>
    <finding>The dataset had zero missing values, making preprocessing straightforward</finding>
  </key_findings>

  <!-- ===================================================================== -->

  <skills_demonstrated>
    <skill category="Machine Learning">
      Linear Regression, Train-Test Split, Model Evaluation (RMSE, R²),
      Feature Importance via Coefficients, Feature Engineering (Log Transform)
    </skill>
    <skill category="Data Analysis">
      EDA, DataFrame operations, Missing Value Check, Statistical Summary
    </skill>
    <skill category="Visualization">
      Scatter Plot (Actual vs Predicted), Residual Plot, Coefficient Bar Chart
    </skill>
    <skill category="Python">
      Functions, Loops, Conditionals, Type Casting, Exception Handling,
      List operations, f-Strings, Modules (statistics, math, datetime)
    </skill>
    <skill category="Libraries">
      NumPy, Pandas, Matplotlib, Scikit-Learn
    </skill>
  </skills_demonstrated>

  <!-- ===================================================================== -->

  <project_structure>
    <file name="Project_2.ipynb"                 description="Main Jupyter Notebook — full ML pipeline"/>
    <file name="calculator.py"                   description="Mini Project — Advanced CLI Calculator"/>
    <file name="house_price_prediction.csv"      description="Model output — Actual vs Predicted prices"/>
    <file name="README.xml"                      description="Project documentation (this file)"/>
  </project_structure>

  <!-- ===================================================================== -->

  <setup>
    <prerequisites>
      <item>Python 3.x</item>
      <item>Jupyter Notebook or Google Colab</item>
    </prerequisites>

    <install_dependencies>
      <command>pip install numpy pandas matplotlib scikit-learn</command>
    </install_dependencies>

    <run_notebook>
      <command>jupyter notebook Project_2.ipynb</command>
    </run_notebook>

    <run_calculator>
      <command>python calculator.py</command>
    </run_calculator>

    <note>
      No dataset download needed. The California Housing dataset loads automatically
      from Scikit-Learn's built-in datasets on first run.
    </note>
  </setup>

  <!-- ===================================================================== -->

  <technologies>
    <tech name="Python 3"      role="Core programming language"/>
    <tech name="NumPy"         role="Numerical computing and array operations"/>
    <tech name="Pandas"        role="Data manipulation and DataFrame operations"/>
    <tech name="Matplotlib"    role="Data visualization"/>
    <tech name="Scikit-Learn"  role="Machine learning — model training and evaluation"/>
    <tech name="Jupyter"       role="Interactive notebook environment"/>
    <tech name="statistics"    role="Python standard library for median/mode"/>
  </technologies>

  <!-- ===================================================================== -->

  <author>
    <name>[Your Name]</name>
    <github>[https://github.com/yourusername]</github>
    <note>Feel free to connect, fork, or raise issues!</note>
  </author>

  <license>MIT License — open source and free to use.</license>

</readme>
