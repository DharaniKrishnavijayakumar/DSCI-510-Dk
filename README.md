Hello All !!!!!
Before starting with this project please take time to read the Project Proposal and Project Report file which is present in the results directory. By doing this you will get a feel of the project and I feel it will be easiy to understand how each and everything works here.

*****Important Note******: I have submitted the processed file also in the data directory. When your testing my code feel free to delete all files inside the data->processed folder except: data/processed/Latitude and Longitude.csv ( file name: Latitude and Longitude.csv) do not delete this file alone it is a already extracted clean data set from Google map website. There will be 2 files present in the data->raw folder makesure you delete this file before running the code:data/raw/RAW_Weather_API_Data_Set.csv (file name:RAW_Weather_API_Data_Set.csv) after deleting this you will be left with only 1 file in data->raw folder with name:data/raw/RAW_Tourism_Dataset.csv (file name:RAW_Tourism_Dataset.csv) this file do not delete it is a RAW tourism file which is being extracted from kaggle.
******Reason for this important note*****: I tried creating a folder in git hub to store all my processed data but git did not allow me to create a new folder (to shocase the expected output). So, had to insert my output files in the respective folders. But feel free to delete as mentioned above and start running the code.

Other than this delete all the files present inside the folder of data->processed path. After this follow the steps below so that you will be able to get the required processed files one by one as script run's.
***If you want to skip these steps which has detailed explanation and directly want to just test my code please go to bottom on this text you will find flow follow that and you will get results as expected***

Save the project as a whole package in your local machine using terminal command:
Git clone (git hub repo url)

Note: I will be using the path of the file's needed to be used in case your looking for name of the file it is usually present in the last after "/" and in our project mostly all files end with.csv extension , .py, .ipynb and .html.
So, don't get confused just follow the path of the file you will be good to go.

Step-1:

First things First. Before touching any directory makesure you download all the requirements (like libraries). So, to make it easier for you I have uploaded a file named 
requirements.txt file in the home directory of the repo which contains all the required libraries I used for this project.
So, as first step maksure you download the requirements.txt file to your local machine and then open your terminal in your local machine and use the command:
pip install -r requirements.txt.
As you give this command please wait for a while it will download all the necessary libraries to your machine and once the process is done you will get a message.

Step-2:

After step 1 is done we can dive into the problem statement (actual coding!!!!) Now our project is structured into 4 different sections.
I. Tourism 
II. Weather 
III. Analysis 
IV. Visualization

So, firstly we will be dealing with Tourism_dataset. Over here we will be wokring on a CSV file which was extracted from Kaggle. The RAW dataset is available in data directory inside raw folder with path: data/raw/RAW_Tourism_Dataset.csv
In the first place we will be cleaning this data and produce clean dataset for tourism and save it in path: data/processed/Clean_Tourist_Dataset.csv. So, to perform cleaning of this data set please run this script present in the path:src/Clean_Tourism.py . Once this script is run the clean dataset will be available in the path mentioned above. (Reminder: Make sure to follow the ***important note*** above before running and generating the files)

Step-3:

Next, is the crucial step we will be performing pre-processing using the cleaned dataset of tourism which is saved in the path: data/processed/Clean_Tourist_Dataset.csv. By,performing this step we will be able again insight about the dataset like what are the unique destination list and which all months people visit these destinations. To perfrom this please run the script present in the path:src/Processed_Tourism_Dataset.py. Once this script is ran we can expect a detailed .txt file with various info regarding the dataset in the path:data/processed/Pre-Processing.txt.

Step-4:

Creating Empty File:
This is an exicting step where we will deviate from the regular data collection process and use API for data collection. Yes, this step helps us to get weather dataset for different destination in specific month using API from the OpenWeatherMap.org website. To perfom this step please run the py script file present in the path:src/Empty_Weather_csv_file_creation.py. This script creates an empty csv type file called RAW_Weather_API_Data_Set.csv in the path: data/raw/RAW_Weather_API_Data_Set.csv.
Make sure to review the data/raw/RAW_Weather_API_Data_Set.csv file whether it is empty and has the necessary weather parameters in the name's of the column.

Create an Account ot use my API Key:

Next create an student account in the website of openweathermap.org (link:https://openweathermap.org/appid). After this you will recieve an secure mail with your API KEY in this case I have the key already entered in the scrip (get_weather_dataset.py) just replace the key with your's or you can use my Key itself (My API KEY:'6f2aec8845d47a5f2d30365f6482bf7a'). If you are using my API key do not make chages to scrip for ease of running the code I have already entered my API Key. Next, subscribe the historic dataset and read doc for that API. But you no need to write a code after reading the doc because I have already written the scrip using python and request library. Just for educational purpose you can see.

Getting data from API:

Once the empty file is created start running the script file present in the path:src/get_data_Weather.py. This script has list of destination's, months and coordinates of the destination's. The coordinates of the destinations are feed as a csv file from the path: data/processed/Latitude and Longitude.csv.
After this script is completed we can find the raw weather dataset csv file being saved in the location:data/raw/RAW_Weather_API_Data_Set.csv. Bascially the data obtained from API are in the form of json but to make the analysis easier and unifrom the script will convert json into csv and save it as a csv file itsel.
This step is little slow please wait until you receive a print statement as: Data appended to data/raw/RAW_Weather_API_Data_Set.csv. After you receive this statement go raw folder and check whether the dataset is saved.
***Note:*** When getting data from API we can notice slight fluctation in the dataset it's because weather data are usually updated and refined constantly by the metroical stations for the quality of data to be maintained and also there might be few floating point changes. As far as I knew there was very minute change's like 0.01 - 0.2 which is barely visible. I can assure you due to these chnages the ***Analysis or the Visualization*** part will not be different from what I got. I have tested it more than 2 time's and I got the same result's every time I run.

Cleaning RAW_Weather_Dataset:

Once the data/raw/RAW_Weather_API_Data_Set.csv. produced we have to run the script file:src/Clean_data_Weather.py and once this is done we will get the cleaned dataset for the weather data in the location:data/processed/Clean_Weather_API_Dataset.csv.

This step helps us to get the dataset from API and store it in a csv file and then the stored raw data is cleaned and saved.
Note: We do not need to extract latitude and longitude dataset using script it is already available in a csv format from reliable source and it issaved in the location:data/processed/Latitude and Longitude.csv so please just use it.
The API KEY is: '6f2aec8845d47a5f2d30365f6482bf7a'

Step-5: 

Merging 3 dataset's together:

This step is a crucial part to perform robust data analysis. If you have followed the above steps properly only we can go ahead with this step.
We will be working with clean dataset files which will be saved in the data directory inside the processed folder.
We, are going to merge 3 dataset's:
i. data/processed/Clean_Tourist_Dataset.csv - clean_tourism dataset
ii.data/processed/Clean_Weather_API_Dataset.csv - clean_weather dataset
iii.data/processed/Latitude and Longitude.csv - Latitude and Longitude dataset (coordinate dataset)

We are going to merge these 3 datset into a single datset and save it as a csv file in the path and with name as:data/processed/Tourism_Weather_Merged.csv.

To perfrom this operation we have to run a small script which takes in the inputs as 3 files to be merged and returns a merged dataset. So, these 3 files / dataset's are 
merged using common columns over here we  use Destination and Month as common columns.
After the scrip is completed the file is saved in the location:data/processed/Tourism_Weather_Merged.csv

Note: Please take a look at the merged dataset so that it will be easier to understand what columns we use present in the dataset.

Step-6:

Perfrom Analysis:
The data set which we extracted, cleaned, merged is in a great structure where we can use this carefully crafted datset to perform various analysis which gives us insights about the tourism vs weather trends for various 40 different location's around the world.
So, to perform analysis we use the script:src/run_Analysis.py with dataset path:data/processed/Tourism_Weather_Merged.csv. By running this we will be able to see 10 different analysis and result's.

To run as a notebook:
To access the notebook to perfrom analysis I have submitted an .ipynb file in the location:results/Analysis_Final.ipynb. Please use google colab and also include the datset:data/processed/Tourism_Weather_Merged.csv.

Step-7:

Perfrom Visualizations:
This is the most interesting part where we get various interactive charts, maps, and heat-map and so on. This the Visualization part where we use the dataset: data/processed/Tourism_Weather_Merged.csv to perfrom visualization using a py script in the path:src/Visualize_results.py. Once this script is ran we will be able to witness 7 different types of visualiztions beeing performed !!!
I have provided a .ipynb file which displays the interactive charts and easiy to use. It is saved in the path: results/Visuailization_Final.ipynb and as told above don't forget to upload the dataset file:data/processed/Tourism_Weather_Merged.csv before performing visualization.

We will be able to see every results in a display screen except the 6th visualization which is saved in the path:results/Spatial analysis and exploration of data associated with specific locations.html (results folder). So, this is an interesting piece of visualization where we can hoover around the world map and see various weather parameters like temperature, humidity, windspeed for each month of 2023 for various destinations.
Feel free to zoom in and zoom out to see detalis of the destination.

And, there are other graphs and charts which are also interactive in nature try hoovering and clicking in the lines to see details. I recommend using google colab: https://colab.google to perfrom visualization to see the full potential of it.

***Flow:***
If you want to skip these paragraphs and directly want to test my code in action follow this:

1st->run this script:src/Clean_Tourism.py

2nd->run this script:src/Processed_Tourism_Dataset.py

3rd->run this script:src/Empty_Weather_csv_file_creation.py

4th->run this script:src/get_data_Weather.py (have to use API KEY. I have already generated an API KEY: '6f2aec8845d47a5f2d30365f6482bf7a' you can use this to test if you do not want to create an account. I have already entered my API Key in the script so need to change just run the script)

5th->run this script:src/Clean_data_Weather.py

6th->run this script:src/Merging_Tourism_Weather_Latitude _and_Longitude_dataset.py

-------**After 6th step please CHECK THE data->processed folder to see all necessary files being created using scripts which you have run(TOTALLY:6 files should be there)**-----------------------------------------------------------------------------------------------

7th->run this script:src/run_Analysis.py

8th->run this script:src/Visualize_results.py

9th->For interactive Visualization:

Run this .ipynb script in you google colab (https://colab.google) with this dataset:data/processed/Tourism_Weather_Merged.csv
Notebook file:results/Visuailization_Finalipynb.ipynb

By, running this Notebook you can see interactive models beeing generated and you can hover and see changes in the real time.

Note:
After you run all these scripts by following these steps you can seamlessly run the work and get the desired output. 
For intial refernce I have uploaded all my files inside each directiory feel free to delete those and try re-running the scripts to view the output's being generated dynamically as you run scripts!!!!


***Please feel free to reach out to me if there is any difficulties in running the code. You can contact me through my email: dbalasub@usc.edu.***
Thank You!!!!!





