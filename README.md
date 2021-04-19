<!-- wp:heading -->
<h2>How Personality affects Heroin Consumption</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3><strong>Setting up the dataset for binary classification</strong></h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>For each drug, an individual falls under one of 7 classes—CL0, CL1, CL2, CL3, CL4, CL5, and CL6.&nbsp;CL0 means that the individual never used the drug, CL1 means the individual used the drug over a decade ago, CL2 means the individual used the drug within the last decade; and CL3, CL4, CL5, and CL6 mean the individual used the drug in the last year, in the last month, in the last week, and in the last day, respectively.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>First, I took the .data file and converted it into a .csv file.&nbsp;I restricted the dataset to the drug heroin by deleting all the columns for the other drugs.&nbsp;I then added a new column “User” that has value 0 if the individual falls under CL0 or CL1—the individual is not considered a User.&nbsp;Otherwise, the individual falls under CL2, CL3, CL4, CL5, or CL6; in this case, the value is 1—the individual is considered a User.&nbsp;This gives a binary classification problem for classifying individuals as User or Not User.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>I took a random sample of the heroin dataset using excel.&nbsp;Then, I broke up the dataset into two separate csv files: one containing 80% of the data, the other containing 20% of the data.&nbsp;The set containing 80% is our training set, and the set containing 20% is our test set.&nbsp;&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3><strong>Visualizing the data</strong></h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>For this section, I’m going to use the entire dataset for heroin consumption.&nbsp;Let’s look at heroin consumption by gender.&nbsp;Here is a graph for the number of users for each gender.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":365} -->
<figure class="wp-block-image"><img src="https://www.onlinemathtraining.com/wp-content/uploads/2019/10/image.png" alt="" class="wp-image-365"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>As you can see, there are about the same number of males as females in the population.&nbsp;For both genders, only a small fraction are heroin users, and there are about twice as many male heroin users as female heroin users.&nbsp;We can test whether gender is statistically significant using the chi-squared test:</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td></td><td></td><td></td><td></td></tr><tr><td>
  Chi-Squared Test
  </td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td>
  Observed
  </td><td></td><td></td><td></td></tr><tr><td></td><td>
  Not User
  </td><td>
  User
  </td><td></td></tr><tr><td>
  Male 
  </td><td>
  797
  </td><td>
  146
  </td><td>
  943
  </td></tr><tr><td>
  Female
  </td><td>
  876
  </td><td>
  66
  </td><td>
  942
  </td></tr><tr><td></td><td>
  1673
  </td><td>
  212
  </td><td>
  1885
  </td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td>
  Expected
  </td><td></td><td></td><td></td></tr><tr><td></td><td>
  Not User
  </td><td>
  User
  </td><td></td></tr><tr><td>
  Male
  </td><td>
  836.9437666
  </td><td>
  106.056233
  </td><td>
  943
  </td></tr><tr><td>
  Female
  </td><td>
  836.0562334
  </td><td>
  105.943767
  </td><td>
  942
  </td></tr><tr><td></td><td>
  1673
  </td><td>
  212
  </td><td>
  1885
  </td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td>
  P-value
  </td><td>
  5.74672E-09
  </td><td></td><td></td></tr><tr><td>
  Significance Level
  </td><td>
  0.05
  </td><td></td><td></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>Since the p-value is less than the significance level, gender is statistically significant.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Let’s look at the percentages of users by country.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":368} -->
