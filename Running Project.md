```python
#https://www.kaggle.com/datasets/aiaiaidavid/the-big-dataset-of-ultra-marathon-running
```


```python
#Importing libraries
```


```python
import pandas as pd
```


```python
import seaborn as sns
```


```python
df = pd.read_csv("TWO_CENTURIES_OF_UM_RACES")
```

    C:\Users\azadp\AppData\Local\Temp\ipykernel_7388\3078229781.py:1: DtypeWarning: Columns (11) have mixed types. Specify dtype option on import or set low_memory=False.
      df = pd.read_csv("TWO_CENTURIES_OF_UM_RACES")
    


```python
#see the data head of 10
```


```python
df.head(10)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Year of event</th>
      <th>Event dates</th>
      <th>Event name</th>
      <th>Event distance/length</th>
      <th>Event number of finishers</th>
      <th>Athlete performance</th>
      <th>Athlete club</th>
      <th>Athlete country</th>
      <th>Athlete year of birth</th>
      <th>Athlete gender</th>
      <th>Athlete age category</th>
      <th>Athlete average speed</th>
      <th>Athlete ID</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2018</td>
      <td>06.01.2018</td>
      <td>Selva Costera (CHI)</td>
      <td>50km</td>
      <td>22</td>
      <td>4:51:39 h</td>
      <td>Tnfrc</td>
      <td>CHI</td>
      <td>1978.0</td>
      <td>M</td>
      <td>M35</td>
      <td>10.286</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2018</td>
      <td>06.01.2018</td>
      <td>Selva Costera (CHI)</td>
      <td>50km</td>
      <td>22</td>
      <td>5:15:45 h</td>
      <td>Roberto Echeverría</td>
      <td>CHI</td>
      <td>1981.0</td>
      <td>M</td>
      <td>M35</td>
      <td>9.501</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2018</td>
      <td>06.01.2018</td>
      <td>Selva Costera (CHI)</td>
      <td>50km</td>
      <td>22</td>
      <td>5:16:44 h</td>
      <td>Puro Trail Osorno</td>
      <td>CHI</td>
      <td>1987.0</td>
      <td>M</td>
      <td>M23</td>
      <td>9.472</td>
      <td>2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2018</td>
      <td>06.01.2018</td>
      <td>Selva Costera (CHI)</td>
      <td>50km</td>
      <td>22</td>
      <td>5:34:13 h</td>
      <td>Columbia</td>
      <td>ARG</td>
      <td>1976.0</td>
      <td>M</td>
      <td>M40</td>
      <td>8.976</td>
      <td>3</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2018</td>
      <td>06.01.2018</td>
      <td>Selva Costera (CHI)</td>
      <td>50km</td>
      <td>22</td>
      <td>5:54:14 h</td>
      <td>Baguales Trail</td>
      <td>CHI</td>
      <td>1992.0</td>
      <td>M</td>
      <td>M23</td>
      <td>8.469</td>
      <td>4</td>
    </tr>
    <tr>
      <th>5</th>
      <td>2018</td>
      <td>06.01.2018</td>
      <td>Selva Costera (CHI)</td>
      <td>50km</td>
      <td>22</td>
      <td>6:25:01 h</td>
      <td>NaN</td>
      <td>ARG</td>
      <td>1974.0</td>
      <td>M</td>
      <td>M40</td>
      <td>7.792</td>
      <td>5</td>
    </tr>
    <tr>
      <th>6</th>
      <td>2018</td>
      <td>06.01.2018</td>
      <td>Selva Costera (CHI)</td>
      <td>50km</td>
      <td>22</td>
      <td>6:28:00 h</td>
      <td>Los Patagones</td>
      <td>ARG</td>
      <td>1979.0</td>
      <td>F</td>
      <td>W35</td>
      <td>7.732</td>
      <td>6</td>
    </tr>
    <tr>
      <th>7</th>
      <td>2018</td>
      <td>06.01.2018</td>
      <td>Selva Costera (CHI)</td>
      <td>50km</td>
      <td>22</td>
      <td>6:32:24 h</td>
      <td>Reaktiva Chile</td>
      <td>CHI</td>
      <td>1967.0</td>
      <td>F</td>
      <td>W50</td>
      <td>7.645</td>
      <td>7</td>
    </tr>
    <tr>
      <th>8</th>
      <td>2018</td>
      <td>06.01.2018</td>
      <td>Selva Costera (CHI)</td>
      <td>50km</td>
      <td>22</td>
      <td>6:39:08 h</td>
      <td>Puro Trail Osorno</td>
      <td>CHI</td>
      <td>1985.0</td>
      <td>M</td>
      <td>M23</td>
      <td>7.516</td>
      <td>8</td>
    </tr>
    <tr>
      <th>9</th>
      <td>2018</td>
      <td>06.01.2018</td>
      <td>Selva Costera (CHI)</td>
      <td>50km</td>
      <td>22</td>
      <td>6:45:11 h</td>
      <td>Marlene Flores Team</td>
      <td>CHI</td>
      <td>1976.0</td>
      <td>M</td>
      <td>M40</td>
      <td>7.404</td>
      <td>9</td>
    </tr>
  </tbody>
</table>
</div>




```python
#To check the Shape (Rows and Columns)
```


```python
df.shape
```




    (7117634, 13)




```python
#To check the type of data our dataframe has
```


```python
df.dtypes
```




    Year of event                  int64
    Event dates                   object
    Event name                    object
    Event distance/length         object
    Event number of finishers      int64
    Athlete performance           object
    Athlete club                  object
    Athlete country               object
    Athlete year of birth        float64
    Athlete gender                object
    Athlete age category          object
    Athlete average speed         object
    Athlete ID                     int64
    dtype: object




```python
#Cleaning the data
```


```python
#Athlete of USA of 50km or 50mi in 2020
```


```python
df[(df["Athlete country"].isin(["USA"])) & (df["Event distance/length"].isin(["50km", "50mi"])) & (df["Year of event"] == 2020)]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Year of event</th>
      <th>Event dates</th>
      <th>Event name</th>
      <th>Event distance/length</th>
      <th>Event number of finishers</th>
      <th>Athlete performance</th>
      <th>Athlete club</th>
      <th>Athlete country</th>
      <th>Athlete year of birth</th>
      <th>Athlete gender</th>
      <th>Athlete age category</th>
      <th>Athlete average speed</th>
      <th>Athlete ID</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2538588</th>
      <td>2020</td>
      <td>07.-09.02.2020</td>
      <td>Taipei 48hr Ultra Marathon - 50mi (TPE)</td>
      <td>50mi</td>
      <td>38</td>
      <td>10:32:38 h</td>
      <td>NaN</td>
      <td>USA</td>
      <td>1975.0</td>
      <td>M</td>
      <td>M45</td>
      <td>7.632</td>
      <td>4543</td>
    </tr>
    <tr>
      <th>2538628</th>
      <td>2020</td>
      <td>07.-09.02.2020</td>
      <td>Taipei 48hr Ultra Marathon - 50km (TPE)</td>
      <td>50km</td>
      <td>38</td>
      <td>6:09:08 h</td>
      <td>NaN</td>
      <td>USA</td>
      <td>1975.0</td>
      <td>M</td>
      <td>M45</td>
      <td>8.127</td>
      <td>4543</td>
    </tr>
    <tr>
      <th>2538860</th>
      <td>2020</td>
      <td>07.02.2020</td>
      <td>Dead Sea Marathon Ein Bokek - 50km (ISR)</td>
      <td>50km</td>
      <td>179</td>
      <td>5:12:29 h</td>
      <td>NaN</td>
      <td>USA</td>
      <td>1963.0</td>
      <td>M</td>
      <td>M55</td>
      <td>9.601</td>
      <td>71520</td>
    </tr>
    <tr>
      <th>2538883</th>
      <td>2020</td>
      <td>07.02.2020</td>
      <td>Dead Sea Marathon Ein Bokek - 50km (ISR)</td>
      <td>50km</td>
      <td>179</td>
      <td>5:33:17 h</td>
      <td>JIM Ridolfo</td>
      <td>USA</td>
      <td>1980.0</td>
      <td>M</td>
      <td>M35</td>
      <td>9.001</td>
      <td>366634</td>
    </tr>
    <tr>
      <th>2539317</th>
      <td>2020</td>
      <td>02.02.2020</td>
      <td>Gumi Dorissa Trail Run (KOR)</td>
      <td>50km</td>
      <td>14</td>
      <td>7:19:11 h</td>
      <td>NaN</td>
      <td>USA</td>
      <td>1971.0</td>
      <td>M</td>
      <td>M45</td>
      <td>6.831</td>
      <td>810218</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>2760957</th>
      <td>2020</td>
      <td>03.10.2020</td>
      <td>Yankee Springs Fall Trail Run Festival (USA)</td>
      <td>50km</td>
      <td>30</td>
      <td>7:07:48 h</td>
      <td>*East Lansing, MI</td>
      <td>USA</td>
      <td>1958.0</td>
      <td>F</td>
      <td>W60</td>
      <td>7.013</td>
      <td>816361</td>
    </tr>
    <tr>
      <th>2760958</th>
      <td>2020</td>
      <td>03.10.2020</td>
      <td>Yankee Springs Fall Trail Run Festival (USA)</td>
      <td>50km</td>
      <td>30</td>
      <td>7:27:22 h</td>
      <td>*Traverse City, MI</td>
      <td>USA</td>
      <td>1977.0</td>
      <td>F</td>
      <td>W40</td>
      <td>6.706</td>
      <td>326469</td>
    </tr>
    <tr>
      <th>2760959</th>
      <td>2020</td>
      <td>03.10.2020</td>
      <td>Yankee Springs Fall Trail Run Festival (USA)</td>
      <td>50km</td>
      <td>30</td>
      <td>7:27:24 h</td>
      <td>*Traverse City, MI</td>
      <td>USA</td>
      <td>1962.0</td>
      <td>F</td>
      <td>W55</td>
      <td>6.705</td>
      <td>372174</td>
    </tr>
    <tr>
      <th>2760960</th>
      <td>2020</td>
      <td>03.10.2020</td>
      <td>Yankee Springs Fall Trail Run Festival (USA)</td>
      <td>50km</td>
      <td>30</td>
      <td>7:38:30 h</td>
      <td>*Mason, MI</td>
      <td>USA</td>
      <td>1981.0</td>
      <td>F</td>
      <td>W35</td>
      <td>6.543</td>
      <td>860349</td>
    </tr>
    <tr>
      <th>2760961</th>
      <td>2020</td>
      <td>03.10.2020</td>
      <td>Yankee Springs Fall Trail Run Festival (USA)</td>
      <td>50km</td>
      <td>30</td>
      <td>7:59:53 h</td>
      <td>NaN</td>
      <td>USA</td>
      <td>1980.0</td>
      <td>M</td>
      <td>M35</td>
      <td>6.252</td>
      <td>770097</td>
    </tr>
  </tbody>
