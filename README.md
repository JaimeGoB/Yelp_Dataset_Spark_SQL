# Yelp_Dataset_Spark_SQL


# Datasets 
The datasets were stored in Spark SQL tables. 

### Business 
**business.csv** file contains basic information about local businesses, and it contains the following columns:
* 'business_id':(a unique identifier for the business) 
* 'full_address': (localized address),
* 'categories': [(localized category names)]

### Reviews
**review.csv** file contains the star rating given by a user to a business. Use user_id to associate this review with others by the same user. Use business_id to associate this review with others of the same business. This file contains the following columns:
* 'review_id': (a unique identifier for the review) 
* 'user_id': (theidentifierofthereviewedbusiness), 
* 'business_id': (the identifier of the authoring user),
* 'stars': (star rating, integer 1-5), the rating given by the user to a business.

### Users
**user.csv** file contains aggregate information about a single user. This file contains the following columns:
* ‘user_id': (unique user identifier),
* 'name': (first name, last initial, like 'Matt J.'), this column has been
made anonymous to preserve privacy, 
* 'url': url of the user on Yelp.


#### Compute the total number of posted reviews and average number of stars for each State. Display these aggregated figures sorted by the average ratings.

|state|total_number_reviews|average_rating_per_state|
|-----|--------------------|------------------------|
|   NC|                7620|       3.826771653543307|
|   ON|                  76|      3.8157894736842106|
|   IN|                2829|       3.767762460233298|
|   TX|               22482|      3.7565163241704473|
|   IL|                6758|      3.7133767386800827|
|   Na|                1042|       3.682341650671785|
|   CA|              130139|       3.679050861002467|
|   MI|               10910|      3.6774518790100825|
|   GA|               14496|      3.6709437086092715|
|   WA|               16816|      3.6610965746907707|
|   RI|               10313|      3.6569378454377968|
|   MA|               51334|      3.6215568628978843|
|   PA|               18862|       3.572102640229032|
|   NY|               22172|       3.553490889410067|
|   VA|                1436|       3.548050139275766|
|   NJ|                7337|      3.5420471582390625|
|   MD|                5449|      3.5068819966966416|

#### List the 'user id', 'name' and average 'rating' of users that reviewed businesses classified as “Colleges & Universities” in list of categories. Note that the average rating must be computed over all the ratings posted by the user ids and not only the ratings related to businesses classified as “Colleges & Universities” .

|             user_id|       name|all_reviews_rating_average|
|--------------------|-----------|--------------------------|
|ojm14lh_LrlO_-XXH...|     Len L.|                       4.6|
|SRjFsLFbRl2GMVSX1...|    Marc B.|                       3.5|
|R_ID5xU9Mm78pH9pJ...|    Huan L.|                     4.125|
|CSIc4hf87BEQC3sdx...| Destany L.|                       5.0|
|q6UCOzZHK3L4gpxgw...|      J. B.|         3.826923076923077|
|T6jCRh9Qi6bzAp-TG...|    Dave N.|                       3.6|
|HFZHPHHEIzn-gqTld...|  Nicole B.|                       4.0|
|twV69QQrEZTxVwH20...|   Scott Z.|                       5.0|
|Ofj4dQb8FOA1ukRbD...|Michelle N.|        3.2857142857142856|
|UlF7L8wyiAMK4ijiE...|    dave d.|                       5.0|
|Ucah-9vTsgDlBstPM...|Harrison W.|                      2.75|
|spuLpDcMQOdixxBUr...|    Dave L.|                       4.5|
|ZIowdUve-IjIN-EgQ...| natasha s.|                       4.0|
|9S0VFqNFSi-75y6eI...|  Robert S.|                       3.2|
|3F4jxfkqZN76wZuSF...|   Haley S.|                       4.2|
|qN0rmMRWS7hHGfi3e...|       A A.|        3.3333333333333335|
|qZqqd0ZleZ7k1Vgdc...| Roberto A.|                       4.0|
|U4INQZOPSUaj8hMjL...| Michael U.|         4.416666666666667|
|dCATwLTGaDZAbSFxA...|     Jen F.|         2.870967741935484|
|W-k23QYJjbWmieyH6...|  Deanna G.|                       3.5|


#### List the business_id, full address and categories of the Top 10 businesses located in “NY” using the average ratings. Display the results sorted by average rating.

|         business_id|        full_address|          categories|avg(stars)|
|--------------------|--------------------|--------------------|----------|
|LScpEFvKvx9JH5oQG...|2258 15th StTroy,...|List(Auto Repair,...|       5.0|
|8BuQKohXzZGK5Bx1i...|221 W 107th StMan...|List(Churches, Re...|       5.0|
|00rrqw4O0Flfatd0V...|301 Cathedral Pkw...|List(Local Servic...|       5.0|
|1KWaczlXfDi9Z3urq...|1080 Danby RdItha...|List(Food, Bakeri...|       5.0|
|1utXwCsWjsULq3Trj...|601 W 114 StMorni...|List(Specialty Sc...|       5.0|
|7NiTUyoXawiCHxx_U...|Bayberry Square63...|List(Massage, Bea...|       5.0|
|Bu-D_mYJWctqUsqXZ...|Goldwin Smith Hal...|List(Cafes, Resta...|       5.0|
|4zbi6yjv64spii1Ol...|40 Catherwood RdI...|List(Arts & Enter...|       5.0|
|CLnsQyp0ndsCDFoKg...|Queen of Tarts143...|List(Food, Bakeri...|       5.0|
|5BAeOZKdi9ZG49UXd...|Lynah RinkCampus ...|List(Active Life,...|       5.0|


#### List the 'user id', 'name' and average 'rating' of users that reviewed businesses located in more than one State.

|             user_id|       name|        avg(stars)|
|--------------------|-----------|------------------|
|_xgjhgNZ5H6qQoluj...|     Lee G.|3.1818181818181817|
|Wc4KQbyJOWv4U5Zms...|   Betty H.|3.6923076923076925|
|Bf87HcPERF9yiSjb2...|   Kevin S.|3.4285714285714284|
|bN25cOkFDluT1NjMN...|   KaThy T.|               4.0|
|6zvkp8OaEheQwlDeL...|       E K.|               3.0|
|GSsQ_AybkmJvT-PDh...|   Candi K.| 4.333333333333333|
|g30HN1yaLAwS1WFI2...|   Brian M.|               4.0|
|ePilZ3GMYOIVzE-LC...|Annmarie L.|               4.0|
|YoZaupmfhnR3T4tMa...|   Loree B.|               4.0|
|oE_z5Xa9pjqPRmMNu...| Jessica N.|              3.25|
|AnxhKq7H6swc-OffZ...|     Ken M.|              3.25|
|cD2te7Lsf85xYYYrs...|   Sarah T.| 3.619047619047619|
|DIfU9Bzh5soyEqcg5...|   Tulsi P.|              4.75|
|HdQ8mcCXNxUqsFgTf...|   David A.|3.7142857142857144|
|o_naR5UiF1GJMDZ7D...|   annie w.| 4.214285714285714|
|bJ5FtCtZX3ZZacz2_...|    Bill M.|3.8533333333333335|
|x62hW5KIfIGFLD93b...|  cranky p.|               4.0|
|Sfgfz2Awh2EGPJvoE...|   Peter H.|              4.25|
|khWps7J16XT6B9YHb...|     Eva K.| 4.166666666666667|
|PgWTn7gY1hZ1saa0H...|  Hannah G.|               4.5|

