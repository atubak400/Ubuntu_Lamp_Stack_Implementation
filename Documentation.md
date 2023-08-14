# **Ubuntu Lamp Stack Implementation on AWS**

## **What is a LAMP Stack**

A LAMP stack is a commonly used set of software components that together provide a platform for building and hosting dynamic websites and web applications. The name "LAMP" is an acronym for the four key components that make up the stack: Linux, Apache, MySQL, and PHP/Perl/Python (usually referred to as PHP).

## **Overview of each component of the LAMP Stack**

#### *Linux*
The operating system that serves as the foundation of the stack. It provides the environment for running the other components and managing hardware resources.

#### *Apache*
A popular open-source web server software that listens to incoming HTTP requests from clients (web browsers), processes those requests, and serves web content (HTML, CSS, JavaScript, etc.) back to the clients. It's responsible for handling the communication between the server and the client's browser.

#### *MySQL*
A widely used open-source relational database management system (RDBMS) that manages and stores structured data. MySQL is crucial for storing and retrieving data for web applications, making it possible to create dynamic websites that interact with databases.

#### *PHP/Perl/Python*
These are scripting languages used to develop dynamic web content and applications. In the context of the LAMP stack, PHP is the most common choice. PHP scripts are embedded within HTML and executed on the server side. They generate dynamic content that's sent to the client's browser as HTML, allowing for interactive and data-driven web applications.

## **Setting up  and Connecting to Ubuntu VM**
First, we log in to aws and create an ubuntu ec2 instance. We then connect to it using instance connect.

![Alt Text](./Images/1.png)
![Alt Text](./Images/2.png)
![Alt Text](./Images/3.png)
![Alt Text](./Images/4.png)


## Lists

Markdown supports both ordered and unordered lists:

### Unordered List

- Item 1
- Item 2
  - Sub-item A
  - Sub-item B
- Item 3

### Ordered List

1. First item
2. Second item
3. Third item
   1. Sub-item A
   2. Sub-item B

## Links

You can create links in Markdown:

- [Google](https://www.google.com)
- [OpenAI](https://www.openai.com)

## Images

You can embed images using the following syntax:


## Code

Inline code: `print("Hello, world!")`

Code block:

```python
def greet(name):
    print(f"Hello, {name}!")

greet("Alice")