</table>
<p>26326 rows × 13 columns</p>
</div>




```python
#Race in USA of 50km or 50mi in 2018
```


```python
df2 = df[(df["Event distance/length"].isin(["50km", "50mi"])) & (df["Year of event"] == 2018) & (df["Event name"].str.split('(').str.get(1).str.split(')').str.get(0) == 'USA')]
```


```python
df2.head(10)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Year of event</th>
      <th>Event dates</th>
      <th>Event name</th>
      <th>Event distance/length</th>
      <th>Event number of finishers</th>
      <th>Athlete performance</th>
      <th>Athlete club</th>
      <th>Athlete country</th>
      <th>Athlete year of birth</th>
      <th>Athlete gender</th>
      <th>Athlete age category</th>
      <th>Athlete average speed</th>
      <th>Athlete ID</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>55</th>
      <td>2018</td>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge (USA)</td>
      <td>50mi</td>
      <td>9</td>
      <td>9:53:05 h</td>
      <td>*Middleville, MI</td>
      <td>USA</td>
      <td>1983.0</td>
      <td>M</td>
      <td>M23</td>
      <td>8.141</td>
      <td>55</td>
    </tr>
    <tr>
      <th>56</th>
      <td>2018</td>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge (USA)</td>
      <td>50mi</td>
      <td>9</td>
      <td>11:09:35 h</td>
      <td>*Waterloo, ON</td>
      <td>CAN</td>
      <td>1977.0</td>
      <td>F</td>
      <td>W40</td>
      <td>7.211</td>
      <td>56</td>
    </tr>
    <tr>
      <th>57</th>
      <td>2018</td>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge (USA)</td>
      <td>50mi</td>
      <td>9</td>
      <td>11:33:00 h</td>
      <td>*Kitchener, ON</td>
      <td>CAN</td>
      <td>1976.0</td>
      <td>M</td>
      <td>M40</td>
      <td>6.967</td>
      <td>57</td>
    </tr>
    <tr>
      <th>58</th>
      <td>2018</td>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge (USA)</td>
      <td>50mi</td>
      <td>9</td>
      <td>11:38:17 h</td>
      <td>*Utica, MI</td>
      <td>USA</td>
      <td>1986.0</td>
      <td>M</td>
      <td>M23</td>
      <td>6.914</td>
      <td>58</td>
    </tr>
    <tr>
      <th>59</th>
      <td>2018</td>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge (USA)</td>
      <td>50mi</td>
      <td>9</td>
      <td>11:56:35 h</td>
      <td>*Grass Lake, MI</td>
      <td>USA</td>
      <td>1988.0</td>
      <td>M</td>
      <td>M23</td>
      <td>6.738</td>
      <td>59</td>
    </tr>
    <tr>
      <th>60</th>
      <td>2018</td>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge (USA)</td>
      <td>50mi</td>
      <td>9</td>
      <td>12:32:16 h</td>
      <td>*Olaton, KY</td>
      <td>USA</td>
      <td>1995.0</td>
      <td>M</td>
      <td>MU23</td>
      <td>6.418</td>
      <td>60</td>
    </tr>
    <tr>
      <th>61</th>
      <td>2018</td>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge (USA)</td>
      <td>50mi</td>
      <td>9</td>
      <td>12:39:36 h</td>
      <td>*Wyoming, MI</td>
      <td>USA</td>
      <td>1979.0</td>
      <td>M</td>
      <td>M35</td>
      <td>6.356</td>
      <td>61</td>
    </tr>
    <tr>
      <th>62</th>
      <td>2018</td>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge (USA)</td>
      <td>50mi</td>
      <td>9</td>
      <td>12:39:36 h</td>
      <td>*Grand Rapids, MI</td>
      <td>USA</td>
      <td>1977.0</td>
      <td>F</td>
      <td>W40</td>
      <td>6.356</td>
      <td>62</td>
    </tr>
    <tr>
      <th>63</th>
      <td>2018</td>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge (USA)</td>
      <td>50mi</td>
      <td>9</td>
      <td>13:24:05 h</td>
      <td>*Lansing, MI</td>
      <td>USA</td>
      <td>1990.0</td>
      <td>F</td>
      <td>W23</td>
      <td>6.004</td>
      <td>63</td>
    </tr>
    <tr>
      <th>64</th>
      <td>2018</td>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 km Winter Challenge (USA)</td>
      <td>50km</td>
      <td>36</td>
      <td>5:09:40 h</td>
      <td>*Okemos, MI</td>
      <td>USA</td>
      <td>1991.0</td>
      <td>F</td>
      <td>W23</td>
      <td>9.688</td>
      <td>64</td>
    </tr>
  </tbody>
</table>
</div>




```python
df2.shape
```




    (64299, 13)




```python
#Remove USA from event name
```


```python
df2["Event name"] = df2["Event name"].str.split('(').str.get(0)
```

    C:\Users\azadp\AppData\Local\Temp\ipykernel_7388\9866251.py:1: SettingWithCopyWarning: 
    A value is trying to be set on a copy of a slice from a DataFrame.
    Try using .loc[row_indexer,col_indexer] = value instead
    
    See the caveats in the documentation: https://pandas.pydata.org/pandas-docs/stable/user_guide/indexing.html#returning-a-view-versus-a-copy
      df2["Event name"] = df2["Event name"].str.split('(').str.get(0)
    


```python
df2.head(10)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Year of event</th>
      <th>Event dates</th>
      <th>Event name</th>
      <th>Event distance/length</th>
      <th>Event number of finishers</th>
      <th>Athlete performance</th>
      <th>Athlete club</th>
      <th>Athlete country</th>
      <th>Athlete year of birth</th>
      <th>Athlete gender</th>
      <th>Athlete age category</th>
      <th>Athlete average speed</th>
      <th>Athlete ID</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>55</th>
      <td>2018</td>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>9:53:05 h</td>
      <td>*Middleville, MI</td>
      <td>USA</td>
      <td>1983.0</td>
      <td>M</td>
      <td>M23</td>
      <td>8.141</td>
      <td>55</td>
    </tr>
    <tr>
      <th>56</th>
      <td>2018</td>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>11:09:35 h</td>
      <td>*Waterloo, ON</td>
      <td>CAN</td>
      <td>1977.0</td>
      <td>F</td>
      <td>W40</td>
      <td>7.211</td>
      <td>56</td>
    </tr>
    <tr>
      <th>57</th>
      <td>2018</td>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>11:33:00 h</td>
      <td>*Kitchener, ON</td>
      <td>CAN</td>
      <td>1976.0</td>
      <td>M</td>
      <td>M40</td>
      <td>6.967</td>
      <td>57</td>
    </tr>
    <tr>
      <th>58</th>
      <td>2018</td>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>11:38:17 h</td>
      <td>*Utica, MI</td>
      <td>USA</td>
      <td>1986.0</td>
      <td>M</td>
      <td>M23</td>
      <td>6.914</td>
      <td>58</td>
    </tr>
    <tr>
      <th>59</th>
      <td>2018</td>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>11:56:35 h</td>
      <td>*Grass Lake, MI</td>
      <td>USA</td>
      <td>1988.0</td>
      <td>M</td>
      <td>M23</td>
      <td>6.738</td>
      <td>59</td>
    </tr>
    <tr>
      <th>60</th>
      <td>2018</td>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>12:32:16 h</td>
      <td>*Olaton, KY</td>
      <td>USA</td>
      <td>1995.0</td>
      <td>M</td>
      <td>MU23</td>
      <td>6.418</td>
      <td>60</td>
    </tr>
    <tr>
      <th>61</th>
      <td>2018</td>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>12:39:36 h</td>
      <td>*Wyoming, MI</td>
      <td>USA</td>
      <td>1979.0</td>
      <td>M</td>
      <td>M35</td>
      <td>6.356</td>
      <td>61</td>
    </tr>
    <tr>
      <th>62</th>
      <td>2018</td>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>12:39:36 h</td>
      <td>*Grand Rapids, MI</td>
      <td>USA</td>
      <td>1977.0</td>
      <td>F</td>
      <td>W40</td>
      <td>6.356</td>
      <td>62</td>
    </tr>
    <tr>
      <th>63</th>
      <td>2018</td>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>13:24:05 h</td>
      <td>*Lansing, MI</td>
      <td>USA</td>
      <td>1990.0</td>
      <td>F</td>
      <td>W23</td>
      <td>6.004</td>
      <td>63</td>
    </tr>
    <tr>
      <th>64</th>
      <td>2018</td>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 km Winter Challenge</td>
      <td>50km</td>
      <td>36</td>
      <td>5:09:40 h</td>
      <td>*Okemos, MI</td>
      <td>USA</td>
      <td>1991.0</td>
      <td>F</td>
      <td>W23</td>
      <td>9.688</td>
      <td>64</td>
    </tr>
  </tbody>