<figure class="wp-block-image"><img src="https://www.onlinemathtraining.com/wp-content/uploads/2019/10/image-1.png" alt="" class="wp-image-368"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>As you can see, the USA and UK have the largest representation in the sample.&nbsp;Most of the heroin users in the sample are from the USA.&nbsp;Applying the chi-squared test, we can check that country is statistically significant:</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>
  <strong>Column1</strong>
  </td><td>
  <strong>Column2</strong>
  </td><td>
  <strong>Column3</strong>
  </td><td>
  <strong>Column4</strong>
  </td></tr><tr><td>
  Chi-Squared Test
  </td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td>
  Observed
  </td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td>
  Country
  </td><td>
  Not User
  </td><td>
  User
  </td><td></td></tr><tr><td>
  -0.57009
  </td><td>
  412
  </td><td>
  145
  </td><td>
  557
  </td></tr><tr><td>
  -0.46841
  </td><td>
  3
  </td><td>
  2
  </td><td>
  5
  </td></tr><tr><td>
  -0.28519
  </td><td>
  107
  </td><td>
  11
  </td><td>
  118
  </td></tr><tr><td>
  -0.09765
  </td><td>
  48
  </td><td>
  6
  </td><td>
  54
  </td></tr><tr><td>
  0.21128
  </td><td>
  18
  </td><td>
  2
  </td><td>
  20
  </td></tr><tr><td>
  0.24923
  </td><td>
  75
  </td><td>
  12
  </td><td>
  87
  </td></tr><tr><td>
  0.96082
  </td><td>
  1,010
  </td><td>
  34
  </td><td>
  1044
  </td></tr><tr><td></td><td>
  1673
  </td><td>
  212
  </td><td>
  1885
  </td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td>
  Expected
  </td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td>
  Country
  </td><td>
  Not User
  </td><td>
  User
  </td><td></td></tr><tr><td>
  -0.57009
  </td><td>
  494.3559682
  </td><td>
  62.6440318
  </td><td>
  557
  </td></tr><tr><td>
  -0.46841
  </td><td>
  4.437665782
  </td><td>
  0.56233422
  </td><td>
  5
  </td></tr><tr><td>
  -0.28519
  </td><td>
  104.7289125
  </td><td>
  13.2710875
  </td><td>
  118
  </td></tr><tr><td>
  -0.09765
  </td><td>
  47.92679045
  </td><td>
  6.07320955
  </td><td>
  54
  </td></tr><tr><td>
  0.21128
  </td><td>
  17.75066313
  </td><td>
  2.24933687
  </td><td>
  20
  </td></tr><tr><td>
  0.24923
  </td><td>
  77.21538462
  </td><td>
  9.78461538
  </td><td>
  87
  </td></tr><tr><td>
  0.96082
  </td><td>
  926.5846154
  </td><td>
  117.415385
  </td><td>
  1044
  </td></tr><tr><td></td><td>
  1673
  </td><td>
  212
  </td><td>
  1885
  </td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td>
  P-value
  </td><td>
  3.70058E-39
  </td><td></td><td></td></tr><tr><td>
  Signif Level
  </td><td>
  0.05
  </td><td></td><td></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>Since the p-value is less than 0.05, country is statistically significant.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Let’s see how Impulsivity affects the percentage of users:</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":369} -->
