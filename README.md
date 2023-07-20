This is the GitHub repository for my submission for the July 2023 Challenge Statement of the AngelHack Monthly Code Challenge.

All visualization and insight derivation with explanation are include in the Jupyter notebook [file](./pokemon.ipynb)

The extended automatically generated report is also [included](./pokemonreports.html)

The dataset used is the same dataset that was linked to the challege and is also in this repository [data](./pokemon.csv)

Code written and submitted by [EngineerLambda]"(www.twitter.com/abdulsomad_me")

## Storytelling
The dataset used for this analytics project was obtained from [kaggle]() through the Angelhack challenge page
The dataset contains information about 1194 unique pokemons
The dataset had 12 columns initially, and was reduced to 11 for ease of ananlysis. The data has 542 NaN (Not a Number) values in the `Type2` column, which were all replaced with the `Not Available` tag after due considerations of what the column means.

### About the visualizations
1. The first visualization made was used to display 30 pokemons sampled from the first 30 instances of the dataset, using the Image url column.
How? I created a function that uses python `requests` library to get the data from the image urls, I then proceeded to read the data as bytedata and then opened it with the python's `Pillow` library. The created function is then passed into the `imshow` method in the `Pyplot` class of the `Matplotlib` library

2. The second visualization displayed the counts of pokemon with one type only as compared to the whole dataset, and it happens to be that, the number of empty values in the dataset (i.e `Type2` column) is a determiner of the number of pokemons with only one type, that only means, the rows are empty because there is no second type for some of the pokemons

3. Thirdly, I made use of the seaborn library to show the distribution of the `Type1` column, with a beautifully anotated histogram plot, the anotations were made present to show the number of instances of each pokemon type in the column

4. The same visualization was done for the `Type2` column

5. The fifth visualization worked to show the distribution of the two columns (Type1 and Type2) combined. It was noticed from the previous visualizations (3 and 4), that there are similar pokemon types in the two columns, therfore, I wanted to combine the two columns, then took the count of the number of instances of each pokemon type using the `Counter` class from the `collections` module, and then made a beautiful visualization with pyplot's bar method to make a bar plot, with anotations, of course. It was discovered there that there are 18 valid types (without the `Not Available` tag)

6. I then looked into the other numerical columns which contains the battle stats of each pokemon, then got the average total for each pokemon type, considering repetitions, and then plotted a barplot using `seaborn` to show the average total with respect to the pokemon type name, with anotations, as usual, using the Type1 column.

7. Same visualization was done for the Type2 column

Finally, I generated an auto visualization using the ydata_profiling library (previously pandas_profiling), and then deployed on firebase for access to the visualization since I exported the report as an html file.
