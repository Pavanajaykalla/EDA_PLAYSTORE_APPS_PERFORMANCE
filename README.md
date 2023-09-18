# EDA_PLAYSTORE_APPS_PERFORMANCE
Google Play Store wants to develop a feature that would enable them to boost visibility for the most promising apps
Now, this analysis would require a preliminary understanding of theyou have plotted a distribution plot to check the distribution of ratings using both the Matplotlib function and the Seaborn functions. features that define a well-performing app. For which, you can ask questions like:

>Does a higher size or price of an app necessarily mean that it would perform better than the other apps? 
Or
>Does a higher number of installs give a clear picture of which app would have a better rating than others?
**DATA HANDING & CLEANING:**
>The dataset contains a total of 10,841 apps and 13 features or columns
>We have gone through the data set briefly & performed some basic data-cleaning tasks by handling the null values and then converting all the columns having the incorrect data types to the correct ones.
>Once the data is having the columns with right data types & we did sanity checks & dealt with the outliers.
The following are the highlights of sanity checks:
>Rating is between 1 and 5 for all the apps.
>Number of Reviews is less than or equal to the number of Installs.
>Free Apps shouldn’t have a price greater than 0.
On further inspection, we have observed that a lot of junk apps with 'I am rich' string having those outlier values. Removing them and then inspecting only the paid apps using the pandas boxplot tool:
>After inspecting the entries having Price greater than 30, we went ahead and removed them as well. Finally, we were left with 9338 records.
>This revealed that lots of pre-installed and superstar apps are present in the data. These apps won’t be useful for our analysis since they already have skewed statistics (an extremely high number of installs and reviews), which is not common for a majority of the rest of the apps. Hence, we took a qualifier of 1 million reviews and removed all the apps having more reviews.
>We have plotted a distribution plot to check the distribution of ratings using both the Matplotlib function and the Seaborn functions.
>So after the data handling tasks, we went ahead and plotted the total number of records in each category of Content Rating using the pie chart and the bar graph in matplotlib.
You understood the reasons why a pie chart is not very much preferred in cases where there are 3 more categories to be plotted. Essentially, it is very difficult to assess the difference between the different categories when their proportions are pretty similar as seen in the following pie chart:
![image](https://github.com/Pavanajaykalla/EDA_PLAYSTORE_APPS_PERFORMANCE/assets/129858752/a97b9cf8-b386-40b4-8377-aeebe69fb60a)
However, this problem is easily overcome with the bar graph, where there are clear visual cues with the length of the bars that portray the difference between the categories succinctly. In fact, you can draw a horizontal bar graph as well to make the difference much more apparent. Both the views are shown in the images below
>![image](https://github.com/Pavanajaykalla/EDA_PLAYSTORE_APPS_PERFORMANCE/assets/129858752/1566f66f-f719-4cea-a70b-c2e39e22303b)
We can clearly see that ‘Everyone’ category has the highest number of apps followed by Teen and Mature 17+.
We have utilised the jointplot() functionality of seaborn to plot it and observed the following results:
 ![image](https://github.com/Pavanajaykalla/EDA_PLAYSTORE_APPS_PERFORMANCE/assets/129858752/196badf1-c16b-49b5-8f2d-8b13c5de7eb4)
Here, you get a bird’s eye view of the spread of ratings for the different categories: median, 75th percentiles, fences, etc. The immediate insight that you obtained from the above view are:

That “Everyone” category has the highest number of ratings in the lower percentiles as compared to the other categories.
The median values are all comparable, which was discovered in the previous views as well.
The upper fences for all the categories get capped at 5.0, whereas there are some observable differences in the lower fences.
![image](https://github.com/Pavanajaykalla/EDA_PLAYSTORE_APPS_PERFORMANCE/assets/129858752/aa5a8108-ef10-4388-83e3-00621cbe00e1)
![image](https://github.com/Pavanajaykalla/EDA_PLAYSTORE_APPS_PERFORMANCE/assets/129858752/b2b05f48-76fe-4eb2-a573-c0b196f7a516)
**summary of case study:**

>First, we did a fair bit of data handling and cleaning - cleaning junk records, adding missing values, changing data types, remove outliers, etc.
>When we analysed the ratings using the histogram, we saw that they are skewed towards higher ratings.
>Using a bar chart, we saw that most of the apps belong to the Everyone category.
>We also observed a weak trend between the ratings and the size of the app, using a scatter-plot. We also briefly forayed to reg plots to understand its nuances.
>Using a pair-plot, we were able to see multiple scatter plots and draw several inferences, for example, price and rating having very weak trend, reviews and price being inversely related and so on.
>After that, we utilised estimator functions along with bar plots as well as box plots to observe the spread of ratings across the different Content Rating Categories. Here, our main observation was that Everyone category has a lot of apps having very low ratings.
>Finally, we created a heat map comparing the ratings across different Reviews and Content Rating buckets.
