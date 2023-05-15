# Air-Quality-Index
from cProfile import label
import pandas as pd

dataset = pd.read_csv(r"air_pollution2.csv", index_col='From Date')
a = dataset.replace("None", 0)
a.to_csv("air_pollution4.csv")
df = pd.read_csv("air_pollution4.csv", sep=",", parse_dates=['From Date'],
                 index_col='From Date')

b = df.resample('M').max()
print(b)
pm25 = list(b["PM2.5"].values)
pm25_19 = []
for i in pm25:
    if i <= 30:
        pm25_19.append(i * (50 / 30))
    elif (i > 30 and i <= 60):
        e = (50 / 30)
        pm25_19.append(50 + ((i - 30) * e))
    elif (i > 60 and i <= 90):
        e = (100 / 30)
        pm25_19.append(100 + ((i - 60) * e))
    elif (i > 90 and i <= 120):
        e = (100 / 30)
        pm25_19.append(200 + ((i - 90) * e))
    elif (i > 120 and i <= 250):
        e = (100 / 30)
        pm25_19.append(300 + ((i - 120) * e))
    elif (i > 250):
        e = (100 / 30)
        pm25_19.append(400 + ((i - 250) * e))

print(pm25_19)

pm10 = list(b["PM10"].values)
pm10_19 = []
for i in pm10:
    if i <= 100:
        pm10_19.append(i)
    elif (i > 100 and i <= 250):
        e = (100 / 150)
        pm10_19.append(100 + ((i - 100) * e))
    elif (i > 250 and i <= 350):
        pm10_19.append(i - 50)
    elif (i > 350 and i <= 430):
        e = (100 / 80)
        pm10_19.append(300 + ((i - 350) * e))
    elif i > 430:
        e = (100 / 80)
        pm10_19.append(400 + ((i - 430) * e))

print(pm10_19)

so2 = list(b["SO2"].values)
so2_19 = []
for i in so2:
    if i <= 40:
        so2_19.append(i * (50 / 40))
    elif (i > 40 and i <= 80):
        e = (50 / 40)
        so2_19.append(50 + ((i - 40) * e))
    elif (i > 80 and i <= 180):
        e = (100 / 100)
        so2_19.append(100 + ((i - 80) * e))
    elif (i > 180 and i <= 280):
        e = (100 / 100)
        so2_19.append(200 + ((i - 180) * e))
    elif (i > 280 and i <= 400):
        e = (100 / 120)
        so2_19.append(300 + ((i - 280) * e))
    elif (i > 400):
        e = (100 / 120)
        so2_19.append(400 + ((i - 400) * e))

print(so2_19)

no2 = list(b["NO2"].values)
no2_19 = []
for i in no2:
    if i <= 40:
        no2_19.append(i * (50 / 40))
    elif (i > 40 and i <= 80):
        e = (50 / 40)
        no2_19.append(50 + ((i - 40) * e))
    elif (i > 80 and i <= 380):
        e = (100 / 300)
        no2_19.append(100 + ((i - 80) * e))
    elif (i > 380 and i <= 800):
        e = (100 / 420)
        no2_19.append(200 + ((i - 380) * e))
    elif (i > 800 and i <= 1600):
        e = (100 / 800)
        no2_19.append(300 + ((i - 800) * e))
    elif (i > 1600):
        e = (100 / 800)
        no2_19.append(400 + ((i - 1600) * e))

print(no2_19)

co = list(b["CO"].values)
co_19 = []
for i in co:
    if i <= 1:
        co_19.append(i * (50 / 1))
    elif (i > 1 and i <= 2):
        co_19.append(50 + ((i - 1) * 50))
    elif (i > 2 and i <= 10):
        e = (100 / 8)
        co_19.append(100 + ((i - 2) * e))
    elif (i > 10 and i <= 17):
        e = (100 / 7)
        co_19.append(200 + ((i - 10) * e))
    elif (i > 17 and i <= 34):
        e = (100 / 17)
        co_19.append(300 + ((i - 17) * e))
    elif (i > 34):
        e = (100 / 17)
        co_19.append(400 + ((i - 34) * e))

print(co_19)
ozone = list(b["OZONE"].values)
ozone_19 = []
for i in ozone:
    if i <= 50:
        ozone_19.append(i * (50 / 50))
    elif (i > 50 and i <= 100):
        e = (50 / 50)
        ozone_19.append(50 + ((i - 50) * e))
    elif (i > 100 and i <= 168):
        e = (100 / 68)
        ozone_19.append(100 + ((i - 100) * e))
    elif (i > 168 and i <= 208):
        e = (100 / 40)
        ozone_19.append(200 + ((i - 168) * e))
    elif (i > 208 and i <= 748):
        e = (100 / 539)
        ozone_19.append(300 + ((i - 208) * e))
    elif (i > 748):
        e = (100 / 539)
        ozone_19.append(400 + ((i - 748) * e))

