What is Data Analysis?
- A process of inspecting, cleansing, transforming and modeling data with the goal of discovering useful information,
  informing conclusion and supporting decision-making.

inspecting, cleansing, transforming
  - The first part of the process of Data Analysis is usually tedious, it starts by gathering the data, cleaning it and transforming it for further analysis.
This is where Python and the PyData tools excel. We’re going to be using Pandas to read, clean and transform our data.

Modeling data
- Modeling data means adapting real life scenarios to information systems. Using inferential statistics to see if any patterns or models arise. For this, we’re going to be using the statistical analysis features of Pandas and visualizations from Matplotlib and Seaborn.

discovering useful information
- Once we’ve process the data and modeled it, we’ll try to drive conclusions from it. Find interesting patterns or anomalies that might arise. The word “information” is key. We’re transforming Data into Information. Our data might be a huge list of all the purchases made in Walmart in the last year. The information will be something like: “pop-tarts sell better on Tuesdays”

informing conclusion and supporting decision-making
- This is the final objective of Data Analysis. We need to provide evidence of our findings, create readable reports and dashboards, and aid other departments with the information we’ve gathered. Multiple actors will use your analysis: marketing, sales, accounting, executives, etc. They might need to see different “views” of the same information. They might all need different reports or level of detail.

What tools are available today for Data Analysis?


![image](https://github.com/user-attachments/assets/645c0408-3fab-4179-b5d1-cc2f63946682)

We’ve broken this down into 2 main categories: “auto managed tools” are closed products. Tools that you can buy and start using right out of the box. Excel is a good example. Tableau and Looker are probably the most popular ones for Data Analysis.
In the other extreme, we have what we call “programming languages”, or we could call them “open tools”. These are not sold by any individual vendor, but they’re a combination of languages, open source libraries and products. Python, R and Julia are the most popular ones in this category.
Let’s explore the advantages and disadvantages of them.

![image](https://github.com/user-attachments/assets/80878d83-b2c3-4b8e-97c3-662f95a3acb2)

The main advantage of closed tools like Tableau or Excel is that they’re generally easy to learn. There’s a company writing documentation, providing support and driving the creation of the product. The biggest disadvantage is that the scope of the tool is limited, you can’t cross the boundaries of it.
In contrast, using Python and the universe of PyData tools, gives you amazing flexibility. Do you need to read data from a closed API using secret key authentication? You can do it. Do you need to consume data directly from AWS Kinesis? You can do it. A programming language is the most powerful tool you can learn. Another important advantage is the general scope of a programming language. What happens if Tableau, for example, goes out of business? Or if you just get bored from it and feel like your career is stuck? Learning how to process data using a programming language gives you freedom.
The main disadvantage of a programming language is that it’s not as simple to learn as with a tool. You need to learn the basics of coding first, and it takes time.

Why are we choosing Python to do Data Analysis?

- Python is the best programming language to learn to code. It’s simple, intuitive and readable. It includes thousands of libraries to do virtually anything, from cryptography to IoT.
- Python is free and open source. That means that there are thousands of eyes, very smart people seeing the internals of the language and the libraries. From Google to Bank of America, major institutions rely on Python everyday, which means that it’s very hard for it just to go away.
- Finally, Python has a great open source spirit. The community is amazing. The documentation is exhaustive and there are a lot of free tutorials around. Check out for conferences in your area, it’s very likely that there’s a local group of python developers in your city.


Let’s quickly review the Data Analysis process.

![image](https://github.com/user-attachments/assets/21900bce-f702-4806-90a0-3431b68e7a76)

- The process starts by getting the data. Where is your data coming from? Usually, it’s in your own database. But it could also come from files stored in different formats or web APIs.
- Once we’ve collected the data we’ll need to clean it. If the source of the data is your own database, then it’s probably already in shape. If you’re using more extreme sources, like web scraping, then the process will be more tedious.
- With our data cleaned, we’ll now need to rearrange and reshape the data for better analysis. Transforming fields, merging tables, combining data from multiple sources, etc. The objective of this process is to get the data ready for the next step.
- The process of analysis involves extracting patterns from the data that is now clean and in shape. Capturing trends or anomalies. Statistical analysis will be fundamental in this process.
- Finally, it’s time to do something with that analysis. If this was a Data Science project, we could be ready to implement Machine Learning models. If we focus strictly on Data Analysis, we’ll probably need to build reports, communicate our results and support decision making.
- Let me finish by saying that, in real life, this process isn’t so linear. We’re usually jumping back and forth between the steps, and it looks more like a cycle than a straight line.

What’s the difference between Data Analysis and Data Science?
![image](https://github.com/user-attachments/assets/acbc31f0-599a-4cb6-a3cb-65603869b0a5)

- The boundaries between Data Analysis and Data Science are not very clear. The main differences are that Data Scientists usually have more programming and math skills. They can then apply these skills in Machine Learning and ETL processes.
- Data Analysts, on the other hand, have better communication skills, creating better reports, with stronger storytelling abilities.
- Source: https://notebooks.ai/santiagobasulto/radar-chart-data-science-vs-data-analysis-ad638c75

Let’s explore the Python and PyData ecosystem. All the tools and libraries that we’ll be using.

![image](https://github.com/user-attachments/assets/96883e89-2adb-4cd8-b579-1612cdaee7c9)

The most important libraries we’ll be using are Pandas for Data Analysis, and Matplotlib and Seaborn for visualizations. But the ecosystem is large, and there are many useful libraries for specific use cases.

How Python Data Analysts think?

![image](https://github.com/user-attachments/assets/3b1c9c4a-c1c8-4d8c-bf86-920b01b9e7b1)

If you’re coming from a traditional Data Analysis place using tools like Excel and tableau, you’re probably used to have a constant visual reference of your data. All the tools are “point and click”. This works great for small amount of data, but it’s less useful when the amount of records grow. It’s just impossible for humans to visually reference too much data, and the processing gets incredibly slow.

![image](https://github.com/user-attachments/assets/39ed30e6-bccf-456f-94d1-cbead9998232)

In contrast, when we work with Python, we don’t have a constant visual reference of the data we’re working with. We know it’s there, we know how it looks like, we know the main statistical properties of it, but we’re not constantly looking at it. This allows us to work with millions of records incredibly fast. This also means you can move your Data Analysis processes to other computers, for example in the cloud, without much overhead.

And finally, why would you like to add Python to your Data Analysis skills.

- According to PayScale, Data Analysts that know Python and SQL are better paid than the ones that don’t know how to use programming tools.

1. What is Data Analysis
2. Real Example Data Analysis with Python
3. How to use Jupyter Notebooks
4. Intro to NumPy (exercises included)
5. Intro to Pandas (exercises included)
6. Data Cleaning
7. Reading Data SQL, CSVs, APIs, etc
8. Python in Under 10 Minutes



