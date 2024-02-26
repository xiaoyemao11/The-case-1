## Project Information

* Project Name : 

  ​		Data Analysis and Prediction of School Enrollment for School-Age Children in Various Cities of Guangdong

* Project Description : 

  ​		This project aims to analyze the enrollment data of school-age children in Guangdong province from 2011 to 2022. The objective is to visualize this data through charts and graphs and utilize linear regression to predict the enrollment numbers and rates for each city in Guangdong in 2023. The results will serve as a reference for future investigations into enrollment trends.

* Directory Structure : 

  * GD_prediction.ipynb ：Jupyter Notebook file containing the main data analysis and prediction processes.
  * 广州入学.xlsx ：Data file containing the necessary enrollment data for Guangdong province.
  * README.md ：Project documentation file providing an overview of the project.

* Data：

  In this project, data from 2011 to 2022 regarding the enrollment of school-age children in various cities in Guangdong is utilized. The raw data is stored in the `广州入学.xlsx` file and is transformed into a dataframe format for ease of manipulation in subsequent data analysis and prediction tasks.

* Data Analysis and Prediction Process :

  * Importing libraries such as numpy, pandas, matplotlib, pyecharts, etc., for data processing and visualization.
  * Reading the data file and converting it into a dataframe.
  * Processing the data to obtain the total enrollment numbers and enrollment rates for each year from 2011 to 2022 in Guangdong. Multiple bar charts and line graphs are plotted.
  * Filtering out the annual enrollment numbers for each city, creating dynamic maps, bar charts, and enrollment rate line graphs for Guangdong cities.
  * Processing data for regions like the Pearl River Delta, East Wing, West Wing, and Mountainous Area, and creating stacked bar charts, pie charts, heatmaps, and scatter plots.
  * Analyzing the trend of enrollment numbers each year in Guangzhou, noting a linear pattern.
  * Training a linear regression model using the data and plotting the fitted line to predict the enrollment numbers for Guangzhou in 2023.
  * Predicting the enrollment numbers and rates for Guangdong cities in 2023.
  
* Conclusion :

  ​		This study encompasses detailed information on the enrollment of school-age children in various regions of Guangdong Province in 2023. Through a thorough analysis of the data, the following conclusions can be drawn:

  * High Overall Enrollment Rates :  The enrollment rates for school-age children in various regions of Guangdong Province are generally high, with most areas reaching 100%. This reflects significant achievements in the universalization of basic education in the province.

  * Educational Equality : From the enrollment rates, the differences among regions are relatively small, indicating a certain level of success in achieving educational equality in Guangdong Province. This is positively significant for ensuring equal educational opportunities for every school-age child.

  * Slightly Lower Enrollment Rates in Some Areas : In a few areas, the enrollment rates are slightly below 100%, with Meizhou City at 99.61% and Shanwei City at 99.49%. This may be related to the distribution of local educational resources or other factors that warrant further in-depth research.

  * From 2011 to 2022, the total enrollment in Guangdong has been steadily increasing from around 7.6 million to over 8.8 million. This represents an average annual growth rate of 1-2%.

  *  The Pearl River Delta region has consistently accounted for the largest share, around 60-65% of total enrollments. This is attributed to its status as the most economically developed area.

  * The Eastern and Western regions also contribute significantly, each making up approximately 20-25% of historical enrollment figures.

  *  Mountainous areas saw more moderate increases in enrollments compared to other regions, but still comprised 10-15% of the overall totals.

  * High enrollment rates exceeding 99% across all localities indicate that compulsory education is reaching the vast majority of school-aged children..

  * Overall Health of Guangdong's Education System : Looking at the overall data, the enrollment situation for school-age children in Guangdong Province is relatively favorable, indicating a healthy trend in the development of the education system as a whole.

## Tools Used

* **Pandas:** 

  ​		Pandas is a powerful data analysis tool that provides simple and efficient data structures and analysis functions, particularly suitable for handling structured data. It offers the DataFrame object, facilitating concise and efficient data manipulation.

* **NumPy:** 

  ​		NumPy is the core library for scientific computing in Python, providing high-performance multidimensional array objects and corresponding mathematical functions. It is utilized in this project for tasks such as statistical calculations, array operations, and numerical computations.

* **Matplotlib:** 

  ​		Matplotlib is a library for creating static, dynamic, and interactive visualizations in Python. It offers various plotting functions and chart styles. Matplotlib is used in this project to generate charts such as trend graphs and scatter plots for better understanding and representation of data.

* **Pyecharts:**

  ​		Pyecharts is a Python charting library based on Echarts, providing rich chart types and interactive features. It combines the convenience of Python with the high performance of Echarts, making it easy to generate interactive and visual charts. In this project, Pyecharts is used to create interactive charts, including heatmaps and line graphs depicting enrollment rates over time.

* **Scikit-learn (sklearn):** 

  ​		Scikit-learn is a Python library for machine learning that offers various machine learning algorithms and tools. It includes a linear regression model used in this project to build and train a predictive model based on linear relationships. The model is trained using historical data to predict future enrollment numbers and rates.

These tools collectively contribute to the effective analysis, visualization, and prediction of school enrollment data in Guangdong province.

## Linear regression algorithm

1. Initialization

- During the initialization phase, create an instance of the linear regression model and set the coefficients (`coefficient`) and intercept (`intercept`) to `None`.

2. Fit Method

- **Input Parameters:** Training dataset `X`, target variable `y`, polynomial degree (`degree`), regularization parameter (`alpha`).
- Functionality:
  - Convert the input one-dimensional array `X` into a column vector (ensure `X` is a two-dimensional array).
  - Use the `_polynomial_features` method to transform original features into polynomial features, obtaining `X_poly`.
  - Calculate the regularization term to prevent overfitting. This is achieved by generating an identity matrix and multiplying it by the regularization parameter `alpha`.
  - Solve the linear regression problem using the normal equation to obtain regression coefficients. The solution to the normal equation is expressed through matrix operations as: [ \text{{coefficients}} = \left( X_{\text{{poly}}}^T X_{\text{{poly}}} + \text{{reg_term}} \right)^{-1} X_{\text{{poly}}}^T y ]
  - Extract the first element of the computed coefficients as the intercept.
  - Extract all elements of the computed coefficients except the first one as feature coefficients.

3. Predict Method

- **Input Parameters:** Dataset to be predicted `X`, polynomial degree (`degree`).
- Functionality:
  - Convert the input list to a NumPy array.
  - Use the `_polynomial_features` method to transform original features into polynomial features, obtaining `X_poly`.
  - Predict target variable values using the model's coefficients and intercept through matrix operations. The prediction formula is: [ \text{{predictions}} = X_{\text{{poly}}} \cdot \left[ \text{{intercept}}, \text{{coefficients}} \right] ]
  - Round the predicted values and return the integer prediction.

4. Polynomial Features Generation Method `_polynomial_features`

- **Input Parameters:** Original feature matrix `X`, polynomial degree (`degree`).
- Functionality:
  - If the degree is 1, return a matrix containing a column for the intercept.
  - If the degree is greater than 1, generate a list containing various powers of the original features and concatenate them column-wise to form the polynomial feature matrix. This is achieved using `np.c_`.

The core of this algorithm lies in fitting the data using polynomial features, solving regression coefficients using the normal equation, and supporting regularization to prevent overfitting.