print(ozone_19)

dataset = pd.read_csv(r"air_pollution2020.csv", index_col='From Date')
d = dataset.replace("None", 0)
d.to_csv("air_pollution5.csv")
df = pd.read_csv("air_pollution5.csv", sep=",", parse_dates=['From Date'],
                 index_col='From Date')

c = df.resample('M').max()
print(c)

pm25 = list(c["PM2.5"].values)
pm25_20 = []
for i in pm25:
    if i <= 30:
        pm25_20.append(i * (50 / 30))
    elif (i > 30 and i <= 60):
        e = (50 / 30)
        pm25_20.append(50 + ((i - 30) * e))
    elif (i > 60 and i <= 90):
        e = (100 / 30)
        pm25_20.append(100 + ((i - 60) * e))
    elif (i > 90 and i <= 120):
        e = (100 / 30)
        pm25_20.append(200 + ((i - 90) * e))
    elif (i > 120 and i <= 250):
        e = (100 / 30)
        pm25_20.append(300 + ((i - 120) * e))
    elif (i > 250):
        e = (100 / 30)
        pm25_20.append(400 + ((i - 250) * e))

print(pm25_20)

pm10 = list(c["PM10"].values)
pm10_20 = []
for i in pm10:
    if i <= 100:
        pm10_20.append(i)
    elif (i > 100 and i <= 250):
        e = (100 / 150)
        pm10_20.append(100 + ((i - 100) * e))
    elif (i > 250 and i <= 350):
        pm10_20.append(i - 50)
    elif (i > 350 and i <= 430):
        e = (100 / 80)
        pm10_20.append(300 + ((i - 350) * e))
    elif i > 430:
        e = (100 / 80)
        pm10_20.append(400 + ((i - 430) * e))

print(pm10_20)

so2 = list(c["SO2"].values)
so2_20 = []
for i in so2:
    if i <= 40:
        so2_20.append(i * (50 / 40))
    elif (i > 40 and i <= 80):
        e = (50 / 40)
        so2_20.append(50 + ((i - 40) * e))
    elif (i > 80 and i <= 180):
        e = (100 / 100)
        so2_20.append(100 + ((i - 80) * e))
    elif (i > 180 and i <= 280):
        e = (100 / 100)
        so2_20.append(200 + ((i - 180) * e))
    elif (i > 280 and i <= 400):
        e = (100 / 120)
        so2_20.append(300 + ((i - 280) * e))
    elif (i > 400):
        e = (100 / 120)
        so2_20.append(400 + ((i - 400) * e))

print(so2_20)

no2 = list(c["NO2"].values)
no2_20 = []
for i in no2:
    if i <= 40:
        no2_20.append(i * (50 / 40))
    elif (i > 40 and i <= 80):
        e = (50 / 40)
        no2_20.append(50 + ((i - 40) * e))
    elif (i > 80 and i <= 380):
        e = (100 / 300)
        no2_20.append(100 + ((i - 80) * e))
    elif (i > 380 and i <= 800):
        e = (100 / 420)
        no2_20.append(200 + ((i - 380) * e))
    elif (i > 800 and i <= 1600):
        e = (100 / 800)
        no2_20.append(300 + ((i - 800) * e))
    elif (i > 1600):
        e = (100 / 800)
        no2_20.append(400 + ((i - 1600) * e))

print(no2_20)

co = list(c["CO"].values)
co_20 = []
for i in co:
    if i <= 1:
        co_20.append(i * (50 / 1))
    elif (i > 1 and i <= 2):
        co_20.append(50 + ((i - 1) * 50))
    elif (i > 2 and i <= 10):
        e = (100 / 8)
        co_20.append(100 + ((i - 2) * e))
    elif (i > 10 and i <= 17):
        e = (100 / 7)
        co_20.append(200 + ((i - 10) * e))
    elif (i > 17 and i <= 34):
        e = (100 / 17)
        co_20.append(300 + ((i - 17) * e))
    elif (i > 34):
        e = (100 / 17)
        co_20.append(400 + ((i - 34) * e))

print(co_20)
ozone = list(c["OZONE"].values)
ozone_20 = []

for i in ozone:
    if i <= 50:
        ozone_20.append(i * (50 / 50))
    elif (i > 50 and i <= 100):
        e = (50 / 50)
        ozone_20.append(50 + ((i - 50) * e))
    elif (i > 100 and i <= 168):
        e = (100 / 68)
        ozone_20.append(100 + ((i - 100) * e))
    elif (i > 168 and i <= 208):
        e = (100 / 40)
        ozone_20.append(200 + ((i - 168) * e))
    elif (i > 208 and i <= 748):
        e = (100 / 539)
        ozone_20.append(300 + ((i - 208) * e))
    elif (i > 748):
        e = (100 / 539)
        ozone_20.append(400 + ((i - 748) * e))