</table>
</div>




```python
#Make a column for athlete's age at the time of race
```


```python
df2["Athlete age"] = 2018 - df2["Athlete year of birth"]
```

    C:\Users\azadp\AppData\Local\Temp\ipykernel_7388\314522473.py:1: SettingWithCopyWarning: 
    A value is trying to be set on a copy of a slice from a DataFrame.
    Try using .loc[row_indexer,col_indexer] = value instead
    
    See the caveats in the documentation: https://pandas.pydata.org/pandas-docs/stable/user_guide/indexing.html#returning-a-view-versus-a-copy
      df2["Athlete age"] = 2018 - df2["Athlete year of birth"]
    


```python
df2["Athlete age"].head()
```




    55    35.0
    56    41.0
    57    42.0
    58    32.0
    59    30.0
    Name: Athlete age, dtype: float64




```python
#Remove h from athlete's performance
```


```python
df2["Athlete performance"] = df2["Athlete performance"].str.split(" ").str.get(0)
df2["Athlete performance"].head()
```

    C:\Users\azadp\AppData\Local\Temp\ipykernel_7388\887016247.py:1: SettingWithCopyWarning: 
    A value is trying to be set on a copy of a slice from a DataFrame.
    Try using .loc[row_indexer,col_indexer] = value instead
    
    See the caveats in the documentation: https://pandas.pydata.org/pandas-docs/stable/user_guide/indexing.html#returning-a-view-versus-a-copy
      df2["Athlete performance"] = df2["Athlete performance"].str.split(" ").str.get(0)
    




    55     9:53:05
    56    11:09:35
    57    11:33:00
    58    11:38:17
    59    11:56:35
    Name: Athlete performance, dtype: object




