# Session 2 --- Data, Quality & Pre-processing (Comprehensive Notes)

Machine learning depends heavily on the quality and structure of data.
Every algorithm can be broken into three main components: how the data
is represented, how the parameters are optimized, and how the model is
evaluated and selected. In practice, however, the story begins much
earlier, with domain understanding, integration of data from different
sources, cleaning and preprocessing to remove inconsistencies, and
handling issues like imbalance or missingness. Without these, even the
most sophisticated algorithms will produce unreliable results.

## 1) Data, Objects, and Attributes

Data itself is defined as a collection of objects described by
attributes. An object, which may also be called a record, case, entity,
or instance, is represented through a set of attributes, also known as
variables, features, fields, or dimensions. Attributes vary in their
type and in the operations that can be meaningfully applied to them.
Nominal attributes represent categories without any order, such as ID
numbers, zip codes, or eye color. Ordinal attributes introduce a sense
of order but not meaningful distances; examples include grades,
rankings, or categories like tall, medium, and short. Interval
attributes extend this further: they have order and meaningful
differences, but lack a true zero. Calendar dates and Celsius or
Fahrenheit temperature scales are common interval attributes. Ratio
attributes complete the scale by introducing a true zero, making ratios
meaningful. Kelvin temperature, length, counts, and elapsed time fall
into this category.

The difference between interval and ratio attributes can be illustrated
by asking whether it is meaningful to say that 10 degrees is twice as
hot as 5 degrees. On the Celsius or Fahrenheit scale, such a claim is
invalid because there is no true zero. On the Kelvin scale, however,
this ratio is meaningful. A similar analogy arises when measuring
deviation from average: saying that one person's height is six inches
above average and another's is three inches above average does not
justify claiming the first is "twice as tall," because relative
deviations do not scale proportionally. The classification of attributes
into these four types, originally suggested by S. S. Stevens, also
defines what transformations preserve meaning. Nominal data can be
permuted arbitrarily, ordinal data can be mapped through any
order-preserving transformation, interval data can undergo linear
transformations (a·x + b), while ratio data can be rescaled
multiplicatively (a·x).

Attributes can also be divided into discrete and continuous. Discrete
attributes have a finite or countably infinite set of values and are
often represented as integers. Zip codes, counts of objects, and words
in a text collection are discrete examples. A special case of discrete
attributes is binary data, which may be symmetric (where both outcomes
are equally important, such as male versus female) or asymmetric (where
one outcome is rare and carries more weight, such as disease presence).
Continuous attributes, on the other hand, take values from the real
numbers, though in practice they are represented with finite precision
as floating-point values. Temperature, height, and weight are examples
of continuous data.

## 2) Other Data Characteristics

Beyond attribute type, data has several important characteristics that
shape machine learning. Dimensionality, or the number of attributes, is
crucial: high-dimensional data poses challenges such as sparsity, where
data points become widely separated, and the "curse of dimensionality,"
where distance measures and density-based methods lose effectiveness.
Sparsity itself is a separate property, often appearing in applications
like text mining, where only the presence of certain features matters.
Resolution refers to the scale of measurement: patterns may appear or
disappear depending on whether we look at data daily, weekly, or
monthly. Finally, the size of the dataset influences both the type of
analysis possible and the computational techniques used; massive data
requires scalable algorithms.

## 3) Data Types

Machine learning deals with many different data types. Relational or
object data is stored in traditional tables with rows and columns.
Transactional data captures sequences of events, such as shopping
histories. Document data consists of unstructured text. Web and social
network data is graph-based, recording interactions, friendships, or
hyperlinks. Spatial data records geographical information, while time
series data captures measurements over time such as stock prices or
weather readings. Sequence data is ordered but not necessarily
time-dependent, such as DNA sequences or event logs. Real-world problems
often combine multiple data types. For example, a case study from the
slides showed a bank wishing to segment customers for marketing,
requiring relational account information, transactional histories, and
categorical demographic attributes, with the goal of targeting
high-income customers who hold Titanium cards.

## 4) Data Quality