print(ozone_20)

import numpy as np

l = ["01-31", "02-29", "03-31", "04-30", "05-31", "06-30", "07-31", "08-31", "09-30", "10-31", "11-30", "12-31"]
date = np.array(l)
print(date)

import seaborn as sb
import matplotlib.pyplot as mp

mp.subplot(2, 3, 1)
mp.xlabel("VALUES", fontsize=15)
mp.ylabel("DATES", fontsize=15)
mp.title("CONCENTRATION OF PM2.5", fontsize=15)
mp.scatter(np.array(pm25_19), date, label="pm2.5(2019)")
mp.scatter(np.array(pm25_20), date, label="pm2.5(2020)")
mp.legend(["PM2.5(2019)", "PM2.5(2020)"])

mp.subplot(2, 3, 2)
mp.xlabel("VALUES", fontsize=15)
mp.ylabel("DATES", fontsize=15)
mp.title("CONCENTRATION OF PM10", fontsize=15)
mp.scatter(np.array(pm10_19), date, label="pm10(2019)")
mp.scatter(np.array(pm10_20), date, label="pm10(2020)")
mp.legend(["PM10(2019)", "PM10(2020)"])

mp.subplot(2, 3, 3)
mp.xlabel("VALUES", fontsize=15)
mp.ylabel("DATES", fontsize=15)
mp.title("CONCENTRATION OF SO2", fontsize=15)
sb.scatterplot(np.array(so2_19), date, label="so2(2019)")
sb.scatterplot(np.array(so2_20), date, label="so2(2020)")
mp.legend(["SO2(2019)", "SO2(2020)"])

mp.subplot(2, 3, 4)
mp.xlabel("VALUES", fontsize=15)
mp.ylabel("DATES", fontsize=15)
mp.title("CONCENTRATION OF NO2", fontsize=15)
mp.scatter(np.array(no2_19), date, label="NO2(2019)")
mp.scatter(np.array(no2_20), date, label="NO2(2020)")
mp.legend(["NO2(2019)", "NO2(2020)"])

mp.subplot(2, 3, 5)
mp.xlabel("VALUES", fontsize=15)
mp.ylabel("DATES", fontsize=15)
mp.title("CONCENTRATION OF CO", fontsize=15)
mp.scatter(np.array(co_19), date, label="CO(2019)")
mp.scatter(np.array(co_20), date, label="CO(2020)", )
mp.legend(["CO(2019)", "CO(2020)"])

mp.xlabel("VALUES", fontsize=15)
mp.ylabel("DATES", fontsize=15)
mp.subplot(2, 3, 6)
mp.title("CONCENTRATION OF ozone", fontsize=15)
mp.scatter(np.array(ozone_20), date, label="OZONE(2019)")
mp.scatter(np.array(ozone_20), date, label="OZONE(2020)")
mp.legend(["OZONE(2019)", "OZONE(2020)"])

mp.show()
sb.pairplot(c)
mp.show()

sb.pairplot(b)
mp.show()

date2 = c.index.values
# for 2019 data
pm25 = {"PM2.5 after using formula": pm25_19}
f1 = pd.DataFrame(pm25)

pm10 = {"PM10 after using formula": pm10_19}
f2 = pd.DataFrame(pm10)

no2 = {"NO2 after using formula": no2_19}
f3 = pd.DataFrame(no2)

so2 = {"SO2 after using formula": so2_19}
f4 = pd.DataFrame(so2)

co = {"CO after using formula": co_19}
f5 = pd.DataFrame(co)

ozone = {"CO after using formula": ozone_19}
f6 = pd.DataFrame(ozone)

date1 = {"date": list(date2)}

f = pd.DataFrame(date1)
u = pd.concat([f, f1, f2, f3, f4, f5, f6], axis=1)

u.to_csv("air_pollution12.csv")

# for 2020 data
date3 = b.index.values

pm25 = {"PM2.5 after using formula": pm25_20}
f1 = pd.DataFrame(pm25)

pm10 = {"PM10 after using formula": pm10_20}
f2 = pd.DataFrame(pm10)

no2 = {"NO2 after using formula": no2_20}
f3 = pd.DataFrame(no2)

so2 = {"SO2 after using formula": so2_20}
f4 = pd.DataFrame(so2)

co = {"CO after using formula": co_20}
f5 = pd.DataFrame(co)

ozone = {"CO after using formula": ozone_20}
f6 = pd.DataFrame(f6)

date1 = {"date for 2020": list(date3)}

f = pd.DataFrame(date1)
u = pd.concat([f, f1, f2, f3, f4, f5, f6], axis=1)

u.to_csv("air_pollution13.csv")
