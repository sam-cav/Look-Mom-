<center>
    <img src="https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-PY0101EN-SkillsNetwork/IDSNlogo.png" width="300" alt="cognitiveclass.ai logo"  />
</center>

# Reading Files Python

Estimated time needed: **40** minutes

## Objectives

After completing this lab you will be able to:

*   Read text files using Python libraries


<h2>Table of Contents</h2>
<div class="alert alert-block alert-info" style="margin-top: 20px">
    <ul>
        <li><a href="https://download/?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkPY0101ENSkillsNetwork19487395-2021-01-01">Download Data</a></li>
        <li><a href="https://read/?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkPY0101ENSkillsNetwork19487395-2021-01-01">Reading Text Files</a></li>
        <li><a href="https://better/?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkPY0101ENSkillsNetwork19487395-2021-01-01">A Better Way to Open a File</a></li>
    </ul>

</div>

<hr>


<h2 id="download">Download Data</h2>



```python
import urllib.request
url = 'https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-PY0101EN-SkillsNetwork/labs/Module%204/data/example1.txt'
filename = 'Example1.txt'
urllib.request.urlretrieve(url, filename)
```




    ('Example1.txt', <http.client.HTTPMessage at 0x7ff784103828>)




```python
# Download Example file


!wget -O /resources/data/Example1.txt https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-PY0101EN-SkillsNetwork/labs/Module%204/data/example1.txt
```

    /resources/data/Example1.txt: No such file or directory


<hr>


<h2 id="read">Reading Text Files</h2>


One way to read or write a file in Python is to use the built-in <code>open</code> function. The <code>open</code> function provides a **File object** that contains the methods and attributes you need in order to read, save, and manipulate the file. In this notebook, we will only cover **.txt** files. The first parameter you need is the file path and the file name. An example is shown as follow:


<img src="https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-PY0101EN-SkillsNetwork/labs/Module%204/images/ReadOpen.png" width="500" />


The mode argument is optional and the default value is **r**. In this notebook we only cover two modes:

<ul>
    <li>**r**: Read mode for reading files </li>
    <li>**w**: Write mode for writing files</li>
</ul>


For the next example, we will use the text file **Example1.txt**. The file is shown as follows:


<img src="https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-PY0101EN-SkillsNetwork/labs/Module%204/images/ReadFile.png" width="100" />


We read the file:



```python
# Read the Example1.txt

example1 = "Example1.txt"
file1 = open(example1, "r")
```

We can view the attributes of the file.


The name of the file:



```python
# Print the path of file

file1.name
```




    'Example1.txt'



The mode the file object is in:



```python
# Print the mode of file, either 'r' or 'w'

file1.mode
```




    'r'



We can read the file and assign it to a variable :



```python
# Read the file

FileContent = file1.read()
FileContent
```




    'This is line 1 \nThis is line 2\nThis is line 3'



The **/n** means that there is a new line.


We can print the file:



```python
# Print the file with '\n' as a new line

print(FileContent)
```

    This is line 1 
    This is line 2
    This is line 3


The file is of type string:



```python
# Type of file content

type(FileContent)
```




    str



It is very important that the file is closed in the end. This frees up resources and ensures consistency across different python versions.



```python
# Close file after finish

file1.close()
```

<hr>


<h2 id="better">A Better Way to Open a File</h2>


Using the <code>with</code> statement is better practice, it automatically closes the file even if the code encounters an exception. The code will run everything in the indent block then close the file object.



```python
# Open file using with

with open(example1, "r") as file1:
    FileContent = file1.read()
    print(FileContent)
```

    This is line 1 
    This is line 2
    This is line 3


The file object is closed, you can verify it by running the following cell:



```python
# Verify if the file is closed

file1.closed
```

We can see the info in the file:



```python
# See the content of file

print(FileContent)
```

    This is line 1 
    This is line 2
    This is line 3


The syntax is a little confusing as the file object is after the <code>as</code> statement. We also don’t explicitly close the file. Therefore we summarize the steps in a figure:


<img src="https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-PY0101EN-SkillsNetwork/labs/Module%204/images/ReadWith.png" width="500" />


We don’t have to read the entire file, for example, we can read the first 4 characters by entering three as a parameter to the method **.read()**:



