Impact of traditional dishes on health
================

*   [Selecting a project (milestone 1)](#milestone_1)
    *   [Abstract](#abstract)
    *   [Research Question](#question)
    *   [Datasets](#datasets)
*   [Data collection and description (milestone 2)](#milestone_2)
*   [Final Analysis (milestone 3)](#milestone_3)
*   [Contributions](#contributions)


* * *

<h2 id="milestone_1">Selecting a project (milestone 1)</h2>

<h3 id="abstract">Abstract</h3>

In our present day society, the amount of variety we are offered when buying food products is unfathomable, and it can become difficult to make conscious and healthy changes to our regime. The first step towards a better lifestyle is acknowledging the impact that nutrition has on our health and our project is centered towards this goal. Using datasets containing cooking recipes from around the world and World Health Organization diseases data, we first associate a nutritious score (NS) indicating the healthiness of each recipe. The NS score is calculated following the equation recommended by the french government during the health law reform of 2016. We then attempt to compare nutritional habits with population health statistics from countries around the world, such as obesity and diabetes to study potential correlations. 

<h3 id="question">Research question</h3>

-  How significant is the impact of the different recipes around the world on modern diseases?

<h3 id="datasets">Datasets</h3>

As explained above, we will both be using the Open Food Facts Dataset containing nutritional information about tens of thousands of supermarket products (primarly from France), as well as the Stanford cooking recipe dataset, linking recipes to home countries. The cooking recipe dataset will be used to detemine which types of ingredients and cooking styles are used in the cuisine of different countries. It consists of a set of HTML web pages we will have to scrap (BeautifulSoup) to retrieve information about the ingredients, quantities, cooking styles, calories, etc... In order to determine the "healthiness" of the recipes, we will then need the data from the other dataset to get nutritional information about each recipe's ingredients. The open food fact dataset will be treated by parsing it knowing the delimeters are tabs and not commas, and we will add any missing nutritional information about common products with data scraps either from Google, or from specialized websites. We will also include statistics and datasets from the World Health Organization about mortality causes, diabetes, obesity to look at the health impact of the chosen diets. This will either be done by web scraps or by using the availables datasheets the World Health organizition provides on its website.


* * *

<h2 id="milestone_2">Data collection and description (milestone 2)</h2>

The jupyter notebook `Final_notebook.ipynb` contains all necessary code and information about the data collection and description. Reading the notebook will give more information about this milestone than solely looking at the Readme file. 

As explained in the notebook, the first part of the collected data represents scraps from about 400 recipes from different regions around the world. Each recipe is associated with a region, and a title, a rating, an ingredient list and nutritional content information. This data is generated from web scraps and smart parses from the www.allrecipes.com website, and is exported in both csv and json formats. We made sure to keep common references between the CSV table datas and the more hierarchic and raw JSON files, so as to be able to access directly from the CSV to information one of the JSON file exclusively contains. The  CSV files are cleaned of all missing values and have a consistent and verified format in each given row. The numerical information the rows contain (quantities, scores,...) all are associated with a unit when possible, and are in either integer or float format and correspond to ONE serving of each recipe. The JSON exclusively contains information about the ingredients (stored as a dictionnary of dictionnaries). This information is also extensively cleaned, by different processes. Unit and quantity detection is first applied to the ingredient lists, as well as several corrections and transformations when needed (ounces to grams for example). To begin the third milestone, textual analysis is also used to detect fruits and vegetables from the ingredient lists, and link them to a quantity. This is done through the webscrapping of yet another website with lists of vegetables and exported as the 'veggies.csv' file. This is further explained in the notebook and will be useful for calculations of the Nutriscore we intend to do in the third milestone. The data size of the parsed recipes (useful data) reduces to under a megabyte, which is well below the limits Pandas can handle. Data size will thus not be a problem! 

The second part of the data are tables from the World Health Organization (WHO) that represent food related diseases in each country and world region. We choose to study two diseases for the project that are diabetes and overweight (BMI > 25) / obesity (BMI > 30) on the adult population in 2017. In the notebook, the data is arranged such that it is best prepared for our next analyzis and is free of missing values. The values are expressed as the percentage of the population affected by each disease.

Similarly as before, our objectives for the third milestone remain to be able to associate to each recipe a 'Healthiness' score, using a metric approved by the french ministry of health, the NutriScore. This metric is computed by summing 'positive' nutrients and food attributes and substracting 'negative' ones using a well-defined formula and documentation. These attributes include sugar amounts, proteins, fibers, fats, all information that we have generated from the web scraps. Additional needed information for computing the NutriScore is the amount of vegetables and fruits in the recipes, which is the reason for the detection functions included in the notebook. With that Nutriscore information and different learning based clustering and/or clustering techniques, we will then analyze and try to find patterns in region's culinar culture, and try to find correlations and patterns between alimentation and health. 

* * *

<h2 id="milestone_3">Final Analysis (milestone 3)</h2>

The final analysis can be found in the report and the Final Jupyter notebook, linking the computed NutriScore of each recipe within world regions with the World Health Organization data about food related diseases. The technical details  of the different types of algortihms and conducted analysis (numerical, semantic, network), can be found in the updated notebook `Final_notebook.html` (this version allows us to see the Folium map showing the NutriScore in the output compared to the original Jupyter Notebook `Final_notebook.ipynb`). 

* * *

<h2 id="contributions">Contributions</h2>

- Romain Caristan: Find and parse health datasets, analyze nutriscores with health data, Nutri Score Folium map, writing report.
- Manuel Faysse: Build scrapbot to extract and clean data from website, try clustering algorithms on data, semantic similarity matrix of the ingredients.
- Rafael Rolli: Find correlations between health data and nutriments consumption, Canada case study, writing report.

Manuel will be our presenter for the poster presentation on January, 21 2019.
