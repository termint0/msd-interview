# Occurrence Counter
This is a simple application that counts the number of occurrences of word pairs in a text file. It is written in Python and uses the Flask framework. The application can be run on the default file `data.txt`, a custom file sent via POST request, or a wikipedia article. The application is also dockerized.

# Getting started

To create a docker image, replace "IMAGE-NAME" with our name for the image and run the following command in the root directory of the project:
    
    docker build -t IMAGE-NAME .

To run the docker image, run the following command. Don't forget to replace "IMAGE-NAME" with the name you chose for the image:

    docker run -p 5000:5000 IMAGE-NAME


# Running

## Using the default file

To run the application on the default file (data.txt), send a GET request to the following URL. To change the default file, change the value of the `DEFAULT_FILE` variable in the `app.py` file:

    http://localhost:5000/occurrence_counter/default

## Using a custom file

The application can also be run on a custom file. To do so, send a POST request to the following URL, with the file in the body of the request. The file must be sent as a form-data file with the key `file`:

    http://localhost:5000/occurrence_counter/file

## Running the app on a wikipedia article

The application can also be run on a wikipedia article. To do so, send a GET request to the following URL, with the url of the article in the body of the request. The url must be sent as a form-data file with the key `url`. An example for the article on the [python programming language](https://en.wikipedia.org/wiki/Python_(programming_language)) is given below:

    http://localhost:5000/occurrence_counter/wiki&url=https://en.wikipedia.org/wiki/Python_(programming_language)