<figure class="wp-block-image"><img src="https://www.onlinemathtraining.com/wp-content/uploads/2019/10/image-2.png" alt="" class="wp-image-369"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>As the Impulsive score increases, the percentage of users increases.&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>We can apply the Chi-Squared test to check whether Impulsivity is statistically significant:</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>
  <strong>&nbsp;</strong>
  </td><td>
  <strong>&nbsp;</strong>
  </td><td>
  <strong>&nbsp;</strong>
  </td><td>
  <strong>&nbsp;</strong>
  </td></tr><tr><td>
  Chi-Squared Test
  </td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td>
  Observed
  </td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td>
  Impulsive
  </td><td>
  Not User
  </td><td>
  User
  </td><td></td></tr><tr><td>
  -2.55524
  </td><td>
  20
  </td><td>
  0
  </td><td>
  20
  </td></tr><tr><td>
  -1.37983
  </td><td>
  269
  </td><td>
  7
  </td><td>
  276
  </td></tr><tr><td>
  -0.71126
  </td><td>
  282
  </td><td>
  25
  </td><td>
  307
  </td></tr><tr><td>
  -0.21712
  </td><td>
  329
  </td><td>
  26
  </td><td>
  355
  </td></tr><tr><td>
  0.19268
  </td><td>
  231
  </td><td>
  26
  </td><td>
  257
  </td></tr><tr><td>
  0.52975
  </td><td>
  185
  </td><td>
  31
  </td><td>
  216
  </td></tr><tr><td>
  0.88113
  </td><td>
  155
  </td><td>
  40
  </td><td>
  195
  </td></tr><tr><td>
  1.29221
  </td><td>
  119
  </td><td>
  29
  </td><td>
  148
  </td></tr><tr><td>
  1.86203
  </td><td>
  79
  </td><td>
  25
  </td><td>
  104
  </td></tr><tr><td>
  2.90161
  </td><td>
  4
  </td><td>
  3
  </td><td>
  7
  </td></tr><tr><td></td><td>
  1673
  </td><td>
  212
  </td><td>
  1885
  </td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td>
  Expected
  </td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td>
  Impulsive
  </td><td>
  Not User
  </td><td>
  User
  </td><td></td></tr><tr><td>
  -2.55524
  </td><td>
  17.75066313
  </td><td>
  2.24933687
  </td><td>
  20
  </td></tr><tr><td>
  -1.37983
  </td><td>
  244.9591512
  </td><td>
  31.0408488
  </td><td>
  276
  </td></tr><tr><td>
  -0.71126
  </td><td>
  272.472679
  </td><td>
  34.527321
  </td><td>
  307
  </td></tr><tr><td>
  -0.21712
  </td><td>
  315.0742706
  </td><td>
  39.9257294
  </td><td>
  355
  </td></tr><tr><td>
  0.19268
  </td><td>
  228.0960212
  </td><td>
  28.9039788
  </td><td>
  257
  </td></tr><tr><td>
  0.52975
  </td><td>
  191.7071618
  </td><td>
  24.2928382
  </td><td>
  216
  </td></tr><tr><td>
  0.88113
  </td><td>
  173.0689655
  </td><td>
  21.9310345
  </td><td>
  195
  </td></tr><tr><td>
  1.29221
  </td><td>
  131.3549072
  </td><td>
  16.6450928
  </td><td>
  148
  </td></tr><tr><td>
  1.86203
  </td><td>
  92.30344828
  </td><td>
  11.6965517
  </td><td>
  104
  </td></tr><tr><td>
  2.90161
  </td><td>
  6.212732095
  </td><td>
  0.7872679
  </td><td>
  7
  </td></tr><tr><td></td><td>
  1673
  </td><td>
  212
  </td><td>
  1885
  </td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td>
  P-value
  </td><td>
  1.28149E-14
  </td><td></td><td></td></tr><tr><td>
  Signif Level
  </td><td>
  0.05
  </td><td></td><td></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>Since the p-value is less than the significance level, Impulsivity is statistically significant.&nbsp;&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>As the Impulsive score increases, the percentage of users increases .&nbsp;A similar effect can be seen with Nscore:</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":370} -->