```python
#drop columns Athlete club, Athlete country, Athlete year of birth, Athlete age category
```


```python
df2 = df2.drop(["Athlete club","Athlete country","Athlete year of birth","Athlete age category"], axis = 1)
```


```python
#Clean up null values
```


```python
df2.isna().sum()
```




    Year of event                  0
    Event dates                    0
    Event name                     0
    Event distance/length          0
    Event number of finishers      0
    Athlete performance            0
    Athlete gender                 0
    Athlete average speed          0
    Athlete ID                     0
    Athlete age                  575
    dtype: int64




```python
df2[df2["Athlete age"].isna()==1]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Year of event</th>
      <th>Event dates</th>
      <th>Event name</th>
      <th>Event distance/length</th>
      <th>Event number of finishers</th>
      <th>Athlete performance</th>
      <th>Athlete gender</th>
      <th>Athlete average speed</th>
      <th>Athlete ID</th>
      <th>Athlete age</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>453</th>
      <td>2018</td>
      <td>01.01.2018</td>
      <td>Red Eye 50km</td>
      <td>50km</td>
      <td>21</td>
      <td>5:10:00</td>
      <td>M</td>
      <td>9.677</td>
      <td>453</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>456</th>
      <td>2018</td>
      <td>01.01.2018</td>
      <td>Red Eye 50km</td>
      <td>50km</td>
      <td>21</td>
      <td>5:44:00</td>
      <td>M</td>
      <td>8.721</td>
      <td>456</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>459</th>
      <td>2018</td>
      <td>01.01.2018</td>
      <td>Red Eye 50km</td>
      <td>50km</td>
      <td>21</td>
      <td>6:07:00</td>
      <td>M</td>
      <td>8.174</td>
      <td>459</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>460</th>
      <td>2018</td>
      <td>01.01.2018</td>
      <td>Red Eye 50km</td>
      <td>50km</td>
      <td>21</td>
      <td>6:12:00</td>
      <td>M</td>
      <td>8.065</td>
      <td>460</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>13214</th>
      <td>2018</td>
      <td>17.03.2018</td>
      <td>Lt. JC Stone 50K UltraMarathon</td>
      <td>50km</td>
      <td>34</td>
      <td>4:54:43</td>
      <td>F</td>
      <td>10.179</td>
      <td>12483</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>659684</th>
      <td>2018</td>
      <td>27.10.2018</td>
      <td>Lake Hodges Trail Fest 50K</td>
      <td>50km</td>
      <td>133</td>
      <td>8:24:14</td>
      <td>F</td>
      <td>5.95</td>
      <td>374269</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>659685</th>
      <td>2018</td>
      <td>27.10.2018</td>
      <td>Lake Hodges Trail Fest 50K</td>
      <td>50km</td>
      <td>133</td>
      <td>8:25:12</td>
      <td>F</td>
      <td>5.938</td>
      <td>358717</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>659688</th>
      <td>2018</td>
      <td>27.10.2018</td>
      <td>Lake Hodges Trail Fest 50K</td>
      <td>50km</td>
      <td>133</td>
      <td>8:29:59</td>
      <td>M</td>
      <td>5.883</td>
      <td>204804</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>659689</th>
      <td>2018</td>
      <td>27.10.2018</td>
      <td>Lake Hodges Trail Fest 50K</td>
      <td>50km</td>
      <td>133</td>
      <td>8:31:30</td>
      <td>F</td>
      <td>5.865</td>
      <td>374272</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>659690</th>
      <td>2018</td>
      <td>27.10.2018</td>
      <td>Lake Hodges Trail Fest 50K</td>
      <td>50km</td>
      <td>133</td>
      <td>8:35:28</td>
      <td>M</td>
      <td>5.82</td>
      <td>374273</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
<p>575 rows × 10 columns</p>
</div>




```python
df2 = df2.dropna()
```


```python
df2.shape
```




    (63724, 10)




```python
#Check for duplicates
```


```python
df2[df2.duplicated()== True]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Year of event</th>
      <th>Event dates</th>
      <th>Event name</th>
      <th>Event distance/length</th>
      <th>Event number of finishers</th>
      <th>Athlete performance</th>
      <th>Athlete gender</th>
      <th>Athlete average speed</th>
      <th>Athlete ID</th>
      <th>Athlete age</th>
    </tr>
  </thead>
  <tbody>
  </tbody>
</table>
</div>




```python
#reset index
```


```python
df2.reset_index(drop = True)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Year of event</th>
      <th>Event dates</th>
      <th>Event name</th>
      <th>Event distance/length</th>
      <th>Event number of finishers</th>
      <th>Athlete performance</th>
      <th>Athlete gender</th>
      <th>Athlete average speed</th>
      <th>Athlete ID</th>
      <th>Athlete age</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2018</td>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>9:53:05</td>
      <td>M</td>
      <td>8.141</td>
      <td>55</td>
      <td>35.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2018</td>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>11:09:35</td>
      <td>F</td>
      <td>7.211</td>
      <td>56</td>
      <td>41.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2018</td>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>11:33:00</td>
      <td>M</td>
      <td>6.967</td>
      <td>57</td>
      <td>42.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2018</td>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>11:38:17</td>
      <td>M</td>
      <td>6.914</td>
      <td>58</td>
      <td>32.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2018</td>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>11:56:35</td>
      <td>M</td>
      <td>6.738</td>
      <td>59</td>
      <td>30.0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>63719</th>
      <td>2018</td>
      <td>27.-28.10.2018</td>
      <td>Cactus Rose 50 Mile</td>
      <td>50mi</td>
      <td>29</td>
      <td>17:05:58</td>
      <td>M</td>
      <td>4.706</td>
      <td>68122</td>
      <td>46.0</td>
    </tr>
    <tr>
      <th>63720</th>
      <td>2018</td>
      <td>27.-28.10.2018</td>
      <td>Cactus Rose 50 Mile</td>
      <td>50mi</td>
      <td>29</td>
      <td>18:13:01</td>
      <td>M</td>
      <td>4.417</td>
      <td>23336</td>
      <td>65.0</td>
    </tr>
    <tr>
      <th>63721</th>
      <td>2018</td>
      <td>27.-28.10.2018</td>
      <td>Cactus Rose 50 Mile</td>
      <td>50mi</td>
      <td>29</td>
      <td>18:49:58</td>
      <td>M</td>
      <td>4.273</td>
      <td>375022</td>
      <td>32.0</td>
    </tr>
    <tr>
      <th>63722</th>
      <td>2018</td>
      <td>27.-28.10.2018</td>
      <td>Cactus Rose 50 Mile</td>
      <td>50mi</td>
      <td>29</td>
      <td>23:30:00</td>
      <td>M</td>
      <td>3.424</td>
      <td>68273</td>
      <td>66.0</td>
    </tr>
    <tr>
      <th>63723</th>
      <td>2018</td>
      <td>27.-28.10.2018</td>
      <td>Cactus Rose 50 Mile</td>
      <td>50mi</td>
      <td>29</td>
      <td>25:40:10</td>
      <td>M</td>
      <td>3.135</td>
      <td>341648</td>
      <td>67.0</td>
    </tr>
  </tbody>
</table>
<p>63724 rows × 10 columns</p>
</div>




```python
#Fix types
```


```python
df2["Athlete age"] = df2["Athlete age"].astype(int)
```


```python
df2["Athlete average speed"] = df2["Athlete average speed"].astype(float)
```


```python
df2.dtypes
```




    Year of event                  int64
    Event dates                   object
    Event name                    object
    Event distance/length         object
    Event number of finishers      int64
    Athlete performance           object
    Athlete gender                object
    Athlete average speed        float64
    Athlete ID                     int64
    Athlete age                    int32
    dtype: object




```python
#Rename Columns
```


```python
df2.columns
```




    Index(['Year of event', 'Event dates', 'Event name', 'Event distance/length',
           'Event number of finishers', 'Athlete performance', 'Athlete gender',
           'Athlete average speed', 'Athlete ID', 'Athlete age'],
          dtype='object')




```python
df2 = df2.rename(columns = {'Year of event' : "year", 
                             'Event dates': "race_day", 
                             'Event name' : "event_name", 
                             'Event distance/length' : "race_length",
                             'Event number of finishers' : "number_of_finishers", 
                             'Athlete performance' : "athlete_performance", 
                             'Athlete gender' : "athlete_gender",
                             'Athlete average speed': "athlete_average_speed",
                             'Athlete ID' : "athlete_age", 
                             'Athlete age' : "athlete_age"
                           })
