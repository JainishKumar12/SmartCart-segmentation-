# Description of my repo -
This project is a Smart Cart Segmentation System built using Unsupervised Machine Learning techniques.
The goal of this project is to group similar carts/customers together based on their shopping behavior so we can better understand patterns and create meaningful segments.

->PROJECT WORKFLOW :-
# Feature Engineering (Data Cleaning) -
Before applying any ML model, the dataset was cleaned properly by:
>> handling missing values .
>> removing unnecessary or irrelevant columns .
>> creating new useful features for better segmentation .

# Exploratory Data Analysis (EDA) -
A lot of focus was given to visualization in order to understand the dataset and take better decisions.
>> Plots used:
1. Pairplot (for feature relationships)
2. Heatmap (to analyze correlation between numeric columns)
3. 3D Scatterplots using both Matplotlib and Plotly (for cluster visualization)

# Encoding -
I have used One Hot Encoding for catagorical features to covert them into numric columns .

# Feature Scaling - 
To ensure all features contribute equally in distance-based clustering, the data was scaled using:
> StandardScaler

# Dimensionality Reduction -
To reduce feature space complexity and improve clustering performance, PCA (Principal Component Analysis) was applied.

# Unsupervised Learning -
1. Finding Optimal K (Number of Clusters)
To find the best cluster value, multiple methods were used:
> Elbow Method (Manual)
> KneeLocator
> Silhouette Score

-> Combined visualization using both Elbow & Silhouette to choose the best possible K . This helped ensure the K value wasn’t chosen randomly and had proper reasoning behind it .

2. Models Implemented
Two unsupervised clustering models were used:
>> K-Means Clustering -
used for main segmentation and it works well for distance-based clustering .

>> Agglomerative Clustering - 
used for comparison and helps validate whether cluster patterns match KMeans results .
>> Unsupervised model :
I have used Kmeans and Agglomerative Clustering to see the relation between our clusters using our optimal k and understand the characterstics of our clusters .

# Cluster Insights ->
After applying clustering, the clusters were analyzed and interpreted based on their feature distributions.

Cluster 0 — Average Customers / Balanced Buyers ->
1. Income: ~40,573 (moderate)
2. Total Spending: ~242 (low-moderate)
3. Web Visits/Month: ~6.3 (high browsing)
4. Response: 0.078 (very low response rate)
Meaning:
These people browse a lot but don’t spend much.
They are likely window shoppers / average buyers.

Cluster 1 — High Income, High Engagement Customers
1. Income: ~68,048 (high)
2. Total Spending: ~1105 (very high)
3. Store Purchases: ~8.1 (high)
4. Catalog Purchases: ~4.64 (high)
5. Tenure: ~385 days (highest loyalty)
6. Response: 0.313 (highest response rate)
Meaning:
These are your premium loyal customers, very valuable segment.

Cluster 2 — Low Income, Low Spending Customers (Weak Segment)
1. Income: ~35,123 (lowest)
2. Total Spending: ~119 (lowest)
3. Store Purchases: ~3.27 (low)
4. Catalog Purchases: ~0.64 (very low)
5. Web Visits/Month: ~6.66 (highest browsing)
6. Complaints: 0.0128 (highest complaint rate)
Meaning:
These people visit a lot but don’t buy much.
They also complain more.
This looks like low value / high friction customers.

Cluster 3 — Rich Big Spenders (Top Customers)
1. Income: ~73,626 (highest)
2. Total Spending: ~1270 (highest spending)
3. Catalog Purchases: ~5.67 (highest)
4. Web Purchases: ~5.67 (high)
5. Store Purchases: ~8.67 (highest store purchases)
6. Response: 0.171 (moderate response rate)
Meaning:
This is your VIP segment.
They spend the most and purchase frequently across multiple channels.

# Business Recommendations (Cluster-Based Strategy)
• Cluster 0: Give small discounts + personalized recommendations to convert browsers into buyers.
• Cluster 1: Offer loyalty rewards and exclusive premium deals to retain high-value customers.
• Cluster 2: Improve support and provide essential discounts to reduce complaints and increase engagement.
• Cluster 3: Provide VIP benefits, premium bundles, and upselling offers to maximize revenue.