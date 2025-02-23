# Algoritma-Pemrograman
DS 04-02


# DIBAWAH INI TEMPLATE YAA

## EDA - Exploratory Data Analysis : menggunakan Python Function

- Exploratory Data Analysis (EDA) adalah proses awal dalam analisis data yang bertujuan untuk memahami distribusi, pola, hubungan antar variabel, serta mengidentifikasi anomali atau outliers dalam dataset melalui penggunaan teknik statistik dan visualisasi seperti histogram, scatter plot, dan heatmap, sehingga memberikan wawasan awal yang membantu dalam pengambilan keputusan untuk analisis lebih lanjut atau pemodelan. Dan juga kita manggunakan bahasa yang ada dibawah ini

![Python Logo](https://www.python.org/static/community_logos/python-logo.png)

## Daftar Isi
1. [Load Data](#load-data)
2. [Information About Dataset](#information-about-dataset)
3. [Cek Nilai Duplicate](#cek-nilai-duplicate)
4. [Vidualisasikan](#visualisasikan)
5. [Null Values](#null-values)
6. [Replace semua Null Values](#replace-semua-null-values )
7. [Mengetahui Tipe Data](#mengetahui-tipe-data)
8. [Filter Data](#filter-data)
9. [Boxplot](#boxplot)
10. [Correlation](#correlation)
---

## 1. Load Data
  Untuk Load data, file yang paling sering digunakan apalagi di kaggle.com adalah berformat csv. Jadi disini saya menggunakan kode untuk menampilkan data mmenggunakan format csv

### Contoh Kode
```python
df = pd.read_csv("C:/Users/ASUS/Documents/Untitled Folder/gold_price_yearly.csv")
df
```
<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Year</th>
      <th>Average Closing Price</th>
      <th>Year Open</th>
      <th>Year High</th>
      <th>Year Low</th>
      <th>Year Range Price</th>
      <th>Year Close</th>
      <th>Annual % Change</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1969</td>
      <td>41.10</td>
      <td>41.80</td>
      <td>43.75</td>
      <td>35.00</td>
      <td>8.75</td>
      <td>35.21</td>
      <td>-0.161</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1970</td>
      <td>35.96</td>
      <td>35.13</td>
      <td>39.19</td>
      <td>34.78</td>
      <td>4.41</td>
      <td>37.38</td>
      <td>0.062</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1971</td>
      <td>40.80</td>
      <td>37.33</td>
      <td>43.90</td>
      <td>37.33</td>
      <td>6.57</td>
      <td>43.50</td>
      <td>0.164</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1972</td>
      <td>58.17</td>
      <td>43.73</td>
      <td>70.00</td>
      <td>43.73</td>
      <td>26.27</td>
      <td>64.70</td>
      <td>0.487</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1973</td>
      <td>97.12</td>
      <td>64.99</td>
      <td>127.00</td>
      <td>64.10</td>
      <td>62.90</td>
      <td>112.25</td>
      <td>0.735</td>
    </tr>
    <tr>
      <th>5</th>
      <td>1974</td>
      <td>158.76</td>
      <td>114.75</td>
      <td>197.50</td>
      <td>114.75</td>
      <td>82.75</td>
      <td>187.50</td>
      <td>0.670</td>
    </tr>
    <tr>
      <th>6</th>
      <td>1975</td>
      <td>160.87</td>
      <td>185.00</td>
      <td>186.25</td>
      <td>128.75</td>
      <td>57.50</td>
      <td>140.25</td>
      <td>-0.252</td>
    </tr>
    <tr>
      <th>7</th>
      <td>1976</td>
      <td>124.80</td>
      <td>140.35</td>
      <td>140.35</td>
      <td>103.05</td>
      <td>37.30</td>
      <td>134.55</td>
      <td>-0.041</td>
    </tr>
    <tr>
      <th>8</th>
      <td>1977</td>
      <td>147.84</td>
      <td>136.10</td>
      <td>168.15</td>
      <td>129.40</td>
      <td>38.75</td>
      <td>165.60</td>
      <td>0.231</td>
    </tr>
    <tr>
      <th>9</th>
      <td>1978</td>
      <td>193.57</td>
      <td>168.60</td>
      <td>243.65</td>
      <td>166.30</td>
      <td>77.35</td>
      <td>224.50</td>
      <td>0.356</td>
    </tr>
    <tr>
      <th>10</th>
      <td>1979</td>
      <td>307.01</td>
      <td>227.15</td>
      <td>524.00</td>
      <td>216.55</td>
      <td>307.45</td>
      <td>524.00</td>
      <td>1.334</td>
    </tr>
    <tr>
      <th>11</th>
      <td>1980</td>
      <td>614.75</td>
      <td>559.00</td>
      <td>843.00</td>
      <td>474.00</td>
      <td>369.00</td>
      <td>589.50</td>
      <td>0.125</td>
    </tr>
    <tr>
      <th>12</th>
      <td>1981</td>
      <td>459.16</td>
      <td>592.00</td>
      <td>599.25</td>
      <td>391.75</td>
      <td>207.50</td>
      <td>400.00</td>
      <td>-0.322</td>
    </tr>
    <tr>
      <th>13</th>
      <td>1982</td>
      <td>376.11</td>
      <td>399.00</td>
      <td>488.50</td>
      <td>297.00</td>
      <td>191.50</td>
      <td>448.00</td>
      <td>0.120</td>
    </tr>
    <tr>
      <th>14</th>
      <td>1983</td>
      <td>423.71</td>
      <td>452.75</td>
      <td>511.50</td>
      <td>374.75</td>
      <td>136.75</td>
      <td>381.50</td>
      <td>-0.148</td>
    </tr>
    <tr>
      <th>15</th>
      <td>1984</td>
      <td>360.65</td>
      <td>384.00</td>
      <td>406.85</td>
      <td>303.25</td>
      <td>103.60</td>
      <td>309.00</td>
      <td>-0.190</td>
    </tr>
    <tr>
      <th>16</th>
      <td>1985</td>
      <td>317.42</td>
      <td>306.25</td>
      <td>339.30</td>
      <td>285.00</td>
      <td>54.30</td>
      <td>327.00</td>
      <td>0.058</td>
    </tr>
    <tr>
      <th>17</th>
      <td>1986</td>
      <td>368.20</td>
      <td>327.10</td>
      <td>442.75</td>
      <td>326.00</td>
      <td>116.75</td>
      <td>390.90</td>
      <td>0.195</td>
    </tr>
    <tr>
      <th>18</th>
      <td>1987</td>
      <td>446.84</td>
      <td>402.40</td>
      <td>502.75</td>
      <td>392.60</td>
      <td>110.15</td>
      <td>486.50</td>
      <td>0.245</td>
    </tr>
    <tr>
      <th>19</th>
      <td>1988</td>
      <td>436.78</td>
      <td>484.10</td>
      <td>485.30</td>
      <td>389.05</td>
      <td>96.25</td>
      <td>410.15</td>
      <td>-0.157</td>
    </tr>
    <tr>
      <th>20</th>
      <td>1989</td>
      <td>381.27</td>
      <td>413.60</td>
      <td>417.15</td>
      <td>358.10</td>
      <td>59.05</td>
      <td>401.00</td>
      <td>-0.022</td>
    </tr>
    <tr>
      <th>21</th>
      <td>1990</td>
      <td>383.73</td>
      <td>401.65</td>
      <td>421.40</td>
      <td>346.75</td>
      <td>74.65</td>
      <td>391.00</td>
      <td>-0.025</td>
    </tr>
    <tr>
      <th>22</th>
      <td>1991</td>
      <td>362.34</td>
      <td>392.50</td>
      <td>403.70</td>
      <td>343.50</td>
      <td>60.20</td>
      <td>353.40</td>
      <td>-0.096</td>
    </tr>
    <tr>
      <th>23</th>
      <td>1992</td>
      <td>343.87</td>
      <td>351.20</td>
      <td>359.30</td>
      <td>330.20</td>
      <td>29.10</td>
      <td>332.90</td>
      <td>-0.058</td>
    </tr>
    <tr>
      <th>24</th>
      <td>1993</td>
      <td>360.05</td>
      <td>329.40</td>
      <td>406.70</td>
      <td>326.50</td>
      <td>80.20</td>
      <td>390.65</td>
      <td>0.174</td>
    </tr>
    <tr>
      <th>25</th>
      <td>1994</td>
      <td>384.16</td>
      <td>395.00</td>
      <td>397.50</td>
      <td>370.25</td>
      <td>27.25</td>
      <td>382.50</td>
      <td>-0.021</td>
    </tr>
    <tr>
      <th>26</th>
      <td>1995</td>
      <td>384.07</td>
      <td>381.40</td>
      <td>396.95</td>
      <td>372.45</td>
      <td>24.50</td>
      <td>386.70</td>
      <td>0.011</td>
    </tr>
    <tr>
      <th>27</th>
      <td>1996</td>
      <td>387.73</td>
      <td>387.10</td>
      <td>416.25</td>
      <td>368.30</td>
      <td>47.95</td>
      <td>369.55</td>
      <td>-0.044</td>
    </tr>
    <tr>
      <th>28</th>
      <td>1997</td>
      <td>331.00</td>
      <td>367.80</td>
      <td>367.80</td>
      <td>283.05</td>
      <td>84.75</td>
      <td>289.20</td>
      <td>-0.217</td>
    </tr>
    <tr>
      <th>29</th>
      <td>1998</td>
      <td>294.12</td>
      <td>287.70</td>
      <td>314.60</td>
      <td>273.40</td>
      <td>41.20</td>
      <td>287.45</td>
      <td>-0.006</td>
    </tr>
    <tr>
      <th>30</th>
      <td>1999</td>
      <td>278.86</td>
      <td>288.25</td>
      <td>326.25</td>
      <td>252.90</td>
      <td>73.35</td>
      <td>290.85</td>
      <td>0.012</td>
    </tr>
    <tr>
      <th>31</th>
      <td>2000</td>
      <td>279.29</td>
      <td>282.05</td>
      <td>316.60</td>
      <td>263.80</td>
      <td>52.80</td>
      <td>272.65</td>
      <td>-0.063</td>
    </tr>
    <tr>
      <th>32</th>
      <td>2001</td>
      <td>271.19</td>
      <td>272.80</td>
      <td>292.85</td>
      <td>256.70</td>
      <td>36.15</td>
      <td>276.50</td>
      <td>0.014</td>
    </tr>
    <tr>
      <th>33</th>
      <td>2002</td>
      <td>310.08</td>
      <td>278.10</td>
      <td>348.50</td>
      <td>277.80</td>
      <td>70.70</td>
      <td>342.75</td>
      <td>0.240</td>
    </tr>
    <tr>
      <th>34</th>
      <td>2003</td>
      <td>363.83</td>
      <td>342.20</td>
      <td>417.25</td>
      <td>319.75</td>
      <td>97.50</td>
      <td>417.25</td>
      <td>0.217</td>
    </tr>
    <tr>
      <th>35</th>
      <td>2004</td>
      <td>409.53</td>
      <td>415.20</td>
      <td>455.75</td>
      <td>373.50</td>
      <td>82.25</td>
      <td>438.00</td>
      <td>0.050</td>
    </tr>
    <tr>
      <th>36</th>
      <td>2005</td>
      <td>444.99</td>
      <td>426.80</td>
      <td>537.50</td>
      <td>411.50</td>
      <td>126.00</td>
      <td>513.00</td>
      <td>0.171</td>
    </tr>
    <tr>
      <th>37</th>
      <td>2006</td>
      <td>604.34</td>
      <td>520.75</td>
      <td>725.75</td>
      <td>520.75</td>
      <td>205.00</td>
      <td>635.70</td>
      <td>0.239</td>
    </tr>
    <tr>
      <th>38</th>
      <td>2007</td>
      <td>696.43</td>
      <td>640.75</td>
      <td>841.75</td>
      <td>608.30</td>
      <td>233.45</td>
      <td>836.50</td>
      <td>0.316</td>
    </tr>
    <tr>
      <th>39</th>
      <td>2008</td>
      <td>872.37</td>
      <td>840.75</td>
      <td>1023.50</td>
      <td>692.50</td>
      <td>331.00</td>
      <td>865.00</td>
      <td>0.034</td>
    </tr>
    <tr>
      <th>40</th>
      <td>2009</td>
      <td>973.66</td>
      <td>869.75</td>
      <td>1218.25</td>
      <td>813.00</td>
      <td>405.25</td>
      <td>1104.00</td>
      <td>0.276</td>
    </tr>
    <tr>
      <th>41</th>
      <td>2010</td>
      <td>1226.66</td>
      <td>1113.00</td>
      <td>1426.00</td>
      <td>1052.25</td>
      <td>373.75</td>
      <td>1410.25</td>
      <td>0.277</td>
    </tr>
    <tr>
      <th>42</th>
      <td>2011</td>
      <td>1573.16</td>
      <td>1405.50</td>
      <td>1896.50</td>
      <td>1316.00</td>
      <td>580.50</td>
      <td>1574.50</td>
      <td>0.117</td>
    </tr>
    <tr>
      <th>43</th>
      <td>2012</td>
      <td>1668.86</td>
      <td>1590.00</td>
      <td>1790.00</td>
      <td>1537.50</td>
      <td>252.50</td>
      <td>1664.00</td>
      <td>0.057</td>
    </tr>
    <tr>
      <th>44</th>
      <td>2013</td>
      <td>1409.51</td>
      <td>1681.50</td>
      <td>1692.50</td>
      <td>1192.75</td>
      <td>499.75</td>
      <td>1201.50</td>
      <td>-0.278</td>
    </tr>
    <tr>
      <th>45</th>
      <td>2014</td>
      <td>1266.06</td>
      <td>1219.75</td>
      <td>1379.00</td>
      <td>1144.50</td>
      <td>234.50</td>
      <td>1199.25</td>
      <td>-0.002</td>
    </tr>
    <tr>
      <th>46</th>
      <td>2015</td>
      <td>1158.86</td>
      <td>1184.25</td>
      <td>1298.00</td>
      <td>1049.60</td>
      <td>248.40</td>
      <td>1060.20</td>
      <td>-0.116</td>
    </tr>
    <tr>
      <th>47</th>
      <td>2016</td>
      <td>1251.92</td>
      <td>1075.20</td>
      <td>1372.60</td>
      <td>1073.60</td>
      <td>299.00</td>
      <td>1151.70</td>
      <td>0.086</td>
    </tr>
    <tr>
      <th>48</th>
      <td>2017</td>
      <td>1260.39</td>
      <td>1162.00</td>
      <td>1351.20</td>
      <td>1162.00</td>
      <td>189.20</td>
      <td>1296.50</td>
      <td>0.126</td>
    </tr>
    <tr>
      <th>49</th>
      <td>2018</td>
      <td>1268.93</td>
      <td>1312.80</td>
      <td>1360.25</td>
      <td>1176.70</td>
      <td>183.55</td>
      <td>1281.65</td>
      <td>-0.012</td>
    </tr>
    <tr>
      <th>50</th>
      <td>2019</td>
      <td>1393.34</td>
      <td>1287.20</td>
      <td>1542.60</td>
      <td>1270.05</td>
      <td>272.55</td>
      <td>1523.00</td>
      <td>0.188</td>
    </tr>
    <tr>
      <th>51</th>
      <td>2020</td>
      <td>1773.73</td>
      <td>1520.55</td>
      <td>2058.40</td>
      <td>1472.35</td>
      <td>586.05</td>
      <td>1895.10</td>
      <td>0.244</td>
    </tr>
    <tr>
      <th>52</th>
      <td>2021</td>
      <td>1798.89</td>
      <td>1946.60</td>
      <td>1954.40</td>
      <td>1678.00</td>
      <td>276.40</td>
      <td>1828.60</td>
      <td>-0.035</td>
    </tr>
    <tr>
      <th>53</th>
      <td>2022</td>
      <td>1864.11</td>
      <td>1800.10</td>
      <td>2043.30</td>
      <td>1785.92</td>
      <td>257.38</td>
      <td>1985.00</td>
      <td>0.086</td>
    </tr>
  </tbody>
</table>
</div>

## 2. Information About Datasets
Ketika bekerja dengan dataset menggunakan pandas di Python, ada beberapa fungsi yang sangat berguna untuk mendapatkan gambaran umum tentang data dan strukturnya. Berikut adalah beberapa fungsi yang paling sering digunakan seperti df.head(), df.info(), dan lainnya:

### Contoh Kode
```python
df.head(5)
```
<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Year</th>
      <th>Average Closing Price</th>
      <th>Year Open</th>
      <th>Year High</th>
      <th>Year Low</th>
      <th>Year Range Price</th>
      <th>Year Close</th>
      <th>Annual % Change</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1969</td>
      <td>41.10</td>
      <td>41.80</td>
      <td>43.75</td>
      <td>35.00</td>
      <td>8.75</td>
      <td>35.21</td>
      <td>-0.161</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1970</td>
      <td>35.96</td>
      <td>35.13</td>
      <td>39.19</td>
      <td>34.78</td>
      <td>4.41</td>
      <td>37.38</td>
      <td>0.062</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1971</td>
      <td>40.80</td>
      <td>37.33</td>
      <td>43.90</td>
      <td>37.33</td>
      <td>6.57</td>
      <td>43.50</td>
      <td>0.164</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1972</td>
      <td>58.17</td>
      <td>43.73</td>
      <td>70.00</td>
      <td>43.73</td>
      <td>26.27</td>
      <td>64.70</td>
      <td>0.487</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1973</td>
      <td>97.12</td>
      <td>64.99</td>
      <td>127.00</td>
      <td>64.10</td>
      <td>62.90</td>
      <td>112.25</td>
      <td>0.735</td>
    </tr>
  </tbody>
</table>
</div>

```python
df.shape
```
(54, 8)
```python
df.info()
```
```
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 54 entries, 0 to 53
Data columns (total 8 columns):
 #   Column                 Non-Null Count  Dtype  
---  ------                 --------------  -----  
 0   Year                   54 non-null     int64  
 1   Average Closing Price  54 non-null     float64
 2   Year Open              54 non-null     float64
 3   Year High              54 non-null     float64
 4   Year Low               54 non-null     float64
 5   Year Range Price       54 non-null     float64
 6   Year Close             54 non-null     float64
 7   Annual % Change        54 non-null     float64
dtypes: float64(7), int64(1)
memory usage: 3.5 KB
```

```python
df.describe()
```
<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Year</th>
      <th>Average Closing Price</th>
      <th>Year Open</th>
      <th>Year High</th>
      <th>Year Low</th>
      <th>Year Range Price</th>
      <th>Year Close</th>
      <th>Annual % Change</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>54.000000</td>
      <td>54.000000</td>
      <td>54.000000</td>
      <td>54.000000</td>
      <td>54.000000</td>
      <td>54.000000</td>
      <td>54.000000</td>
      <td>54.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>1995.500000</td>
      <td>614.832407</td>
      <td>597.865370</td>
      <td>703.203519</td>
      <td>544.099259</td>
      <td>159.104259</td>
      <td>630.736852</td>
      <td>0.100944</td>
    </tr>
    <tr>
      <th>std</th>
      <td>15.732133</td>
      <td>522.134252</td>
      <td>507.545973</td>
      <td>585.269833</td>
      <td>469.351612</td>
      <td>144.733256</td>
      <td>532.327723</td>
      <td>0.269706</td>
    </tr>
    <tr>
      <th>min</th>
      <td>1969.000000</td>
      <td>35.960000</td>
      <td>35.130000</td>
      <td>39.190000</td>
      <td>34.780000</td>
      <td>4.410000</td>
      <td>35.210000</td>
      <td>-0.322000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>1982.250000</td>
      <td>297.342500</td>
      <td>283.462500</td>
      <td>329.512500</td>
      <td>266.200000</td>
      <td>55.100000</td>
      <td>289.612500</td>
      <td>-0.039500</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>1995.500000</td>
      <td>383.900000</td>
      <td>397.000000</td>
      <td>432.075000</td>
      <td>363.200000</td>
      <td>96.875000</td>
      <td>395.500000</td>
      <td>0.057500</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>2008.750000</td>
      <td>948.337500</td>
      <td>862.500000</td>
      <td>1169.562500</td>
      <td>782.875000</td>
      <td>244.925000</td>
      <td>1011.400000</td>
      <td>0.211500</td>
    </tr>
    <tr>
      <th>max</th>
      <td>2022.000000</td>
      <td>1864.110000</td>
      <td>1946.600000</td>
      <td>2058.400000</td>
      <td>1785.920000</td>
      <td>586.050000</td>
      <td>1985.000000</td>
      <td>1.334000</td>
    </tr>
  </tbody>
</table>
</div>

```python
df.columns
```
```
Index(['Year', 'Average Closing Price', 'Year Open', 'Year High', 'Year Low',
       'Year Range Price', 'Year Close', 'Annual % Change'],
      dtype='object')
```
```python
df.isnull().sum()
```
```
Year                     0
Average Closing Price    0
Year Open                0
Year High                0
Year Low                 0
Year Range Price         0
Year Close               0
Annual % Change          0
dtype: int64
```
```python
df.dtypes
```
```
Year                       int64
Average Closing Price    float64
Year Open                float64
Year High                float64
Year Low                 float64
Year Range Price         float64
Year Close               float64
Annual % Change          float64
dtype: object
```

## 3. Cek Nilai Duplicate
Di Python, ada beberapa cara untuk memeriksa nilai duplikat dalam sebuah daftar. Berikut adalah beberapa metode yang umum digunakan:

### Contoh Kode
```python
df.duplicated()
```
0       False
1       False
2       False
3       False
4       False
        ...  
3057    False
3058    False
3059    False
3060    False
3061    False
Length: 3062, dtype: bool
```python
df['Year'].unique()
```
array([1969, 1970, 1971, 1972, 1973, 1974, 1975, 1976, 1977, 1978, 1979,
       1980, 1981, 1982, 1983, 1984, 1985, 1986, 1987, 1988, 1989, 1990,
       1991, 1992, 1993, 1994, 1995, 1996, 1997, 1998, 1999, 2000, 2001,
       2002, 2003, 2004, 2005, 2006, 2007, 2008, 2009, 2010, 2011, 2012,
       2013, 2014, 2015, 2016, 2017, 2018, 2019, 2020, 2021, 2022],
      dtype=int64)
      
## 4. Visualisasikan
Kode yini menggunakan matplotlib untuk membuat visualisasi yang membandingkan dua dataset: Average Closing Price dan Annual % Change dari data yang berisi kolom Year, Average Closing Price, dan Annual % Change. Berikut adalah penjelasan dari setiap bagian kode:

### Contoh Kode
```python
import matplotlib.pyplot as plt
plt.figure(figsize=(10, 6))

plt.plot(df['Year'], df['Average Closing Price'], label='Average Closing Price', color='blue')

plt.plot(df['Year'], df['Annual % Change'], label='Annual % Change', color='green')

plt.title('Average Closing Price and Annual % Change Over Time')
plt.xlabel('Year')
plt.ylabel('Value')
plt.legend()

plt.grid(True)
plt.show()
```
![image](https://github.com/user-attachments/assets/bebb6625-11f0-4f71-94a3-e43596d55613)


## 5. Null Values
Null values atau missing values dalam data adalah entri yang tidak memiliki nilai (kosong) pada kolom tertentu. Di Python, khususnya saat bekerja dengan pustaka seperti pandas, null values sering diwakili dengan NaN (Not a Number) atau None. Nilai-nilai ini bisa muncul karena berbagai alasan, seperti data yang tidak lengkap, kesalahan dalam pengumpulan data, atau data yang tidak relevan pada kasus tertentu.

### Contoh Kode
```python
df.isnull().sum()
```
ini adalah cara untuk mencari sebuah null values atau missing values.

## 6. Replace semua Null Values
Jika ada null Values atau ada mmissing values bagaimana sih kita mengisi data tersebut.
beginilah contoh nya

### Contoh Kode
```python
df['Year Low'] = df['Year Low'].fillna('unknown')
```
ini permisalan jika ada salah satu data dari kolom year low mengalami Null Values.

## 7. Mengetahui Tipe Data
Tipe Data sangat penting untuk diperhatikan, karena tipe data mempengaruhi saat kita saat preprocessing data. Sebelumnya kita cek dulu menggunakan df.dtypes .

### Contoh Kode
```python
df.dtypes()
```
Lalu 
```python
df.describe(include='all')
```

## 8. Filter Data
Disini saya menampilkan 3 contoh kode pemfilterann Data 
yang pertama ada filter data year diatas sama dengan tahun 2000

### Contoh Kode
```python
df_fy = df[df['Year'] >= 2000]
df_fy
```
<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Year</th>
      <th>Average Closing Price</th>
      <th>Year Open</th>
      <th>Year High</th>
      <th>Year Low</th>
      <th>Year Range Price</th>
      <th>Year Close</th>
      <th>Annual % Change</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>31</th>
      <td>2000</td>
      <td>279.29</td>
      <td>282.05</td>
      <td>316.60</td>
      <td>263.80</td>
      <td>52.80</td>
      <td>272.65</td>
      <td>-0.063</td>
    </tr>
    <tr>
      <th>32</th>
      <td>2001</td>
      <td>271.19</td>
      <td>272.80</td>
      <td>292.85</td>
      <td>256.70</td>
      <td>36.15</td>
      <td>276.50</td>
      <td>0.014</td>
    </tr>
    <tr>
      <th>33</th>
      <td>2002</td>
      <td>310.08</td>
      <td>278.10</td>
      <td>348.50</td>
      <td>277.80</td>
      <td>70.70</td>
      <td>342.75</td>
      <td>0.240</td>
    </tr>
    <tr>
      <th>34</th>
      <td>2003</td>
      <td>363.83</td>
      <td>342.20</td>
      <td>417.25</td>
      <td>319.75</td>
      <td>97.50</td>
      <td>417.25</td>
      <td>0.217</td>
    </tr>
    <tr>
      <th>35</th>
      <td>2004</td>
      <td>409.53</td>
      <td>415.20</td>
      <td>455.75</td>
      <td>373.50</td>
      <td>82.25</td>
      <td>438.00</td>
      <td>0.050</td>
    </tr>
    <tr>
      <th>36</th>
      <td>2005</td>
      <td>444.99</td>
      <td>426.80</td>
      <td>537.50</td>
      <td>411.50</td>
      <td>126.00</td>
      <td>513.00</td>
      <td>0.171</td>
    </tr>
    <tr>
      <th>37</th>
      <td>2006</td>
      <td>604.34</td>
      <td>520.75</td>
      <td>725.75</td>
      <td>520.75</td>
      <td>205.00</td>
      <td>635.70</td>
      <td>0.239</td>
    </tr>
    <tr>
      <th>38</th>
      <td>2007</td>
      <td>696.43</td>
      <td>640.75</td>
      <td>841.75</td>
      <td>608.30</td>
      <td>233.45</td>
      <td>836.50</td>
      <td>0.316</td>
    </tr>
    <tr>
      <th>39</th>
      <td>2008</td>
      <td>872.37</td>
      <td>840.75</td>
      <td>1023.50</td>
      <td>692.50</td>
      <td>331.00</td>
      <td>865.00</td>
      <td>0.034</td>
    </tr>
    <tr>
      <th>40</th>
      <td>2009</td>
      <td>973.66</td>
      <td>869.75</td>
      <td>1218.25</td>
      <td>813.00</td>
      <td>405.25</td>
      <td>1104.00</td>
      <td>0.276</td>
    </tr>
    <tr>
      <th>41</th>
      <td>2010</td>
      <td>1226.66</td>
      <td>1113.00</td>
      <td>1426.00</td>
      <td>1052.25</td>
      <td>373.75</td>
      <td>1410.25</td>
      <td>0.277</td>
    </tr>
    <tr>
      <th>42</th>
      <td>2011</td>
      <td>1573.16</td>
      <td>1405.50</td>
      <td>1896.50</td>
      <td>1316.00</td>
      <td>580.50</td>
      <td>1574.50</td>
      <td>0.117</td>
    </tr>
    <tr>
      <th>43</th>
      <td>2012</td>
      <td>1668.86</td>
      <td>1590.00</td>
      <td>1790.00</td>
      <td>1537.50</td>
      <td>252.50</td>
      <td>1664.00</td>
      <td>0.057</td>
    </tr>
    <tr>
      <th>44</th>
      <td>2013</td>
      <td>1409.51</td>
      <td>1681.50</td>
      <td>1692.50</td>
      <td>1192.75</td>
      <td>499.75</td>
      <td>1201.50</td>
      <td>-0.278</td>
    </tr>
    <tr>
      <th>45</th>
      <td>2014</td>
      <td>1266.06</td>
      <td>1219.75</td>
      <td>1379.00</td>
      <td>1144.50</td>
      <td>234.50</td>
      <td>1199.25</td>
      <td>-0.002</td>
    </tr>
    <tr>
      <th>46</th>
      <td>2015</td>
      <td>1158.86</td>
      <td>1184.25</td>
      <td>1298.00</td>
      <td>1049.60</td>
      <td>248.40</td>
      <td>1060.20</td>
      <td>-0.116</td>
    </tr>
    <tr>
      <th>47</th>
      <td>2016</td>
      <td>1251.92</td>
      <td>1075.20</td>
      <td>1372.60</td>
      <td>1073.60</td>
      <td>299.00</td>
      <td>1151.70</td>
      <td>0.086</td>
    </tr>
    <tr>
      <th>48</th>
      <td>2017</td>
      <td>1260.39</td>
      <td>1162.00</td>
      <td>1351.20</td>
      <td>1162.00</td>
      <td>189.20</td>
      <td>1296.50</td>
      <td>0.126</td>
    </tr>
    <tr>
      <th>49</th>
      <td>2018</td>
      <td>1268.93</td>
      <td>1312.80</td>
      <td>1360.25</td>
      <td>1176.70</td>
      <td>183.55</td>
      <td>1281.65</td>
      <td>-0.012</td>
    </tr>
    <tr>
      <th>50</th>
      <td>2019</td>
      <td>1393.34</td>
      <td>1287.20</td>
      <td>1542.60</td>
      <td>1270.05</td>
      <td>272.55</td>
      <td>1523.00</td>
      <td>0.188</td>
    </tr>
    <tr>
      <th>51</th>
      <td>2020</td>
      <td>1773.73</td>
      <td>1520.55</td>
      <td>2058.40</td>
      <td>1472.35</td>
      <td>586.05</td>
      <td>1895.10</td>
      <td>0.244</td>
    </tr>
    <tr>
      <th>52</th>
      <td>2021</td>
      <td>1798.89</td>
      <td>1946.60</td>
      <td>1954.40</td>
      <td>1678.00</td>
      <td>276.40</td>
      <td>1828.60</td>
      <td>-0.035</td>
    </tr>
    <tr>
      <th>53</th>
      <td>2022</td>
      <td>1864.11</td>
      <td>1800.10</td>
      <td>2043.30</td>
      <td>1785.92</td>
      <td>257.38</td>
      <td>1985.00</td>
      <td>0.086</td>
    </tr>
  </tbody>
</table>
</div>

lalu yang kedua ada 
```python
df_fp = df[df['Average Closing Price'] > 1500]
df_fp
```
<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Year</th>
      <th>Average Closing Price</th>
      <th>Year Open</th>
      <th>Year High</th>
      <th>Year Low</th>
      <th>Year Range Price</th>
      <th>Year Close</th>
      <th>Annual % Change</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>42</th>
      <td>2011</td>
      <td>1573.16</td>
      <td>1405.50</td>
      <td>1896.5</td>
      <td>1316.00</td>
      <td>580.50</td>
      <td>1574.5</td>
      <td>0.117</td>
    </tr>
    <tr>
      <th>43</th>
      <td>2012</td>
      <td>1668.86</td>
      <td>1590.00</td>
      <td>1790.0</td>
      <td>1537.50</td>
      <td>252.50</td>
      <td>1664.0</td>
      <td>0.057</td>
    </tr>
    <tr>
      <th>51</th>
      <td>2020</td>
      <td>1773.73</td>
      <td>1520.55</td>
      <td>2058.4</td>
      <td>1472.35</td>
      <td>586.05</td>
      <td>1895.1</td>
      <td>0.244</td>
    </tr>
    <tr>
      <th>52</th>
      <td>2021</td>
      <td>1798.89</td>
      <td>1946.60</td>
      <td>1954.4</td>
      <td>1678.00</td>
      <td>276.40</td>
      <td>1828.6</td>
      <td>-0.035</td>
    </tr>
    <tr>
      <th>53</th>
      <td>2022</td>
      <td>1864.11</td>
      <td>1800.10</td>
      <td>2043.3</td>
      <td>1785.92</td>
      <td>257.38</td>
      <td>1985.0</td>
      <td>0.086</td>
    </tr>
  </tbody>
</table>
</div>

yang ketiga ada: 
```python
df_pc = df[df['Annual % Change'] > 0.5]
df_pc
```
<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Year</th>
      <th>Average Closing Price</th>
      <th>Year Open</th>
      <th>Year High</th>
      <th>Year Low</th>
      <th>Year Range Price</th>
      <th>Year Close</th>
      <th>Annual % Change</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>4</th>
      <td>1973</td>
      <td>97.12</td>
      <td>64.99</td>
      <td>127.0</td>
      <td>64.10</td>
      <td>62.90</td>
      <td>112.25</td>
      <td>0.735</td>
    </tr>
    <tr>
      <th>5</th>
      <td>1974</td>
      <td>158.76</td>
      <td>114.75</td>
      <td>197.5</td>
      <td>114.75</td>
      <td>82.75</td>
      <td>187.50</td>
      <td>0.670</td>
    </tr>
    <tr>
      <th>10</th>
      <td>1979</td>
      <td>307.01</td>
      <td>227.15</td>
      <td>524.0</td>
      <td>216.55</td>
      <td>307.45</td>
      <td>524.00</td>
      <td>1.334</td>
    </tr>
  </tbody>
</table>
</div>

## 9. Boxplot
Pengertian Boxplot:
Boxplot adalah grafik statistik yang menampilkan persebaran data berdasarkan kuartil. Grafik ini membantu mengidentifikasi outlier dan mengetahui penyebaran data.

**Kode Python untuk Boxplot:**

```python
import matplotlib.pyplot as plt

plt.figure(figsize=(10, 6))
plt.boxplot([df['Average Closing Price'], df['Annual % Change']], labels=['Average Closing Price', 'Annual % Change'])
plt.title('Boxplot of Average Closing Price and Annual % Change')
plt.ylabel('Values')
plt.show()
```
![image](https://github.com/user-attachments/assets/58cc9e99-1333-444e-b032-3befc84b4f0e)

- **Median** (Garis tengah kotak): Menunjukkan nilai tengah data.
- **Kotak**: Menunjukkan distribusi antara kuartil pertama (Q1) dan kuartil ketiga (Q3).
- **Whiskers**: Garis yang memperpanjang dari kotak, mewakili data yang tidak dianggap outlier.
    - **Panjang Whiskers Pendek**: Jika whiskers pendek, ini menunjukkan bahwa data memiliki sebaran yang sempit di luar kuartil, yang berarti sebagian besar nilai data terletak dekat dengan median.
    - **Panjang Whiskers Panjang:** Jika whiskers panjang, ini menunjukkan bahwa data memiliki sebaran yang lebih luas di luar kuartil, menunjukkan bahwa ada lebih banyak variasi atau nilai ekstrim di luar rentang yang normal.

- **Outlier**: Titik-titik di luar whiskers yang dianggap data ekstrem.

## 10. Correlation
Korelasi dalam konteks analisis data mengukur sejauh mana dua variabel memiliki hubungan linear. Dalam Python, korelasi sering digunakan untuk menentukan apakah ada hubungan antara dua fitur atau variabel dalam dataset, serta kekuatan dan arah hubungan tersebut.

### Contoh Kode
```python
correlation = df[['Average Closing Price', 'Annual % Change']].corr()
correlation
```
<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Average Closing Price</th>
      <th>Annual % Change</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Average Closing Price</th>
      <td>1.00000</td>
      <td>-0.10327</td>
    </tr>
    <tr>
      <th>Annual % Change</th>
      <td>-0.10327</td>
      <td>1.00000</td>
    </tr>
  </tbody>
</table>
</div>

ini untuk table heatmap
```python
import seaborn as sns
plt.figure(figsize=(8, 6))  # Set the size of the plot
sns.heatmap(correlation, annot=True, cmap="coolwarm", fmt=".2f")
plt.title("Correlation Heatmap")
plt.show()
```
![image](https://github.com/user-attachments/assets/dc97e201-bd7f-4379-94dc-4e0d9c372a1e)