```


```python
df2 = df2.rename(columns = {"athlete_age" : "athlete_id"})
df2.columns.values[9] = "athlete_age"
```


```python
df2.head(10)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>year</th>
      <th>race_day</th>
      <th>event_name</th>
      <th>race_length</th>
      <th>number_of_finishers</th>
      <th>athlete_performance</th>
      <th>athlete_gender</th>
      <th>athlete_average_speed</th>
      <th>athlete_id</th>
      <th>athlete_age</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>55</th>
      <td>2018</td>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>9:53:05</td>
      <td>M</td>
      <td>8.141</td>
      <td>55</td>
      <td>35</td>
    </tr>
    <tr>
      <th>56</th>
      <td>2018</td>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>11:09:35</td>
      <td>F</td>
      <td>7.211</td>
      <td>56</td>
      <td>41</td>
    </tr>
    <tr>
      <th>57</th>
      <td>2018</td>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>11:33:00</td>
      <td>M</td>
      <td>6.967</td>
      <td>57</td>
      <td>42</td>
    </tr>
    <tr>
      <th>58</th>
      <td>2018</td>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>11:38:17</td>
      <td>M</td>
      <td>6.914</td>
      <td>58</td>
      <td>32</td>
    </tr>
    <tr>
      <th>59</th>
      <td>2018</td>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>11:56:35</td>
      <td>M</td>
      <td>6.738</td>
      <td>59</td>
      <td>30</td>
    </tr>
    <tr>
      <th>60</th>
      <td>2018</td>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>12:32:16</td>
      <td>M</td>
      <td>6.418</td>
      <td>60</td>
      <td>23</td>
    </tr>
    <tr>
      <th>61</th>
      <td>2018</td>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>12:39:36</td>
      <td>M</td>
      <td>6.356</td>
      <td>61</td>
      <td>39</td>
    </tr>
    <tr>
      <th>62</th>
      <td>2018</td>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>12:39:36</td>
      <td>F</td>
      <td>6.356</td>
      <td>62</td>
      <td>41</td>
    </tr>
    <tr>
      <th>63</th>
      <td>2018</td>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>13:24:05</td>
      <td>F</td>
      <td>6.004</td>
      <td>63</td>
      <td>28</td>
    </tr>
    <tr>
      <th>64</th>
      <td>2018</td>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 km Winter Challenge</td>
      <td>50km</td>
      <td>36</td>
      <td>5:09:40</td>
      <td>F</td>
      <td>9.688</td>
      <td>64</td>
      <td>27</td>
    </tr>
  </tbody>
</table>
</div>




```python
#reorder columns
```


```python
df2.columns
```




    Index(['year', 'race_day', 'event_name', 'race_length', 'number_of_finishers',
           'athlete_performance', 'athlete_gender', 'athlete_average_speed',
           'athlete_id', 'athlete_age'],
          dtype='object')




```python
df3 = df2[["race_day", 'event_name', 'race_length', 'number_of_finishers',
'athlete_id','athlete_gender', 'athlete_age','athlete_performance', 'athlete_average_speed']]
```


