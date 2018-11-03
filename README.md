# Impact of traditional dishes on health

# Abstract

In our present day society, the amount of variety we are offered when buying food products is unfathomable. The quantity of possibilities are so big they can be confusing, and it becomes difficult to make conscious and healthy changes to our regime. 
The datasets we elected to work on contain a) a set of cooking recipes from around the world and b) a food product database originally from France, that contains information about all of the products' macro and micro nutrients, and their caloric descriptions. In our project, we will extract traditional cooking recipes from different countries and link them to the recipe's ingredients encountered in the food product database. Our intention is to match every recipe with its nutritious content. The nutritious content is currently measured by a nutritious score (NS), with the equation provided in the food product dataset, and we will explore ways to improve it in given recipes. We will try to group cuisines from around the world in function of the ingredients used and the cooking styles. The objective is ultimately to recommend the use of healthier alternatives to the traditional recipes, provided their ingredients are found on the database and are nutritiously characterized by a NS.  We may also try to compare nutritional habits with population health statistics from countries around the world, such as life expectancy, obesity, diabetes, etc, to study a potential correlation.

# Research questions

- What is the impact of each product on the dishes we eat everyday and how can we preserve our food traditions without compromising our health?
- How can we relate dishes' popularity to the healthiness of their ingredients? Are there any world regions where the most popular recipes go hand in hand with a healthy diet?

-How do eating habits affect a population's health?

# Dataset

As explained above, we will both be using the Open Food Facts Dataset containing nutritional information about tens of thousands of supermarket products (primarly from France), as well as the Stanford cooking recipe dataset, linking recipes to home countries. The cooking recipe dataset will be used to detemine which types of ingredients and cooking styles are used in the cuisine of different countries. It consists of a set of HTML web pages we will have to scrap (BeautifulSoup) to retrieve information about the ingredients, quantities, cooking styles, calories, etc... In order to determine the "healthiness" of the recipes, we will need the data from the other dataset to get nutritional information about the recipe's ingredients. The open food fact dataset will be treated by parsing it knowing the delimeters are tabs and not commas, and we will add any missing nutritional information about common products with data scraps either from Google, or from specialized websites. We may also include statistics and datasets from the World Health Organization about mortality causes, diabetes to look at the health impact of the chosen diets.

# A list of internal milestones up until project milestone 2

For Nov 10th: Explore, clean and extract useful information of the dataset: Open food facts. In addition select a fixed number of countries in different socio-economic regions (to be chosen) where we have enough data available in this dataset to perform a meaningful analysis.

For Nov 17th: Select wanted recipes from these countries: Take the most popular recipes and create a json/csv with the extracted data: Name of country, ingredients, and quantities.

For Nov 25th: Merge extracted informations and precise with clarity the goal of the project, any details to be added to the research questions and the milestone 2 delivery. Scrap data from the web when necessary to complement the datasets missing info.

# Questions for TAa

Is our description of the project clear enough?
Any suggestions or possible additional work we could add to the project to make it more robust?