<figure class="wp-block-image"><img src="https://www.onlinemathtraining.com/wp-content/uploads/2019/10/image-3.png" alt="" class="wp-image-370"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>The same thing can be seen with SS:</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":371} -->
<figure class="wp-block-image"><img src="https://www.onlinemathtraining.com/wp-content/uploads/2019/10/image-4.png" alt="" class="wp-image-371"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>The opposite effect is seen with Ascore:</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":372} -->
<figure class="wp-block-image"><img src="https://www.onlinemathtraining.com/wp-content/uploads/2019/10/image-5.png" alt="" class="wp-image-372"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>The percentage of users is higher for lower Ascores.&nbsp;We can see this more clearly by normalizing the bars:</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":373} -->
<figure class="wp-block-image"><img src="https://www.onlinemathtraining.com/wp-content/uploads/2019/10/image-6.png" alt="" class="wp-image-373"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Similarly, the percentage of users is higher for lower levels of education:</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":374} -->
<figure class="wp-block-image"><img src="https://www.onlinemathtraining.com/wp-content/uploads/2019/10/image-7.png" alt="" class="wp-image-374"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>We can see this better by normalizing the bars:</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":375} -->
<figure class="wp-block-image"><img src="https://www.onlinemathtraining.com/wp-content/uploads/2019/10/image-8.png" alt="" class="wp-image-375"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>The Chi-squared test was applied to Nscore, SS, Ascore, and Education; all were found to be statistically significant.&nbsp;In contrast, applying the chi-squared test to Escore gives a p-value of 0.156615315, which is greater than 0.05.&nbsp;Therefore, Escore is not statistically significant.&nbsp;Ethnicity also turns out to be statistically insignificant.&nbsp;Interestingly, Cscore and Age turn out to be statistically significant although we will eliminate them in backward elimination when building the model.&nbsp;There does seem to be a relationship between Cscore and whether or not the individual is a user:</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":376} -->
<figure class="wp-block-image"><img src="https://www.onlinemathtraining.com/wp-content/uploads/2019/10/image-9.png" alt="" class="wp-image-376"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>The percentage of users is higher for lower Cscores.&nbsp;Similarly, the percentage of users is higher for younger individuals:</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":377} -->
<figure class="wp-block-image"><img src="https://www.onlinemathtraining.com/wp-content/uploads/2019/10/image-10.png" alt="" class="wp-image-377"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3><strong>Building a Logistic Regression Model</strong></h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Using gretl, I applied logistic regression to the training set.&nbsp;In logistic regression, our model will give us a probability for each individual—namely, the probability that the individual is a User.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>First, I used backward elimination to eliminate some of the independent variables using the threshold of 0.05 for p-value.&nbsp;In this way, I was able to eliminate Escore, Cscore, Age, and Ethnicity.&nbsp;At this point, here is what our logistic regression model in gretl looks like:</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Model
32: Logit, using observations 1-1508</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Dependent
variable: User</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Standard
errors based on Hessian</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>
  <em>&nbsp;</em>
  </td><td>
  <em>Coefficient</em>
  </td><td>
  <em>Std.
  Error</em>
  </td><td>
  <em>z</em>
  </td><td>
  <em>p-value</em>
  </td><td>
  &nbsp;
  </td></tr><tr><td>
  const
  </td><td>
  −2.35671
  </td><td>
  0.118925
  </td><td>
  −19.82
  </td><td>
  &lt;0.0001
  </td><td>
  ***
  </td></tr><tr><td>
  Gender
  </td><td>
  −0.491813
  </td><td>
  0.203406
  </td><td>
  −2.418
  </td><td>
  0.0156
  </td><td>
  **
  </td></tr><tr><td>
  Nscore
  </td><td>
  0.279726
  </td><td>
  0.0952334
  </td><td>
  2.937
  </td><td>
  0.0033
  </td><td>
  ***
  </td></tr><tr><td>
  Ascore
  </td><td>
  −0.233985
  </td><td>
  0.0926942
  </td><td>
  −2.524
  </td><td>
  0.0116
  </td><td>
  **
  </td></tr><tr><td>
  Impulsive
  </td><td>
  0.300076
  </td><td>
  0.118098
  </td><td>
  2.541
  </td><td>
  0.0111
  </td><td>
  **
  </td></tr><tr><td>
  SS
  </td><td>
  0.236009
  </td><td>
  0.127718
  </td><td>
  1.848
  </td><td>
  0.0646
  </td><td>
  *
  </td></tr><tr><td>
  Education
  </td><td>
  −0.193636
  </td><td>
  0.107405
  </td><td>
  −1.803
  </td><td>
  0.0714
  </td><td>
  *
  </td></tr><tr><td>
  Oscore
  </td><td>
  0.181861
  </td><td>
  0.101459
  </td><td>
  1.792
  </td><td>
  0.0731
  </td><td>
  *
  </td></tr><tr><td>
  Country
  </td><td>
  −1.00028
  </td><td>
  0.151742
  </td><td>
  −6.592
  </td><td>
  &lt;0.0001
  </td><td>
  ***
  </td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>
  Mean dependent
  var
  </td><td>
  &nbsp;0.112732
  </td><td>
  &nbsp;
  </td><td>
  S.D. dependent
  var
  </td><td>
  &nbsp;0.316370
  </td></tr><tr><td>
  McFadden R-squared
  </td><td>
  &nbsp;0.187395
  </td><td>
  &nbsp;
  </td><td>
  Adjusted
  R-squared
  </td><td>
  &nbsp;0.170449
  </td></tr><tr><td>
  Log-likelihood
  </td><td>
  −431.5763
  </td><td>
  &nbsp;
  </td><td>
  Akaike
  criterion
  </td><td>
  &nbsp;881.1526
  </td></tr><tr><td>
  Schwarz
  criterion
  </td><td>
  &nbsp;929.0194
  </td><td>
  &nbsp;
  </td><td>
  Hannan-Quinn
  </td><td>
  &nbsp;898.9800
  </td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>Number
