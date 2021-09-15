<center>
    <img src="https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-PY0101EN-SkillsNetwork/IDSNlogo.png" width="300" alt="cognitiveclass.ai logo"  />
</center>

# Dictionaries in Python

Estimated time needed: **25** minutes

## Objectives

After completing this lab you will be able to:

*   Work with and perform operations on dictionaries in Python


<h2>Table of Contents</h2>
<div class="alert alert-block alert-info" style="margin-top: 20px">
    <ul>
        <li>
            <a href="https://#dic">Dictionaries</a>
            <ul>
                <li><a href="https://content/?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkPY0101ENSkillsNetwork19487395-2021-01-01">What are Dictionaries?</a></li>
                <li><a href="https://key/?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkPY0101ENSkillsNetwork19487395-2021-01-01">Keys</a></li>
            </ul>
        </li>
        <li>
            <a href="https://#quiz">Quiz on Dictionaries</a>
        </li>
    </ul>

</div>

<hr>


<h2 id="Dic">Dictionaries</h2>


<h3 id="content">What are Dictionaries?</h3>


A dictionary consists of keys and values. It is helpful to compare a dictionary to a list. Instead of being indexed numerically like a list, dictionaries have keys. These keys are the keys that are used to access values within a dictionary.


<img src="https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-PY0101EN-SkillsNetwork/labs/Module%202/images/DictsList.png" width="650" />


An example of a Dictionary <code>Dict</code>:



```python
# Create the dictionary

Dict = {"key1": 1, "key2": "2", "key3": [3, 3, 3], "key4": (4, 4, 4), ('key5'): 5, (0, 1): 6}
Dict
```




    {'key1': 1,
     'key2': '2',
     'key3': [3, 3, 3],
     'key4': (4, 4, 4),
     'key5': 5,
     (0, 1): 6}



The keys can be strings:



```python
# Access to the value by the key

Dict["key1"]
```




    1



Keys can also be any immutable object such as a tuple:



```python
# Access to the value by the key

Dict[(0, 1)]
```

Each key is separated from its value by a colon "<code>:</code>".  Commas separate the items, and the whole dictionary is enclosed in curly braces. An empty dictionary without any items is written with just two curly braces, like this  "<code>{}</code>".



```python
# Create a sample dictionary

release_year_dict = {"Thriller": "1982", "Back in Black": "1980", \
                    "The Dark Side of the Moon": "1973", "The Bodyguard": "1992", \
                    "Bat Out of Hell": "1977", "Their Greatest Hits (1971-1975)": "1976", \
                    "Saturday Night Fever": "1977", "Rumours": "1977"}
release_year_dict
```

In summary, like a list, a dictionary holds a sequence of elements. Each element is represented by a key and its corresponding value. Dictionaries are created with two curly braces containing keys and values separated by a colon. For every key, there can only be one single value, however,  multiple keys can hold the same value. Keys can only be strings, numbers, or tuples, but values can be any data type.


It is helpful to visualize the dictionary as a table, as in the following image. The first column represents the keys, the second column represents the values.


<img src="https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-PY0101EN-SkillsNetwork/labs/Module%202/images/DictsStructure.png" width="650" />


<h3 id="key">Keys</h3>


You can retrieve the values based on the names:



```python
# Get value by keys

release_year_dict['Thriller'] 
```

This corresponds to:


<img src="https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-PY0101EN-SkillsNetwork/labs/Module%202/images/DictsKeyOne.png" width="500" />


Similarly for <b>The Bodyguard</b>



```python
# Get value by key

release_year_dict['The Bodyguard'] 
```

<img src="https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-PY0101EN-SkillsNetwork/labs/Module%202/images/DictsKeyTwo.png" width="500" />


Now let us retrieve the keys of the dictionary using the method <code>keys()</code>:



```python
# Get all the keys in dictionary

release_year_dict.keys() 
```

You can retrieve the values using the method  <code>values()</code>:



```python
# Get all the values in dictionary

release_year_dict.values() 
```

We can add an entry:



```python
# Append value with key into dictionary

release_year_dict['Graduation'] = '2007'
release_year_dict
```

We can delete an entry:



```python
# Delete entries by key

del(release_year_dict['Thriller'])
del(release_year_dict['Graduation'])
release_year_dict
```

We can verify if an element is in the dictionary:



```python
# Verify the key is in the dictionary

'The Bodyguard' in release_year_dict
```

<hr>


<h2 id="quiz">Quiz on Dictionaries</h2>


<b>You will need this dictionary for the next two questions:</b>



```python
# Question sample dictionary

soundtrack_dic = {"The Bodyguard":"1992", "Saturday Night Fever":"1977"}
soundtrack_dic 
```

a) In the dictionary <code>soundtrack_dic</code> what are the keys ?



```python
# Write your code below and press Shift+Enter to execute
soundtrack_dic = {"The Bodyguard":"1992", "Saturday Night Fever":"1977"}
soundtrack_dic.keys()
```




    dict_keys(['The Bodyguard', 'Saturday Night Fever'])



<details><summary>Click here for the solution</summary>

```python
soundtrack_dic.keys() # The Keys "The Bodyguard" and "Saturday Night Fever" 

```

</details>


b) In the dictionary <code>soundtrack_dic</code> what are the values ?



```python
# Write your code below and press Shift+Enter to e
soundtrack_dic.values()

```




    dict_values(['1992', '1977'])



<details><summary>Click here for the solution</summary>

```python
soundtrack_dic.values() # The values are "1992" and "1977"

```

</details>


<hr>


<b>You will need this dictionary for the following questions:</b>


The Albums <b>Back in Black</b>, <b>The Bodyguard</b> and <b>Thriller</b> have the following music recording sales in millions 50, 50 and 65 respectively:


a) Create a dictionary <code>album_sales_dict</code> where the keys are the album name and the sales in millions are the values.



```python
# Write your code below and press Shift+Enter to execute
album_sales_dict={"Back in Black":50,"The Bodyguard":50,"Thriller":65}
album_sales_dict
```

<details><summary>Click here for the solution</summary>

```python
album_sales_dict = {"The Bodyguard":50, "Back in Black":50, "Thriller":65}

```

</details>


b) Use the dictionary to find the total sales of <b>Thriller</b>:



```python
# Write your code below and press Shift+Enter to execute

```

<details><summary>Click here for the solution</summary>

```python
album_sales_dict["Thriller"]

```

</details>


c) Find the names of the albums from the dictionary using the method <code>keys()</code>:



```python
# Write your code below and press Shift+Enter to execute

```

<details><summary>Click here for the solution</summary>

```python
album_sales_dict.keys()

```

</details>


d) Find the values of the recording sales from the dictionary using the method <code>values</code>:



```python
# Write your code below and press Shift+Enter to execute

```

<details><summary>Click here for the solution</summary>

```python
album_sales_dict.values()

```

</details>


<hr>
<h2>The last exercise!</h2>
<p>Congratulations, you have completed your first lesson and hands-on lab in Python. However, there is one more thing you need to do. The Data Science community encourages sharing work. The best way to share and showcase your work is to share it on GitHub. By sharing your notebook on GitHub you are not only building your reputation with fellow data scientists, but you can also show it off when applying for a job. Even though this was your first piece of work, it is never too early to start building good habits. So, please read and follow <a href="https://cognitiveclass.ai/blog/data-scientists-stand-out-by-sharing-your-notebooks/?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkPY0101ENSkillsNetwork19487395-2021-01-01" target="_blank">this article</a> to learn how to share your work.
<hr>


## Author

<a href="https://www.linkedin.com/in/joseph-s-50398b136/?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkPY0101ENSkillsNetwork19487395-2021-01-01" target="_blank">Joseph Santarcangelo</a>

## Other contributors

<a href="https://www.linkedin.com/in/jiahui-mavis-zhou-a4537814a?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkPY0101ENSkillsNetwork19487395-2021-01-01">Mavis Zhou</a>

## Change Log

| Date (YYYY-MM-DD) | Version | Changed By    | Change Description                                                  |
| ----------------- | ------- | ------------- | ------------------------------------------------------------------- |
| 2020-09-09        | 2.1     | Malika Singla | Updated the variable soundtrack_dict to soundtrack_dic in Questions |
| 2020-08-26        | 2.0     | Lavanya       | Moved lab to course repo in GitLab                                  |
|                   |         |               |                                                                     |
|                   |         |               |                                                                     |

## <h3 align="center"> © IBM Corporation 2020. All rights reserved. <h3/>

