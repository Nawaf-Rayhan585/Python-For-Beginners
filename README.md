# Python Course with Projects

## Introduction

Welcome to this **Python Course**! This course is designed for beginners who want to learn Python from scratch. By the end of the course, you will have a solid understanding of Python and complete two hands-on projects to apply your knowledge.

## Table of Contents

1. Introduction to Python
2. Python Basics
3. Data Structures
4. Functions and Modules
5. Object-Oriented Programming
6. File Handling
7. Project 1: To-Do List Application
8. Project 2: Weather App

---

## 1. Introduction to Python

Python is a powerful, easy-to-learn programming language used in various fields such as web development, data science, and automation.

### Why Learn Python?

- Simple and easy syntax
- Versatile (Web, AI, Data Science, etc.)
- Large community support

---

## 2. Python Basics

### Installation

- Download and install Python from [python.org](https://www.python.org/)
- Use an IDE like VS Code, PyCharm, or Jupyter Notebook

### Hello World Program

```python
print("Hello, World!")
```

### Variables & Data Types

```python
name = "John"
age = 25
height = 5.9
is_student = True
```

### Input & Output

```python
name = input("Enter your name: ")
print("Hello,", name)
```

---

## 3. Data Structures

### Lists

```python
fruits = ["apple", "banana", "cherry"]
print(fruits[0])  # Output: apple
```

### Dictionaries

```python
person = {"name": "Alice", "age": 30}
print(person["name"])  # Output: Alice
```

### Tuples

```python
coordinates = (10, 20)
print(coordinates[0])  # Output: 10
```

### Sets

```python
unique_numbers = {1, 2, 3, 4, 4}
print(unique_numbers)  # Output: {1, 2, 3, 4}
```

---

## 4. Functions and Modules

### Defining Functions

```python
def greet(name):
    return "Hello, " + name

print(greet("Alice"))
```

### Importing Modules

```python
import math
print(math.sqrt(16))  # Output: 4.0
```

---

## 5. Object-Oriented Programming (OOP)

### Classes and Objects

```python
class Car:
    def __init__(self, brand, model):
        self.brand = brand
        self.model = model
    
    def show_info(self):
        return f"Car: {self.brand} {self.model}"

car1 = Car("Toyota", "Camry")
print(car1.show_info())
```

---

## 6. File Handling

### Reading a File

```python
with open("file.txt", "r") as file:
    content = file.read()
    print(content)
```

### Writing to a File

```python
with open("file.txt", "w") as file:
    file.write("Hello, Python!")
```

---

## 7. Project 1: To-Do List Application

### Description

A simple command-line to-do list where users can add, remove, and view tasks.

### Features

- Add tasks
- Remove tasks
- View tasks

### Code

```python
tasks = []

def add_task(task):
    tasks.append(task)
    print("Task added!")

def view_tasks():
    print("To-Do List:")
    for idx, task in enumerate(tasks, 1):
        print(f"{idx}. {task}")

def remove_task(index):
    if 0 <= index < len(tasks):
        tasks.pop(index)
        print("Task removed!")
    else:
        print("Invalid index!")

while True:
    choice = input("Choose: add/view/remove/exit: ")
    if choice == "add":
        add_task(input("Enter task: "))
    elif choice == "view":
        view_tasks()
    elif choice == "remove":
        remove_task(int(input("Enter task number: ")) - 1)
    elif choice == "exit":
        break
    else:
        print("Invalid choice!")
```

---

## 8. Project 2: Weather App

### Description

A simple CLI-based weather app that fetches weather data using an API.

### Features

- Fetch current weather by city
- Display temperature, humidity, and description

### Prerequisites

- Install `requests` library

```sh
pip install requests
```

- Get an API key from [OpenWeatherMap](https://openweathermap.org/api)

### Code

```python
import requests

def get_weather(city):
    api_key = "your_api_key_here"
    url = f"http://api.openweathermap.org/data/2.5/weather?q={city}&appid={api_key}&units=metric"
    response = requests.get(url)
    data = response.json()
    if data["cod"] != "404":
        weather = data["main"]
        temp = weather["temp"]
        humidity = weather["humidity"]
        desc = data["weather"][0]["description"]
        print(f"Temperature: {temp}°C")
        print(f"Humidity: {humidity}%")
        print(f"Description: {desc}")
    else:
        print("City not found!")

city = input("Enter city name: ")
get_weather(city)
```

---

## Conclusion

Congratulations! 🎉 You have completed the Python course and built two real-world projects. Keep practicing and explore more advanced topics like web development, data science, and machine learning.

Happy Coding! 🚀

