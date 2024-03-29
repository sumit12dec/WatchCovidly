# WatchCovidly

Track the home quarantine people in 500 meter radius from the given location.


![](quarantine_heatmap.png)


## Basic setup
  * Make a virtual environment,clone the repository and install the requirements.

  ```
  $ pip install -r requirements.txt
  ```
 * Add the *DB_STRING, GOOGLE_API_KEY, GOOGLE_MAP_URL, FILE_PATH*.
 
## Save the data from xls to database.
  ![](banglore_xls.png)
  
  * Convert *Bengaluru.xlsx* to json and save in the different file as in *bangaluru_quarantined.json* file.
  * Run the script inside the *save_data.py* file.
  * All the json data will be formatted and will be saved in the given collection.
  * Run the server.    
     
  ```
  $ python manage.py runserver
  ```
  * Open web browser and goto [localhost](http://127.0.0.1:8000/).
  * Search the location to see the quarantine people around that location, by
    default heatmap will show the data based on current location of the user. 

## How to use API?
  * To fetch the nearby quarantine users location, use the below endpoint with the *lat, lng* and *radius*.
  
  #### URL
  [https://corona-cases-info.herokuapp.com/api/nearby-quarantined/?lat=12.9145978&lng=77.6653456&radius=500](https://corona-cases-info.herokuapp.com/api/nearby-quarantined/?lat=12.9145978&lng=77.6653456&radius=500)
  
  #### Response (JSON) 
  ```json
 
   {
   "nearby_users":[
      [
         12.9191337,
         77.6651330
     ],
      [
         12.9189321,
         77.6649726
      ],
      [
         12.9191337,
         77.6628913
      ],
      [
         12.9199188,
         77.6683208
      ]
      .....
   ]
}
  
  
  
  
