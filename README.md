# Data Analysis

## Note
### Download this CSV File then put into main destination with program for it to function.
http://bit.ly/Cars_file

# First 5 and Last 5 Cars
- This program creates a database that stores information of a csv file using `pd.read_csv()`. After reading and storing the information, it finds the first 5 information using `.head()` and the last 5 using `.tail()`. The results are then printed out.

# Models, Cylinders, and Gears
### All the functions below are contained into one program that will display all of these.

## Display the first five rows with odd-numbered columns (columns 1, 3, 5, 7...) of cars.
- This program creates a database which reads the csv file. The database is then read and using the function `.iloc[]` selects and access the data using an integer based index. Since Python uses a 0-based index, the value in the function was set to `.iloc[1::2]` with `::2` telling to slice 2 to get a odd numbder of columns, which is then printed out as a result.
  
## Display the row that contains the ‘Model’ of ‘Mazda RX4’
- This program reads database then aims to locate the Model for Mazda RX4. This is done using `cavfile[cavfile['Model'] == 'Mazda RX4']`, which will go through the file and using the given parameters will find a match within the given parameters within the given label, in this instance, `Model`. The result then is all the information for Mazda RX4.

## How many cylinders (‘cyl’) does the car model ‘Camaro Z28’ have?
- This program reads the database that is then made to find the amount of cylinders for a car model. This is done using `.loc[]` which uses a label type indexing, in this case `cavfile.loc[cavfile['Model'] == 'Camaro Z28', 'cyl'].values[0]`. This works by first looking into the column that contains `Camaro Z28`, then it goes into the `cyl` where it outputs the value given in `cyl`. Since the program could not output non-string results, `.values[0]` was added to properly display the value. The results were then printed to show the amount of cylinders the car model Camaro Z28.

## Determine how many cylinders (‘cyl’) and what gear type (‘gear’) do the car models ‘Mazda RX4 Wag’, ‘Ford Pantera L’ and ‘Honda Civic’ have.
- This program reads the database that is then made to find the characteristics of certain car models. Firstly, the models was needed to be declared so that the system knows what to find, this is done by declaring them in a way `models = ['Mazda RX4 Wag', 'Ford Pantera L', 'Honda Civic']` which the variable `models` is put into a searching function using `cars = cavfile[cavfile['Model'].isin(models)]`. Using `.isin()` uses the variable `models` to find multiple columns containing those in the list. After that, locate and print out the `cyl` and `gear` for each model. Locating the `cyl` and `gear` was done using `cars[['Model', 'cyl', 'gear']]` where `cars` was taken from the function before that and is used to locate for `cyl` and `gear`. The results are then printed out, and displayed the amount of cylinders and gear type for the car models.
