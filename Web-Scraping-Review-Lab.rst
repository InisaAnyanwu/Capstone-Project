.. raw:: html

   <p style="text-align:center">

.. raw:: html

   </p>

**Web Scraping Lab**
====================

Estimated time needed: **30** minutes

Objectives
----------

After completing this lab you will be able to:

-  Download a webpage using requests module
-  Scrape all links from a web page
-  Scrape all image urls from a web page
-  Scrape data from html tables

Scrape `www.ibm.com <http://www.ibm.com/?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDA0321ENSkillsNetwork21426264-2022-01-01>`__
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Import the required modules and functions

.. code:: ipython3

    from bs4 import BeautifulSoup # this module helps in web scrapping.
    import requests  # this module helps us to download a web page

Download the contents of the web page

.. code:: ipython3

    url = "http://www.ibm.com"

.. code:: ipython3

    # get the contents of the webpage in text format and store in a variable called data
    data  = requests.get(url).text 

Create a soup object using the class BeautifulSoup

.. code:: ipython3

    soup = BeautifulSoup(data,"html5lib")  # create a soup object using the variable 'data'

Scrape all links

.. code:: ipython3

    for link in soup.find_all('a'):  # in html anchor/link is represented by the tag <a>
        print(link.get('href'))


.. parsed-literal::

    https://www.ibm.com/data-fabric?lnk=ushpv18l1
    None
    #ibm-hp--tech-section
    https://www.ibm.com/consulting/?lnk=ushpv18intro2
    None
    https://www.ibm.com/it-infrastructure/storage/flash/offers/us-en?STW_US_HPT_buy=SDP&lnk=ushpv18f1
    https://www.ibm.com/subscribe/?lnk=ushpv18f2
    https://newsroom.ibm.com/2022-10-03-New-IBM-Study-Finds-Cybersecurity-Incident-Responders-Have-Strong-Sense-of-Service-as-Threats-Cross-Over-to-Physical-World?lnk=ushpv18f3
    https://www.ibm.com/thought-leadership/institute-business-value/en-us/report/foundations-banking-excellence?lnk=ushpv18f4
    None
    https://research.ibm.com/blog/2023-quantum-internships?lnk=ushpv18r1
    https://research.ibm.com/blog/2023-quantum-internships?lnk=ushpv18r1
    https://research.ibm.com/blog/adversarial-attack-stock-prediction?lnk=ushpv18r2
    https://research.ibm.com/blog/AI-updated-virtual-agent?lnk=ushpv18r3
    https://research.ibm.com/blog/quantum-safe-crypto-for-telco?lnk=ushpv18r4
    None
    https://www.ibm.com/case-studies/search?lnk=ushpv18mAll
    https://www.ibm.com/case-studies/bic-camera/?lnk=ushpv18m1
    https://www.ibm.com/case-studies/puma/?lnk=ushpv18m2
    https://www.ibm.com/case-studies/roma-capitale/?lnk=ushpv18m3
    None
    https://www.ibm.com/products?types[0]=trial&lnk=STW_US_MPDISC_BNR_BTN&lnk2=THP&lnk3=ushpv18tAll
    https://www.ibm.com/products/offers-and-discounts?link=ushpv18t5&lnk2=trial_mktpl_MPDISC
    https://www.ibm.com/cloud/instana?lnk=ushpv18t1&lnk2=trial_Instana&psrc=none&pexp=def
    https://www.ibm.com/products/planning-analytics?lnk=ushpv18t2&lnk2=trial_PlanningAnalytics&psrc=none&pexp=def
    https://www.ibm.com/cloud/free?lnk=ushpv18t3&lnk2=trial_Cloud&psrc=none&pexp=def
    https://www.ibm.com/search?lnk=ushpv18srch&locale=en-us&q=
    https://www.ibm.com/products?lnk=ushpv18p1&lnk2=trial_mktpl&psrc=none&pexp=def
    https://www.ibm.com/cloud/hybrid?lnk=ushpv18pt14
    https://www.ibm.com/watson?lnk=ushpv18pt17
    https://www.ibm.com/it-infrastructure?lnk=ushpv18pt19
    https://www.ibm.com/blockchain?lnk=ushpv18pt4
    https://www.ibm.com/security/products?lnk=ushpv18pt9
    https://www.ibm.com/analytics/products?lnk=ushpv18pt1
    https://www.ibm.com/cloud/automation?lnk=ushpv18ct21
    https://www.ibm.com/quantum-computing?lnk=ushpv18pt16
    https://www.ibm.com/mysupport/s/?language=en_US&lnk=ushpv18ct11
    https://www.ibm.com/training/?lnk=ushpv18ct15
    https://community.ibm.com/community/user/home/?lnk=ushpv18ct20
    https://developer.ibm.com/?lnk=ushpv18ct9
    https://www.ibm.com/garage?lnk=ushpv18pt18
    https://www.ibm.com/docs/en?lnk=ushpv18ct14
    https://www.redbooks.ibm.com/?lnk=ushpv18ct10
    https://www.ibm.com/subscribe/?lnk=ushpv18ct22
    https://www-03.ibm.com/employment/technicaltalent/developer/?lnk=ushpv18ct2


Scrape all images

.. code:: ipython3

    for link in soup.find_all('img'):# in html image is represented by the tag <img>
        print(link.get('src'))