```python
df3.head(10)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>race_day</th>
      <th>event_name</th>
      <th>race_length</th>
      <th>number_of_finishers</th>
      <th>athlete_id</th>
      <th>athlete_gender</th>
      <th>athlete_age</th>
      <th>athlete_performance</th>
      <th>athlete_average_speed</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>55</th>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>55</td>
      <td>M</td>
      <td>35</td>
      <td>9:53:05</td>
      <td>8.141</td>
    </tr>
    <tr>
      <th>56</th>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>56</td>
      <td>F</td>
      <td>41</td>
      <td>11:09:35</td>
      <td>7.211</td>
    </tr>
    <tr>
      <th>57</th>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>57</td>
      <td>M</td>
      <td>42</td>
      <td>11:33:00</td>
      <td>6.967</td>
    </tr>
    <tr>
      <th>58</th>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>58</td>
      <td>M</td>
      <td>32</td>
      <td>11:38:17</td>
      <td>6.914</td>
    </tr>
    <tr>
      <th>59</th>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>59</td>
      <td>M</td>
      <td>30</td>
      <td>11:56:35</td>
      <td>6.738</td>
    </tr>
    <tr>
      <th>60</th>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>60</td>
      <td>M</td>
      <td>23</td>
      <td>12:32:16</td>
      <td>6.418</td>
    </tr>
    <tr>
      <th>61</th>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>61</td>
      <td>M</td>
      <td>39</td>
      <td>12:39:36</td>
      <td>6.356</td>
    </tr>
    <tr>
      <th>62</th>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>62</td>
      <td>F</td>
      <td>41</td>
      <td>12:39:36</td>
      <td>6.356</td>
    </tr>
    <tr>
      <th>63</th>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>63</td>
      <td>F</td>
      <td>28</td>
      <td>13:24:05</td>
      <td>6.004</td>
    </tr>
    <tr>
      <th>64</th>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 km Winter Challenge</td>
      <td>50km</td>
      <td>36</td>
      <td>64</td>
      <td>F</td>
      <td>27</td>
      <td>5:09:40</td>
      <td>9.688</td>
    </tr>
  </tbody>
</table>
</div>




```python
#finding entries of race named Everglades 50 Mile Ultra Run
```


```python
df3[df3["event_name"] == "Everglades 50 Mile Ultra Run "]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>race_day</th>
      <th>event_name</th>
      <th>race_length</th>
      <th>number_of_finishers</th>
      <th>athlete_id</th>
      <th>athlete_gender</th>
      <th>athlete_age</th>
      <th>athlete_performance</th>
      <th>athlete_average_speed</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>51923</th>
      <td>17.02.2018</td>
      <td>Everglades 50 Mile Ultra Run</td>
      <td>50mi</td>
      <td>23</td>
      <td>47601</td>
      <td>M</td>
      <td>38</td>
      <td>7:00:00</td>
      <td>11.495</td>
    </tr>
    <tr>
      <th>51924</th>
      <td>17.02.2018</td>
      <td>Everglades 50 Mile Ultra Run</td>
      <td>50mi</td>
      <td>23</td>
      <td>37220</td>
      <td>M</td>
      <td>29</td>
      <td>8:29:48</td>
      <td>9.470</td>
    </tr>
    <tr>
      <th>51925</th>
      <td>17.02.2018</td>
      <td>Everglades 50 Mile Ultra Run</td>
      <td>50mi</td>
      <td>23</td>
      <td>47602</td>
      <td>M</td>
      <td>39</td>
      <td>8:45:31</td>
      <td>9.187</td>
    </tr>
    <tr>
      <th>51926</th>
      <td>17.02.2018</td>
      <td>Everglades 50 Mile Ultra Run</td>
      <td>50mi</td>
      <td>23</td>
      <td>47603</td>
      <td>M</td>
      <td>51</td>
      <td>9:01:52</td>
      <td>8.910</td>
    </tr>
    <tr>
      <th>51927</th>
      <td>17.02.2018</td>
      <td>Everglades 50 Mile Ultra Run</td>
      <td>50mi</td>
      <td>23</td>
      <td>47604</td>
      <td>M</td>
      <td>32</td>
      <td>9:26:06</td>
      <td>8.529</td>
    </tr>
    <tr>
      <th>51928</th>
      <td>17.02.2018</td>
      <td>Everglades 50 Mile Ultra Run</td>
      <td>50mi</td>
      <td>23</td>
      <td>47605</td>
      <td>M</td>
      <td>40</td>
      <td>9:40:18</td>
      <td>8.320</td>
    </tr>
    <tr>
      <th>51929</th>
      <td>17.02.2018</td>
      <td>Everglades 50 Mile Ultra Run</td>
      <td>50mi</td>
      <td>23</td>
      <td>36476</td>
      <td>M</td>
      <td>54</td>
      <td>9:42:43</td>
      <td>8.285</td>
    </tr>
    <tr>
      <th>51930</th>
      <td>17.02.2018</td>
      <td>Everglades 50 Mile Ultra Run</td>
      <td>50mi</td>
      <td>23</td>
      <td>47606</td>
      <td>M</td>
      <td>49</td>
      <td>9:55:37</td>
      <td>8.106</td>
    </tr>
    <tr>
      <th>51931</th>
      <td>17.02.2018</td>
      <td>Everglades 50 Mile Ultra Run</td>
      <td>50mi</td>
      <td>23</td>
      <td>47607</td>
      <td>M</td>
      <td>42</td>
      <td>9:58:07</td>
      <td>8.072</td>
    </tr>
    <tr>
      <th>51932</th>
      <td>17.02.2018</td>
      <td>Everglades 50 Mile Ultra Run</td>
      <td>50mi</td>
      <td>23</td>
      <td>47608</td>
      <td>M</td>
      <td>37</td>
      <td>10:21:15</td>
      <td>7.771</td>
    </tr>
    <tr>
      <th>51933</th>
      <td>17.02.2018</td>
      <td>Everglades 50 Mile Ultra Run</td>
      <td>50mi</td>
      <td>23</td>
      <td>47609</td>
      <td>M</td>
      <td>38</td>
      <td>10:47:05</td>
      <td>7.461</td>
    </tr>
    <tr>
      <th>51934</th>
      <td>17.02.2018</td>
      <td>Everglades 50 Mile Ultra Run</td>
      <td>50mi</td>
      <td>23</td>
      <td>47610</td>
      <td>M</td>
      <td>35</td>
      <td>10:56:06</td>
      <td>7.359</td>
    </tr>
    <tr>
      <th>51935</th>
      <td>17.02.2018</td>
      <td>Everglades 50 Mile Ultra Run</td>
      <td>50mi</td>
      <td>23</td>
      <td>47611</td>
      <td>F</td>
      <td>33</td>
      <td>10:56:50</td>
      <td>7.350</td>
    </tr>
    <tr>
      <th>51936</th>
      <td>17.02.2018</td>
      <td>Everglades 50 Mile Ultra Run</td>
      <td>50mi</td>
      <td>23</td>
      <td>47612</td>
      <td>F</td>
      <td>38</td>
      <td>11:01:52</td>
      <td>7.295</td>
    </tr>
    <tr>
      <th>51937</th>
      <td>17.02.2018</td>
      <td>Everglades 50 Mile Ultra Run</td>
      <td>50mi</td>
      <td>23</td>
      <td>47613</td>
      <td>M</td>
      <td>61</td>
      <td>11:35:50</td>
      <td>6.938</td>
    </tr>
    <tr>
      <th>51938</th>
      <td>17.02.2018</td>
      <td>Everglades 50 Mile Ultra Run</td>
      <td>50mi</td>
      <td>23</td>
      <td>47614</td>
      <td>F</td>
      <td>51</td>
      <td>11:46:45</td>
      <td>6.831</td>
    </tr>
    <tr>
      <th>51939</th>
      <td>17.02.2018</td>
      <td>Everglades 50 Mile Ultra Run</td>
      <td>50mi</td>
      <td>23</td>
      <td>47615</td>
      <td>M</td>
      <td>51</td>
      <td>12:04:12</td>
      <td>6.667</td>
    </tr>
    <tr>
      <th>51940</th>
      <td>17.02.2018</td>
      <td>Everglades 50 Mile Ultra Run</td>
      <td>50mi</td>
      <td>23</td>
      <td>19081</td>
      <td>M</td>
      <td>50</td>
      <td>12:11:39</td>
      <td>6.599</td>
    </tr>
    <tr>
      <th>51941</th>
      <td>17.02.2018</td>
      <td>Everglades 50 Mile Ultra Run</td>
      <td>50mi</td>
      <td>23</td>
      <td>47616</td>
      <td>F</td>
      <td>50</td>
      <td>12:41:05</td>
      <td>6.344</td>
    </tr>
    <tr>
      <th>51942</th>
      <td>17.02.2018</td>
      <td>Everglades 50 Mile Ultra Run</td>
      <td>50mi</td>
      <td>23</td>
      <td>12531</td>
      <td>M</td>
      <td>40</td>
      <td>12:43:43</td>
      <td>6.322</td>
    </tr>
    <tr>
      <th>51943</th>
      <td>17.02.2018</td>
      <td>Everglades 50 Mile Ultra Run</td>
      <td>50mi</td>
      <td>23</td>
      <td>34666</td>
      <td>F</td>
      <td>23</td>
      <td>13:57:09</td>
      <td>5.767</td>
    </tr>
    <tr>
      <th>51944</th>
      <td>17.02.2018</td>
      <td>Everglades 50 Mile Ultra Run</td>
      <td>50mi</td>
      <td>23</td>
      <td>47617</td>
      <td>F</td>
      <td>47</td>
      <td>13:57:10</td>
      <td>5.767</td>
    </tr>
    <tr>
      <th>51945</th>
      <td>17.02.2018</td>
      <td>Everglades 50 Mile Ultra Run</td>
      <td>50mi</td>
      <td>23</td>
      <td>47618</td>
      <td>M</td>
      <td>43</td>
      <td>13:57:10</td>
      <td>5.767</td>
    </tr>
  </tbody>
