# AirBnB Clone - The Console (Version 3)

Welcome to the third iteration of the AirBnB Clone project, focusing on refining and enhancing our console application. This segment is a part of the comprehensive AirBnB project at ALX SE, aimed at imparting essential concepts of higher-level programming.

## Introduction

The console serves as the foundational element of the AirBnB project. It functions as a command interpreter facilitating the management of various objects crucial for the AirBnB (HBnB) website.

#### Key Functionalities:
- Creation of new objects (e.g., User, Place)
- Retrieval of objects from different sources (files, databases, etc.)
- Operations on objects (counting, computing stats, etc.)
- Updating attributes of objects
- Deletion of objects

## Table of Contents
* [Environment](#environment)
* [Installation](#installation)
* [File Descriptions](#file-descriptions)
* [Usage](#usage)
* [Examples of Use](#examples-of-use)
* [Bugs](#bugs)
* [Authors](#authors)
* [License](#license)

## Environment
This project is interpreted and tested on Ubuntu 14.04 LTS using Python 3 (version 3.4.3).

## Installation
* Clone this repository: `git clone "https://github.com/alexaorrico/AirBnB_clone.git"`
* Access the AirBnb directory: `cd AirBnB_clone`
* Run the console interactively: `./console` and enter commands
* Run the console non-interactively: `echo "<command>" | ./console.py`

## File Descriptions
### Console
[console.py](console.py) - The console serves as the entry point of the command interpreter. 
List of supported commands in the console:
* `EOF` - Exits console 
* `quit` - Exits console
* `<emptyline>` - Overwrites default empty line method and does nothing
* `create` - Creates a new instance of `BaseModel`, saves it (to the JSON file), and prints the ID
* `destroy` - Deletes an instance based on the class name and ID (saves the change into the JSON file) 
* `show` - Prints the string representation of an instance based on the class name and ID
* `all` - Prints string representations of all instances based or not on the class name
* `update` - Updates an instance based on the class name and ID by adding or updating an attribute (saves the change into the JSON file)

### Models
The `models/` directory contains classes used for this project:
- [base_model.py](/models/base_model.py) - The BaseModel class serves as the foundation for future classes
  * `__init__(self, *args, **kwargs)` - Initialization of the base model
  * `__str__(self)` - String representation of the BaseModel class
  * `save(self)` - Updates the attribute `updated_at` with the current datetime
  * `to_dict(self)` - Returns a dictionary containing all keys/values of the instance

Classes inherited from Base Model:
- [amenity.py](/models/amenity.py)
- [city.py](/models/city.py)
- [place.py](/models/place.py)
- [review.py](/models/review.py)
- [state.py](/models/state.py)
- [user.py](/models/user.py)

### Engine
The `models/engine` directory contains the File Storage class that handles JSON serialization and deserialization:
- [file_storage.py](/models/engine/file_storage.py) - Serializes instances to a JSON file & deserializes back to instances
  * `all(self)` - Returns the dictionary `__objects`
  * `new(self, obj)` - Sets in `__objects` the obj with key `<obj class name>.id`
  * `save(self)` - Serializes `__objects` to the JSON file (path: `__file_path`)
  * `reload(self)` - Deserializes the JSON file to `__objects`

### Tests
The `tests/` directory contains all unit test cases for this project:

Each test file follows a similar pattern:
- Test class for the respective model documentations
- PEP8 conformance tests
- Documentation tests

## Usage
```
vagrantAirBnB_clone$./console.py
(hbnb) help

Documented commands (type help <topic>):
========================================
EOF  all  create  destroy  help  quit  show  update

(hbnb) all MyModel
** class doesn't exist **
(hbnb) create BaseModel
7da56403-cc45-4f1c-ad32-bfafeb2bb050
(hbnb) all BaseModel
[[BaseModel] (7da56403-cc45-4f1c-ad32-bfafeb2bb050) {'updated_at': datetime.datetime(2017, 9, 28, 9, 50, 46, 772167), 'id': '7da56403-cc45-4f1c-ad32-bfafeb2bb050', 'created_at': datetime.datetime(2017, 9, 28, 9, 50, 46, 772123)}]
(hbnb) show BaseModel 7da56403-cc45-4f1c-ad32-bfafeb2bb050
[BaseModel] (7da56403-cc45-4f1c-ad32-bfafeb2bb050) {'updated_at': datetime.datetime(2017, 9, 28, 9, 50, 46, 772167), 'id': '7da56403-cc45-4f1c-ad32-bfafeb2bb050', 'created_at': datetime.datetime(2017, 9, 28, 9, 50, 46, 772123)}
(hbnb) destroy BaseModel 7da56403-cc45-4f1c-ad32-bfafeb2bb050
(hbnb) show BaseModel 7da56403-cc45-4f1c-ad32-bfafeb2bb050
** no instance found **
(hbnb) quit
```

## Bugs
No known bugs at this time. 

## Authors
- Abdelhamid Maaira - [GitHub](https://github.com/Hmddev23) / [Twitter](https://twitter.com/AbdelhamidMa23)
- Mohamed Amyne Boutallaght - [GitHub](https://github.com/Yamix27) / [Twitter](#)

## License
Public Domain. No copyright protection.