```python
# Read first four characters

with open(example1, "r") as file1:
    print(file1.read(4))
```

    This


Once the method <code>.read(4)</code> is called the first 4 characters are called. If we call the method again, the next 4 characters are called. The output for the following cell will demonstrate the process for different inputs to the method <code>read()</code>:



```python
# Read certain amount of characters

with open(example1, "r") as file1:
    print(file1.read(4))
    print(file1.read(4))
    print(file1.read(7))
    print(file1.read(15))
```

    This
     is 
    line 1 
    
    This is line 2


The process is illustrated in the below figure, and each color represents the part of the file read after the method <code>read()</code> is called:


<img src="https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-PY0101EN-SkillsNetwork/labs/Module%204/images/read.png" width="500" />


Here is an example using the same file, but instead we read 16, 5, and then 9 characters at a time:



```python
# Read certain amount of characters

with open(example1, "r") as file1:
    print(file1.read(16))
    print(file1.read(5))
    print(file1.read(9))
```

    This is line 1 
    
    This 
    is line 2


We can also read one line of the file at a time using the method <code>readline()</code>:



```python
# Read one line

with open(example1, "r") as file1:
    print("first line: " + file1.readline())
```

    first line: This is line 1 
    


We can also pass an argument to <code> readline() </code> to specify the number of charecters we want to read. However, unlike <code> read()</code>, <code> readline()</code> can only read one line at most.



```python
with open(example1, "r") as file1:
    print(file1.readline(20)) # does not read past the end of line
    print(file1.read(20)) # Returns the next 20 chars

```

    This is line 1 
    
    This is line 2
    This 


We can use a loop to iterate through each line:



```python
# Iterate through the lines

with open(example1,"r") as file1:
        i = 0;
        for line in file1:
            print("Iteration", str(i), ": ", line)
            i = i + 1
```

    Iteration 0 :  This is line 1 
    
    Iteration 1 :  This is line 2
    
    Iteration 2 :  This is line 3


We can use the method <code>readlines()</code> to save the text file to a list:



```python
# Read all lines and save as a list

with open(example1, "r") as file1:
    FileasList = file1.readlines()
```

Each element of the list corresponds to a line of text:



```python
# Print the first line

FileasList[0]
```

# Print the second line

FileasList\[1]



```python
# Print the third line

FileasList[2]
```

<hr>
<h2>The last exercise!</h2>
<p>Congratulations, you have completed your first lesson and hands-on lab in Python. However, there is one more thing you need to do. The Data Science community encourages sharing work. The best way to share and showcase your work is to share it on GitHub. By sharing your notebook on GitHub you are not only building your reputation with fellow data scientists, but you can also show it off when applying for a job. Even though this was your first piece of work, it is never too early to start building good habits. So, please read and follow <a href="https://cognitiveclass.ai/blog/data-scientists-stand-out-by-sharing-your-notebooks/?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkPY0101ENSkillsNetwork19487395-2021-01-01" target="_blank">this article</a> to learn how to share your work.
<hr>


## Author

<a href="https://www.linkedin.com/in/joseph-s-50398b136/?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkPY0101ENSkillsNetwork19487395-2021-01-01" target="_blank">Joseph Santarcangelo</a>

## Other contributors

<a href="https://www.linkedin.com/in/jiahui-mavis-zhou-a4537814a?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkPY0101ENSkillsNetwork19487395-2021-01-01">Mavis Zhou</a>

## Change Log

| Date (YYYY-MM-DD) | Version | Changed By    | Change Description                                        |
| ----------------- | ------- | ------------- | --------------------------------------------------------- |
| 2020-09-30        | 1.3     | Malika        | Deleted exericse "Weather Data"                           |
| 2020-09-30        | 1.2     | Malika Singla | Weather Data dataset link added                           |
| 2020-09-30        | 1.1     | Arjun Swani   | Added exericse "Weather Data"                             |
| 2020-09-30        | 1.0     | Arjun Swani   | Added blurbs about closing files and read() vs readline() |
| 2020-08-26        | 0.2     | Lavanya       | Moved lab to course repo in GitLab                        |
|                   |         |               |                                                           |
|                   |         |               |                                                           |

<hr/>

## <h3 align="center"> © IBM Corporation 2020. All rights reserved. <h3/>