</table>
</div>




```python
#finding entries with athlete_id 1100
```


```python
df3[df3["athlete_id"] == 1100]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>race_day</th>
      <th>event_name</th>
      <th>race_length</th>
      <th>number_of_finishers</th>
      <th>athlete_id</th>
      <th>athlete_gender</th>
      <th>athlete_age</th>
      <th>athlete_performance</th>
      <th>athlete_average_speed</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1102</th>
      <td>24.03.2018</td>
      <td>XTERRA Northeast Trail Run Series – Shepaug Ru...</td>
      <td>50km</td>
      <td>10</td>
      <td>1100</td>
      <td>M</td>
      <td>38</td>
      <td>5:51:48</td>
      <td>8.528</td>
    </tr>
    <tr>
      <th>90185</th>
      <td>05.05.2018</td>
      <td>Endurance Challenge - New York Trail 50 Miles</td>
      <td>50mi</td>
      <td>271</td>
      <td>1100</td>
      <td>M</td>
      <td>38</td>
      <td>10:53:44</td>
      <td>7.385</td>
    </tr>
  </tbody>
</table>
</div>




```python
#charts and graphs
```


```python
df3["race_length"] = df3["race_length"].astype("category")
```

    C:\Users\azadp\AppData\Local\Temp\ipykernel_7388\1862522557.py:1: SettingWithCopyWarning: 
    A value is trying to be set on a copy of a slice from a DataFrame.
    Try using .loc[row_indexer,col_indexer] = value instead
    
    See the caveats in the documentation: https://pandas.pydata.org/pandas-docs/stable/user_guide/indexing.html#returning-a-view-versus-a-copy
      df3["race_length"] = df3["race_length"].astype("category")
    


```python
df3.groupby(['race_length', 'athlete_gender']).count()
```

    C:\Users\azadp\AppData\Local\Temp\ipykernel_7388\740476109.py:1: FutureWarning: The default of observed=False is deprecated and will be changed to True in a future version of pandas. Pass observed=False to retain current behavior or observed=True to adopt the future default and silence this warning.
      df3.groupby(['race_length', 'athlete_gender']).count()
    




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th></th>
      <th>race_day</th>
      <th>event_name</th>
      <th>number_of_finishers</th>
      <th>athlete_id</th>
      <th>athlete_age</th>
      <th>athlete_performance</th>
      <th>athlete_average_speed</th>
    </tr>
    <tr>
      <th>race_length</th>
      <th>athlete_gender</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th rowspan="3" valign="top">50km</th>
      <th>F</th>
      <td>17103</td>
      <td>17103</td>
      <td>17103</td>
      <td>17103</td>
      <td>17103</td>
      <td>17103</td>
      <td>17103</td>
    </tr>
    <tr>
      <th>M</th>
      <td>31065</td>
      <td>31065</td>
      <td>31065</td>
      <td>31065</td>
      <td>31065</td>
      <td>31065</td>
      <td>31065</td>
    </tr>
    <tr>
      <th>X</th>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
    </tr>
    <tr>
      <th rowspan="3" valign="top">50mi</th>
      <th>F</th>
      <td>4729</td>
      <td>4729</td>
      <td>4729</td>
      <td>4729</td>
      <td>4729</td>
      <td>4729</td>
      <td>4729</td>
    </tr>
    <tr>
      <th>M</th>
      <td>10824</td>
      <td>10824</td>
      <td>10824</td>
      <td>10824</td>
      <td>10824</td>
      <td>10824</td>
      <td>10824</td>
    </tr>
    <tr>
      <th>X</th>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
sns.histplot(df3["race_length"])
```




    <Axes: xlabel='race_length', ylabel='Count'>




    
![png](output_57_1.png)
    



```python
sns.histplot(df3, x = 'race_length', hue = 'athlete_gender')
```




    <Axes: xlabel='race_length', ylabel='Count'>




    
![png](output_58_1.png)
    



```python
sns.displot(df3[df3['race_length'] == "50mi"]['athlete_average_speed'])
```




    <seaborn.axisgrid.FacetGrid at 0x1fb716acd10>




    
![png](output_59_1.png)
    



```python
sns.violinplot(data=df3, x='race_length', y='athlete_average_speed', hue='athlete_gender', split=True, inner= "quart", linewidth = 1)
```




    <Axes: xlabel='race_length', ylabel='athlete_average_speed'>




    
![png](output_60_1.png)
    



```python
sns.lmplot(data=df3, x='athlete_age', y='athlete_average_speed', hue='athlete_gender')
```




    <seaborn.axisgrid.FacetGrid at 0x1fb918bd070>




    
![png](output_61_1.png)
    



```python
#questions I want to find out from the data
```


```python
#Difference in speed in 50km & 50mi from male to female to X
```


```python
df3.groupby("athlete_gender")["athlete_average_speed"].mean()
```




    athlete_gender
    F    6.959843
    M    7.569282
    X    7.628333
    Name: athlete_average_speed, dtype: float64




```python
#What age group is the best in the 50km race (more than 20 races)
```


```python
df3.query('race_length == "50km"').groupby("athlete_age")["athlete_average_speed"].agg(["mean","count"]).sort_values("mean", ascending =False).query('count>20')
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>mean</th>
      <th>count</th>
    </tr>
    <tr>
      <th>athlete_age</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>20</th>
      <td>8.110445</td>
      <td>155</td>
    </tr>
    <tr>
      <th>23</th>
      <td>8.003496</td>
      <td>379</td>
    </tr>
    <tr>
      <th>27</th>
      <td>7.989370</td>
      <td>884</td>
    </tr>
    <tr>
      <th>24</th>
      <td>7.977480</td>
      <td>496</td>
    </tr>
    <tr>
      <th>22</th>
      <td>7.947148</td>
      <td>284</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>74</th>
      <td>6.229061</td>
      <td>33</td>
    </tr>
    <tr>
      <th>71</th>
      <td>6.021672</td>
      <td>58</td>
    </tr>
    <tr>
      <th>75</th>
      <td>5.904226</td>
      <td>31</td>
    </tr>
    <tr>
      <th>73</th>
      <td>5.796250</td>
      <td>32</td>
    </tr>
    <tr>
      <th>72</th>
      <td>5.710216</td>
      <td>37</td>
    </tr>
  </tbody>
</table>
<p>61 rows × 2 columns</p>
</div>




```python
#Season for the data -> Slower in summer than winter?