Quality is at the heart of data preparation. Poor data quality directly
translates into poor machine learning models, such as a loan risk
classifier that wrongly denies creditworthy applicants while approving
defaulters. The main categories of data quality problems are noise,
outliers, wrong or fake values, missing data, and duplicates. Noise
refers to random errors or distortions. At the object level, noise means
the presence of irrelevant or extraneous cases. At the attribute level,
it refers to distorted values, such as a person's voice on a poor
telephone connection or "snow" on a television screen. Outliers are data
points that deviate strongly from the rest. Sometimes they are noise to
be removed, but in other cases they are the very signals we want to
detect, such as fraudulent transactions or security intrusions. Missing
values arise when information is not collected, such as survey
respondents refusing to share their age, or when attributes are not
applicable, such as annual income for children. Missing values can be
eliminated, estimated through imputation methods such as interpolation
or regression, or ignored if the algorithm is robust enough. Duplicate
data occurs frequently when merging heterogeneous sources, for instance
when the same individual appears under multiple email addresses. It
requires cleaning and deduplication.

## 5) Data Preprocessing

Data preprocessing is the process of transforming raw data into a usable
form for machine learning. It involves both data engineering and feature
engineering. Data engineering includes aggregation, cleansing, sampling,
and scaling, while feature engineering involves creating, selecting, or
transforming features to maximize model effectiveness. Aggregation
combines attributes or objects, such as rolling days into months or
cities into states. This reduces dimensionality, changes scale, and
often yields more stable data. Data cleansing removes errors,
inconsistencies, and duplicates. It may involve imputing missing values,
harmonizing code systems, or discarding attributes with excessive
missingness. Outliers can be detected with statistical rules such as the
interquartile range (IQR) method, which flags points outside 1.5 times
the IQR beyond Q1 or Q3, or the three-sigma rule, which marks points
beyond three standard deviations from the mean under the assumption of a
normal distribution.

Instance selection and partitioning are also key aspects of
preprocessing. Sampling is often necessary because analyzing the full
dataset may be too costly. Small samples, however, can introduce
sampling noise, and flawed sampling processes can introduce bias even
with large samples. A sample is representative if it maintains the same
properties as the population of interest. Training, validation, and test
splits are the standard way to partition data for modeling. Random
subsampling may suffice, but stratified sampling preserves class
proportions in classification problems, while clustered sampling groups
data into natural clusters. Special care is needed for imbalanced
training sets where one class is rare: oversampling the minority class
or undersampling the majority class can be used to balance the
distribution.

## 6) Feature Tuning and Engineering

Feature tuning, particularly scaling, is critical for many algorithms.
Normalization maps data into a bounded range, typically \[0,1\], and is
appropriate when approximate upper and lower bounds are known and the
distribution is roughly uniform, such as with age. Standardization
transforms data to zero mean and unit variance, which is better when
algorithms assume Gaussian distributions, such as linear models, and is
less sensitive to outliers. Decimal scaling normalizes by moving the
decimal point until values fall within a standard range. A key guideline
is to fit scalers on the training data only and then apply them
consistently to both training and test sets.

Feature engineering expands the process further by focusing on the
features themselves. Extraction aims to create informative variables
from raw data. Selection identifies and keeps only the most useful
features, removing redundant or irrelevant ones. Construction involves
creating new features by polynomial expansion, feature crossing, or
domain-specific logic. Transformation techniques include discretization,
where continuous variables are converted into categories, and encoding,
where categorical features are converted into numerical representations.
Discretization, also called binning, may use equal-width partitions,
which divide the range into intervals of equal size, or equal-depth
partitions, which ensure each interval contains roughly the same number
of samples. Encoding categorical features can be done through label
encoding or through one-hot encoding, which creates binary variables.
Some algorithms, such as naïve Bayes or decision trees, naturally
benefit from discrete inputs.

## 7) Challenges of Machine Learning

These challenges in preparing and transforming data feed directly into
the broader challenges of machine learning. Training data may be
insufficient or not representative, leading to poor generalization.
Model selection involves balancing the risks of underfitting, where the
model is too simple, and overfitting, where the model is too complex and
captures noise. Proper validation and testing procedures are required to
evaluate models fairly.

## 8) Inductive Learning Hypothesis

Underlying all this is the inductive learning hypothesis: if a
hypothesis approximates the target function well on a sufficiently large
set of training examples, it will likely generalize well to unseen
examples. Induction in machine learning is essentially prediction: given
examples of a function mapping inputs X to outputs F(X), we aim to
predict F(X) for new values of X. Classification problems involve
discrete outputs, regression involves continuous outputs, and
probability estimation involves predicting likelihoods. Hypotheses can
vary in generality, from the most general assumption that every case is
positive, to the most specific that none are. The balance between these
extremes shapes learning.
