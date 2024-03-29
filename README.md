# DSC204A
Includes my work done(Assignments) in the course: Scalable Data Systems, which I completed while doing my master's at UC San Diego.

**Technologies used: Ray, Modin, Anaconda, Python, DataHub(Jupyter Notebook), Ray Tune, XGBoost**

## Programming Assignment 1:

**Objective:**  
The programming assignment focused on familiarizing students with processing large datasets using Ray and Modin. It comprised three tasks: setting up Ray and Modin, data manipulation with Modin, and implementing parallel computations with the Ray Core API.

**Task 1: Setting up Ray and Modin**

* Created a Python environment with Anaconda and installed Ray and Modin.  
* Checked successful installation of Ray and Modin using version verification commands.  

**Task 2: Data Manipulation with Modin**

* Performed basic data manipulation operations on a subset of the Amazon Reviews dataset using Modin.  
* Generated a new table with specified columns, including reviewerID, number of products reviewed, mean rating, latest review year, and number of helpful votes.  
* Conducted experiments by changing the number of CPUs used by Modin or the Ray backend and documented execution times with 2, 3, and 4 CPUs to observe speedup.  

**Task 3: The Ray Core API**

* Implemented a distributed merge sort algorithm using Ray to parallelize computations and utilize all 4 CPUs.  
* Modified a provided merge sort algorithm to parallelize tasks and achieve a speedup compared to plain sorting.  
* Analyzed the theoretical maximum speedup and accounted for differences between theoretical results and observed speedup with Ray.  

**Takeaways**:  
Overall, the programming assignment provided practical exercises in setting up distributed computing environments, performing data manipulation at scale, and implementing parallel algorithms using Ray and Modin.

***

## Programming Assignment 2

**Objective:**  
The programming assignment aimed to deepen students' understanding of Ray by focusing on multi-node data processing and collective communication. It consisted of three tasks: working with Ray Data, implementing MapReduce with Ray Actors, and implementing collective communication algorithms using Ray's Collective Communications library.

**Task 1: Ray Data**  
* Introduced Ray Data and Ray Datasets for distributed data processing.  
* Utilized Ray Data to process a subset of the Amazon Reviews Dataset and applied methods to transform and clean the data.  
* Ensured maximal CPU utilization across all workers using Ray Dashboard's Cluster section for monitoring.  

**Task 2: MapReduce with Ray Actors**  
* Implemented the MapReduce algorithm using Ray Actors for a distributed word count task.  
* Defined Mappers and Reducer as Ray Actors and divided the text into partitions to distribute workload evenly.  
* Focused on correctness rather than specific runtime requirements.  

**Task 3: Collective Communication**  
* Implemented the AllReduce collective communication operation using point-to-point communication APIs in ray.util.collective.  
* Completed tasks, including implementing P2P communication functions, Ray AllReduce, BDE AllReduce, and MST AllReduce algorithms.  
* Ensured correct P2P communication methods and inspected logging for verification.  

**Takeaways**  
Overall, the programming assignment provided hands-on experience in distributed data processing, MapReduce algorithms, and collective communication using Ray, thereby enhancing students' skills in scalable data systems.

***

## Programming Assignment 3:

**Objective:**  
The aim of Programming Assignment 3 was to train and tune a machine-learning model using Ray. The assignment consisted of two main tasks: feature engineering with Modin on Ray (Task 1) and training and tuning with Ray (Task 2).

**Task 1: Feature Engineering with Modin on Ray**

In Task 1, I performed feature engineering on the Amazon Reviews dataset using Modin on Ray. This involved several subtasks:

* Flatten categories and salesRank: I extracted the most general category from the nested list of categories and flattened the salesRank column into two separate columns, bestSalesCategory and bestSalesRank, handling null values appropriately.

* Flatten related: I calculated the mean price and length of the "also viewed" attribute array, handling null and dangling references gracefully.

* Impute price: I imputed null values in the price column using both mean and median imputation techniques, and imputed null and empty strings in the title column with a special string 'unknown'.

* Process title and one-hot encode category: I processed the title column by converting it to lowercase and splitting it into an array of strings. Additionally, I performed one-hot encoding on the category column.

**Task 2: Training and Tuning with Ray**

In Task 2, I trained a machine learning model using the preprocessed data and tuned its hyperparameters using Ray Tune. This task involved:

* Distributed Xgboost with Ray Train: I trained an Xgboost model to predict user ratings for products, minimizing mean squared error. The model was trained with specified hyperparameters and a scaling configuration for Ray.

* Tuning with Ray Tune: I performed a grid search for hyperparameters using Ray Tune, selecting the best model based on the lowest validation RMSE. The hyperparameters tuned were max depth, eta, and subsample, with a limited grid of values.

**Takeaways:**  
I developed the solutions for this assignment in Jupyter notebooks provided on DataHub, using the Ray environment with specified CPU and RAM configurations. Package installations were already handled, and caution was advised against installing additional libraries that could persist across cluster restarts.
Overall, this assignment provided valuable hands-on experience in feature engineering, model training, and hyperparameter tuning using Ray, contributing to a deeper understanding of scalable data systems and machine learning workflows.