#Spring = 3-5
#Summer = 6-8
#Fall = 8-11
#Winter = 12-2
```


```python
df3["race_month"] = df3["race_day"].str.split(".").str.get(1).astype(int)
```


```python
df3.head(10)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>race_day</th>
      <th>event_name</th>
      <th>race_length</th>
      <th>number_of_finishers</th>
      <th>athlete_id</th>
      <th>athlete_gender</th>
      <th>athlete_age</th>
      <th>athlete_performance</th>
      <th>athlete_average_speed</th>
      <th>race_month</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>55</th>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>55</td>
      <td>M</td>
      <td>35</td>
      <td>9:53:05</td>
      <td>8.141</td>
      <td>1</td>
    </tr>
    <tr>
      <th>56</th>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>56</td>
      <td>F</td>
      <td>41</td>
      <td>11:09:35</td>
      <td>7.211</td>
      <td>1</td>
    </tr>
    <tr>
      <th>57</th>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>57</td>
      <td>M</td>
      <td>42</td>
      <td>11:33:00</td>
      <td>6.967</td>
      <td>1</td>
    </tr>
    <tr>
      <th>58</th>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>58</td>
      <td>M</td>
      <td>32</td>
      <td>11:38:17</td>
      <td>6.914</td>
      <td>1</td>
    </tr>
    <tr>
      <th>59</th>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>59</td>
      <td>M</td>
      <td>30</td>
      <td>11:56:35</td>
      <td>6.738</td>
      <td>1</td>
    </tr>
    <tr>
      <th>60</th>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>60</td>
      <td>M</td>
      <td>23</td>
      <td>12:32:16</td>
      <td>6.418</td>
      <td>1</td>
    </tr>
    <tr>
      <th>61</th>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>61</td>
      <td>M</td>
      <td>39</td>
      <td>12:39:36</td>
      <td>6.356</td>
      <td>1</td>
    </tr>
    <tr>
      <th>62</th>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>62</td>
      <td>F</td>
      <td>41</td>
      <td>12:39:36</td>
      <td>6.356</td>
      <td>1</td>
    </tr>
    <tr>
      <th>63</th>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>63</td>
      <td>F</td>
      <td>28</td>
      <td>13:24:05</td>
      <td>6.004</td>
      <td>1</td>
    </tr>
    <tr>
      <th>64</th>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 km Winter Challenge</td>
      <td>50km</td>
      <td>36</td>
      <td>64</td>
      <td>F</td>
      <td>27</td>
      <td>5:09:40</td>
      <td>9.688</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df3["race_month"] = df3["race_month"].apply(lambda x : 'Winter' if x>11 else 'Fall' if x>7 else 'Summer' if x>5 else 'Spring' if x>2 else 'Winter')
```


```python
df3.head(10)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>race_day</th>
      <th>event_name</th>
      <th>race_length</th>
      <th>number_of_finishers</th>
      <th>athlete_id</th>
      <th>athlete_gender</th>
      <th>athlete_age</th>
      <th>athlete_performance</th>
      <th>athlete_average_speed</th>
      <th>race_month</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>55</th>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>55</td>
      <td>M</td>
      <td>35</td>
      <td>9:53:05</td>
      <td>8.141</td>
      <td>Winter</td>
    </tr>
    <tr>
      <th>56</th>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>56</td>
      <td>F</td>
      <td>41</td>
      <td>11:09:35</td>
      <td>7.211</td>
      <td>Winter</td>
    </tr>
    <tr>
      <th>57</th>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>57</td>
      <td>M</td>
      <td>42</td>
      <td>11:33:00</td>
      <td>6.967</td>
      <td>Winter</td>
    </tr>
    <tr>
      <th>58</th>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>58</td>
      <td>M</td>
      <td>32</td>
      <td>11:38:17</td>
      <td>6.914</td>
      <td>Winter</td>
    </tr>
    <tr>
      <th>59</th>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>59</td>
      <td>M</td>
      <td>30</td>
      <td>11:56:35</td>
      <td>6.738</td>
      <td>Winter</td>
    </tr>
    <tr>
      <th>60</th>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>60</td>
      <td>M</td>
      <td>23</td>
      <td>12:32:16</td>
      <td>6.418</td>
      <td>Winter</td>
    </tr>
    <tr>
      <th>61</th>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>61</td>
      <td>M</td>
      <td>39</td>
      <td>12:39:36</td>
      <td>6.356</td>
      <td>Winter</td>
    </tr>
    <tr>
      <th>62</th>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>62</td>
      <td>F</td>
      <td>41</td>
      <td>12:39:36</td>
      <td>6.356</td>
      <td>Winter</td>
    </tr>
    <tr>
      <th>63</th>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 Mile Winter Challenge</td>
      <td>50mi</td>
      <td>9</td>
      <td>63</td>
      <td>F</td>
      <td>28</td>
      <td>13:24:05</td>
      <td>6.004</td>
      <td>Winter</td>
    </tr>
    <tr>
      <th>64</th>
      <td>06.01.2018</td>
      <td>Yankee Springs 50 km Winter Challenge</td>
      <td>50km</td>
      <td>36</td>
      <td>64</td>
      <td>F</td>
      <td>27</td>
      <td>5:09:40</td>
      <td>9.688</td>
      <td>Winter</td>
    </tr>
  </tbody>
</table>
</div>




```python
df3.groupby("race_month")['athlete_average_speed'].agg(['mean','count']).sort_values('mean', ascending = False)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>mean</th>
      <th>count</th>
    </tr>
    <tr>
      <th>race_month</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Spring</th>
      <td>7.486591</td>
      <td>20462</td>
    </tr>
    <tr>
      <th>Winter</th>
      <td>7.431837</td>
      <td>13409</td>
    </tr>
    <tr>
      <th>Fall</th>
      <td>7.276780</td>
      <td>20358</td>
    </tr>
    <tr>
      <th>Summer</th>
      <td>7.167459</td>
      <td>9495</td>
    </tr>
  </tbody>
</table>
</div>




```python
#50 milers only
```


```python
df3.query('race_length == "50mi"').groupby("race_month")['athlete_average_speed'].agg(['mean','count']).sort_values('mean', ascending = False)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>mean</th>
      <th>count</th>
    </tr>
    <tr>
      <th>race_month</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Fall</th>
      <td>7.319862</td>
      <td>4320</td>
    </tr>
    <tr>
      <th>Spring</th>
      <td>7.312843</td>
      <td>4836</td>
    </tr>
    <tr>
      <th>Summer</th>
      <td>6.953252</td>
      <td>3050</td>
    </tr>
    <tr>
      <th>Winter</th>
      <td>6.758153</td>
      <td>3348</td>
    </tr>
  </tbody>
</table>
</div>




```python

```