of cases 'correctly predicted' = 1334 (88.5%)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>f(beta'x)
at mean of independent vars = 0.316</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Likelihood
ratio test: Chi-square(8) = 199.051 [0.0000]</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>As you can see, the p-value for Oscore is greater than 0.05; however, removing Oscore from the model decreases the Adjusted R-squared value to 0.169289.&nbsp;So, I decided to keep Oscore as well as Education and SS.&nbsp;I checked for collinearity, and there were no signs of collinearity.&nbsp;The accuracy rate of the model is 88.5%.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3><strong>Assessing the model</strong></h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Here is what the CAP curve looks like:</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":378} -->
<figure class="wp-block-image"><img src="https://www.onlinemathtraining.com/wp-content/uploads/2019/10/image-11.png" alt="" class="wp-image-378"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Our training set is ordered by our logistic regression model from highest predicted probability to lowest predicted probability.&nbsp;The horizontal axis measures the percentage of the population of individuals considered.&nbsp;The vertical axis measures the percentage of the population of users in our training set.&nbsp;The red curve, at x% on the horizontal axis, measures the number of users identified out of the first x% of our training set (as ordered by our model) divided by the total number of users in our training set.&nbsp;The blue line is the performance of the random model.&nbsp;As you can see from the CAP curve, our logistic regression model is good.&nbsp;At x=50%, our CAP curve is approximately 90%.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Next, we applied our model to the test set and created the CAP curve for our test set.&nbsp;The test set is ordered by our logistic regression model from highest predicted probability to lowest predicted probability.&nbsp;Here is the CAP curve for our test set:</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":379} -->
<figure class="wp-block-image"><img src="https://www.onlinemathtraining.com/wp-content/uploads/2019/10/image-12.png" alt="" class="wp-image-379"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>At x=50%, our CAP curve is approximately 95%.&nbsp;So our model is very good.&nbsp;What this CAP curve tells us is that, by ordering the list of individuals in our test set according to highest probability given by our model, we would have identified 95% of the users by considering the first 50% of the individuals in the list.&nbsp;If we were to consider a new set of individuals, we could potentially identify 95% of the users by considering only 50% of the individuals.&nbsp;The accuracy rate of our model on the test set is 89.9%.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Let’s take a look at the odds-ratios for the predictors:</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td></td><td>
  coefficient
  </td><td>
  p-value
  </td><td>
  Odds-ratio
  </td></tr><tr><td>
  const
  </td><td>
  -2.3567137
  </td><td>
  2.13E-87
  </td><td></td></tr><tr><td>
  Gender
  </td><td>
  -0.491812885
  </td><td>
  0.015610872
  </td><td>
  0.6115
  </td></tr><tr><td>
  Nscore
  </td><td>
  0.279725709
  </td><td>
  0.003311199
  </td><td>
  1.3228
  </td></tr><tr><td>
  Ascore
  </td><td>
  -0.233985148
  </td><td>
  0.011593878
  </td><td>
  0.7914
  </td></tr><tr><td>
  Impulsive
  </td><td>
  0.300075998
  </td><td>
  0.011056415
  </td><td>
  1.35
  </td></tr><tr><td>
  SS
  </td><td>
  0.236008533
  </td><td>
  0.064617594
  </td><td>
  1.2662
  </td></tr><tr><td>
  Education
  </td><td>
  -0.193636214
  </td><td>
  0.071409777
  </td><td>
  0.824
  </td></tr><tr><td>
  Oscore
  </td><td>
  0.181861329
  </td><td>
  0.073059336
  </td><td>
  1.1994
  </td></tr><tr><td>
  Country
  </td><td>
  -1.000278262
  </td><td>
  4.34E-11
  </td><td>
  0.3678
  </td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>As you can see, Impulsive, Nscore, SS, and Oscore have a positive correlation with their odds-ratios.&nbsp;On the other hand, Country, Gender, Ascore, and Education have a negative correlation with their odds-ratios.&nbsp;This suggests that increasing Impulsive, Nscore, SS, and Oscore correlates with increasing the probability that the individual is a user.&nbsp;On the other hand, increasing Ascore and Education correlates with decreasing the probability that the individual is a user.&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Recall that Cscore and Age were found to be statistically significant although they were not included in the model.&nbsp;I trained a new model by including them to see if it improves the model.&nbsp;Here is the new model in gretl:</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Model
1: Logit, using observations 1-1508</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Dependent
variable: User</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Standard
errors based on Hessian</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>
  <em>&nbsp;</em>
  </td><td>
  <em>Coefficient</em>
  </td><td>
  <em>Std.
  Error</em>
  </td><td>
  <em>z</em>
  </td><td>
  <em>p-value</em>
  </td><td>
  &nbsp;
  </td></tr><tr><td>
  const
  </td><td>
  −2.35386
  </td><td>
  0.119036
  </td><td>
  −19.77
  </td><td>
  &lt;0.0001
  </td><td>
  ***
  </td></tr><tr><td>
  Gender
  </td><td>
  −0.501279
  </td><td>
  0.204678
  </td><td>
  −2.449
  </td><td>
  0.0143
  </td><td>
  **
  </td></tr><tr><td>
  Nscore
  </td><td>
  0.289359
  </td><td>
  0.101232
  </td><td>
  2.858
  </td><td>
  0.0043
  </td><td>
  ***
  </td></tr><tr><td>
  Ascore
  </td><td>
  −0.234622
  </td><td>
  0.0928943
  </td><td>
  −2.526
  </td><td>
  0.0115
  </td><td>
  **
  </td></tr><tr><td>
  Impulsive
  </td><td>
  0.308060
  </td><td>
  0.122780
  </td><td>
  2.509
  </td><td>
  0.0121
  </td><td>
  **
  </td></tr><tr><td>
  SS
  </td><td>
  0.240555
  </td><td>
  0.129383
  </td><td>
  1.859
  </td><td>
  0.0630
  </td><td>
  *
  </td></tr><tr><td>
  Education
  </td><td>
  −0.204355
  </td><td>
  0.109989
  </td><td>
  −1.858
  </td><td>
  0.0632
  </td><td>
  *
  </td></tr><tr><td>
  Oscore
  </td><td>
  0.183988
  </td><td>
  0.102186
  </td><td>
  1.801
  </td><td>
  0.0718
  </td><td>
  *
  </td></tr><tr><td>
  Country
  </td><td>
  −1.01506
  </td><td>
  0.156544
  </td><td>
  −6.484
  </td><td>
  &lt;0.0001
  </td><td>
  ***
  </td></tr><tr><td>
  Cscore
  </td><td>
  0.0259174
  </td><td>
  0.102757
  </td><td>
  0.2522
  </td><td>
  0.8009
  </td><td>
  &nbsp;
  </td></tr><tr><td>
  Age
  </td><td>
  0.0396074
  </td><td>
  0.119620
  </td><td>
  0.3311
  </td><td>
  0.7406
  </td><td>
  &nbsp;
  </td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>
  Mean dependent
  var
  </td><td>
  &nbsp;0.112732
  </td><td>
  &nbsp;
  </td><td>
  S.D. dependent
  var
  </td><td>
  &nbsp;0.316370
  </td></tr><tr><td>
  McFadden
  R-squared
  </td><td>
  &nbsp;0.187567
  </td><td>
  &nbsp;
  </td><td>
  Adjusted
  R-squared
  </td><td>
  &nbsp;0.166856
  </td></tr><tr><td>
  Log-likelihood
  </td><td>
  −431.4846
  </td><td>
  &nbsp;
  </td><td>
  Akaike
  criterion
  </td><td>
  &nbsp;884.9692
  </td></tr><tr><td>
  Schwarz
  criterion
  </td><td>
  &nbsp;943.4731
  </td><td>
  &nbsp;
  </td><td>
  Hannan-Quinn
  </td><td>
  &nbsp;906.7582
  </td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>Number
of cases 'correctly predicted' = 1337 (88.7%)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>f(beta'x)
at mean of independent vars = 0.316</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Likelihood
ratio test: Chi-square(10) = 199.235 [0.0000]</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>As you can see, the accuracy rate is 88.7%, not much better than the accuracy rate of our original model.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Here is the CAP curve for our new model applied to the training set:</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":380} -->
<figure class="wp-block-image"><img src="https://www.onlinemathtraining.com/wp-content/uploads/2019/10/image-13.png" alt="" class="wp-image-380"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>At x=50%, the CAP curve is approximately 90%.&nbsp;The accuracy rate of the model on the training set is 88.66%.&nbsp;Thus, our new model is not much of an improvement over the original model.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>I applied the new model on the test set and got the following CAP curve.&nbsp;&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":381} -->
<figure class="wp-block-image"><img src="https://www.onlinemathtraining.com/wp-content/uploads/2019/10/image-14.png" alt="" class="wp-image-381"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>At x=50%, the curve is approximately 95%.&nbsp;The accuracy rate of the model on the test set is 89.9%.&nbsp;Thus, including Cscore and Age in the model does not improve the model by much.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Here are the odds-ratios for the predictors Cscore and Age:</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td></td><td>
  coefficient
  </td><td>
  p-value
  </td><td>
  Odds-ratio
  </td></tr><tr><td>
  Cscore
  </td><td>
  0.025917
  </td><td>
  0.80087
  </td><td>
  1.0263
  </td></tr><tr><td>
  Age
  </td><td>
  0.039607
  </td><td>
  0.740562
  </td><td>
  1.0404
  </td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>Since the coefficients for Cscore and Age are close to 0, they don’t contribute much to the probability that an individual is a user.&nbsp;It’s strange that Cscore and Age are statistically significant according to the chi-squared test and yet not necessary in the model.&nbsp;What could explain this is that Cscore is negatively correlated with Nscore and Impulsive and that Age is negatively correlated with SS.&nbsp;Here is a heatmap of the correlation matrix:</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":382} -->
<figure class="wp-block-image"><img src="https://www.onlinemathtraining.com/wp-content/uploads/2019/10/image-15.png" alt="" class="wp-image-382"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>The dataset can be found here: <a href="http://archive.ics.uci.edu/ml/datasets/Drug+consumption+%28quantified%29" rel="noreferrer noopener" target="_blank">http://archive.ics.uci.edu/ml/datasets/Drug+consumption+%28quantified%29</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>E. Fehrman, A. K. Muhammad, E. M. Mirkes, V. Egan and A. N. Gorban, "The Five Factor Model of personality and evaluation of drug consumption risk.," arXiv&nbsp;<a rel="noreferrer noopener" href="https://arxiv.org/abs/1506.06297" target="_blank">[Web Link]</a>, 2015</p>
<!-- /wp:paragraph -->