.. parsed-literal::

    data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTA1NSIgaGVpZ2h0PSI1MjcuNSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIiB2ZXJzaW9uPSIxLjEiLz4=
    https://1.dam.s81c.com/p/077d6f8237251350/2022031-ls-data-driven-mobile-720x360.png
    https://1.dam.s81c.com/p/096c816b13c6e3f3/20221012-flash-storage-444x333.jpg
    https://1.dam.s81c.com/p/096c816b1346e3a3/20220926-26933-cybersecurity-newsletter-charles-henderson-444x333.jpg
    https://1.dam.s81c.com/p/096c816b1146e175/20221010-27021-security-responders-study-444x333.jpg
    https://1.dam.s81c.com/p/073a1ba677a4e9e7/19_24_p_gorodenkoff-196.jpg.global.s_4x3.jpg
    https://1.dam.s81c.com/p/0944d56323c6b206/20220926-r1-ibm-quantum-summer-internships-26979-1600x900.jpg
    https://1.dam.s81c.com/p/08b38f4a7f265590/20220801-r1-stock-tweet-manipulation-26864-1600x900.jpg
    https://1.dam.s81c.com/p/08f951362fa700f2/20220926-r1-text-to-speech-26995-1600x900.jpg
    https://1.dam.s81c.com/p/096c816b10c6e110/20221003-r1-telecom-task-force-27015-1600x900.jpg
    https://1.dam.s81c.com/p/096c816b1346e3aa/20221010-m-bic-camera-27022-1600x900.jpg
    https://1.dam.s81c.com/p/08a5a9b9c2c644eb/20220725-m-puma-26850-1600x900.jpg
    https://1.dam.s81c.com/p/08f951362fa700f0/20220926-m-roma-capitale-26981-1600x900.jpg
    https://1.dam.s81c.com/p/08f951362f270092/Instana-trial-800x450.jpg
    https://1.dam.s81c.com/p/096c816b10c6e111/planning-analytics-trial-800x450.jpg
    https://1.dam.s81c.com/public/content/dam/worldwide-content/homepage/ul/g/91/5f/IBM-Cloud-trial-800x450.jpg


Scrape data from html tables
----------------------------

.. code:: ipython3

    #The below url contains a html table with data about colors and color codes.

.. code:: ipython3

    url = "https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-DA0321EN-SkillsNetwork/labs/datasets/HTMLColorCodes.html"

Before proceeding to scrape a web site, you need to examine the
contents, and the way data is organized on the website. Open the above
url in your browser and check how many rows and columns are there in the
color table.

.. code:: ipython3

    # get the contents of the webpage in text format and store in a variable called data
    data  = requests.get(url).text

.. code:: ipython3

    soup = BeautifulSoup(data,"html5lib")

.. code:: ipython3

    #find a html table in the web page
    table = soup.find('table') # in html table is represented by the tag <table>

.. code:: ipython3

    #Get all rows from the table
    for row in table.find_all('tr'): # in html table row is represented by the tag <tr>
        # Get all columns in each row.
        cols = row.find_all('td') # in html a column is represented by the tag <td>
        color_name = cols[2].getText() # store the value in column 3 as color_name
        color_code = cols[3].getText() # store the value in column 4 as color_code
        print("{}--->{}".format(color_name,color_code))


.. parsed-literal::

    Color Name--->Hex Code#RRGGBB
    lightsalmon--->#FFA07A
    salmon--->#FA8072
    darksalmon--->#E9967A
    lightcoral--->#F08080
    coral--->#FF7F50
    tomato--->#FF6347
    orangered--->#FF4500
    gold--->#FFD700
    orange--->#FFA500
    darkorange--->#FF8C00
    lightyellow--->#FFFFE0
    lemonchiffon--->#FFFACD
    papayawhip--->#FFEFD5
    moccasin--->#FFE4B5
    peachpuff--->#FFDAB9
    palegoldenrod--->#EEE8AA
    khaki--->#F0E68C
    darkkhaki--->#BDB76B
    yellow--->#FFFF00
    lawngreen--->#7CFC00
    chartreuse--->#7FFF00
    limegreen--->#32CD32
    lime--->#00FF00
    forestgreen--->#228B22
    green--->#008000
    powderblue--->#B0E0E6
    lightblue--->#ADD8E6
    lightskyblue--->#87CEFA
    skyblue--->#87CEEB
    deepskyblue--->#00BFFF
    lightsteelblue--->#B0C4DE
    dodgerblue--->#1E90FF


Authors
-------

Ramesh Sannareddy

Other Contributors
~~~~~~~~~~~~~~~~~~

Rav Ahuja

Change Log
----------

+------------------+---------+------------------+------------------+
| Date             | Version | Changed By       | Change           |
| (YYYY-MM-DD)     |         |                  | Description      |
+==================+=========+==================+==================+
| 2020-10-17       | 0.1     | Ramesh           | Created initial  |
|                  |         | Sannareddy       | version of the   |
|                  |         |                  | lab              |
+------------------+---------+------------------+------------------+

Copyright © 2020 IBM Corporation. This notebook and its source code are
released under the terms of the `MIT
License <https://cognitiveclass.ai/mit-license/?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDA0321ENSkillsNetwork21426264-2022-01-01>`__.
