# TUGAS-AKHIR-PEMOS-TEAM-18
Repository ini dibuat sebagai pemenuhan tugas akhir Praktikum Pemodelan Oseanografi 2022. Repository ini berisi script dan hasil pemodelan adveksi-difusi 1D dan 2D serta model hidrodinamika 1D dan 2D yang dilakukan selama keberlangsungan praktikum sebagai penyelesaian dari suatu fenomena atau dinamika oseanografi. Pengerjaan repository ini dilakukan menggunakan bahasa pemrograman Phyton yang dapat dilakukan pada beberapa Text Editor seperti Google Colaboratory, Jupyter Notebook, dan Micorsoft VS Code. Adapun library yang digunakan antara lain Numpy, Matplotlib dan Siphon. Seluruh script yang ada merupakan hasil dari Team 18 Oseanografi 2020. Terima kasih semoga bermanfaat untuk kalian.


# I. AUTHORS TEAM 18
1. Raihan Anandra Rahmansyah_26050120140041_B
2. Zalfa Apricia Durotunasha_26050120140133_B
3. Zufar Tsaqiful Aryan_26050120140073_B
4. Audrya Indra Wardana_26050120140162_B
5. Raihan Fadhil Budi Saputra_26050120130055_A
6. Luthfan Nurcahyo Wibowo_26050120140125_B


# II. TEORI DASAR
## 1. Adveksi-Difusi 1D

Adveksi merupakan proses terjadinya pergerakan partikel fluida akibat adanya aliran. Adveksi adalah mekanisme perpindahan massa suatu materi dari satu titik ke titik lainnya. Sedangkan Difusi adalah proses perpindahan panas berupa rambatan dari air dengan temperatur tinggi keair dengan temperatur yang lebih rendah. Persamaan adveksi 1 dimensi dapat ditulis sebagai berikut :

Adveksi 1D

![image](https://user-images.githubusercontent.com/105978081/169934857-2f9e56ee-f474-46e2-b9d6-f8e7a32e28fb.png)

Difusi merupakan proses pergerakan partikel dari daerah yang memiliki konsentrasi tinggi ke konsentrasi rendah dan adanya perubahan konsentrasi.

Difusi 1D

![image](https://user-images.githubusercontent.com/105978081/169934909-8260ce62-0e54-429b-b1f4-e149c9ad0f2f.png)

Persamaan Adveksi-Difusi 1D

![image](https://user-images.githubusercontent.com/105978081/169935138-03f92c49-9edb-421f-9569-ed4e2eb8daff.png)

Diskritisasi Persamaan Model Adveksi-Difusi 1D

Untuk u>0
![image](https://user-images.githubusercontent.com/105978081/169936328-60d2f208-e4b1-45de-ba27-3a8fec86534c.png)

Untuk u<0
![image](https://user-images.githubusercontent.com/105978081/169936374-86b340c0-f40f-40cf-8e22-ec4255849f2e.png)

-----------------------------------------------------------------

Beberapa metode pada Adveksi-Difusi 1D

**a. FTCS**

Pendekatan beda maju terhadap waktu dan beda tengah terhadap ruang. Solusi FTCS termasuk ke dalam solusi stabil bersyarat dengan syarat kestabilan.

**b. _LEAPFROG_ (FTCS)**

_Leapfrog_ merupakan perluasan dari beda tengah terhadap ruang dan waktu. 

**c. _UPSTREAM_ (FTFS)**

Upstream menggunakan pendekatan beda maju untuk waktu sedangkan untuk turunan terhadap ruang dilakukan dengan melihat arah kecepatan u. Jika u>0 maka digunakan beda mundur dan jika u<0 maka digunakan beda maju. Stabilitas sama dengan leapfrog.

## 2. Adveksi-Difusi 2D

Adveksi merupakan mekanisme perpindahan suatu massa atau materi dari satu titik ke titik lainnya dalam satu horizontal akibat adanya aliran maupun perbedaan tekanan. Sedangkan difusi merupakan mekanisme penyebaran suatu materi akibat adanya kecepatan aliran dan perbedaan konsentrasi suatu materi. Adapun persamaan adveksi dan difusi 2D adalah sebagai berikut:

Persamaan Adveksi 2D

![image](https://user-images.githubusercontent.com/105978081/169935765-a6985f9d-7316-46b0-96f0-628307242b2f.png)

Persamaan Difusi 2D

![image](https://user-images.githubusercontent.com/105978081/169935818-6fd128fc-40e5-4080-a870-b095f0a1b052.png)

Persamaan Diskritisasi Adveksi-Difusi 2D

![image](https://user-images.githubusercontent.com/105978081/169935943-11eb1857-02c4-4675-aaff-973e8f237905.png)

![image](https://user-images.githubusercontent.com/106065813/170073910-1a241a61-c67f-49e4-901d-c8d100635a92.png)

![image](https://user-images.githubusercontent.com/106065813/170074013-dfc4618f-84eb-4376-8a55-839d755e2764.png)

Pada nilai C=0 dan ad=1, terlihat bahwa polutan tidak bergerak. Hal itu ditunjukkan dengan gambar pertama dengan running model ke-5 dan gambar kedua adalah running model ke-210. Hal diatas dapat terjadi karena nilai C adalah 0 dimana nilai C dapat menentukan terjadinya pergerakan.

![image](https://user-images.githubusercontent.com/106065813/170074137-01cb789b-389d-4cc2-b050-fdd5f1bb330e.png)

![image](https://user-images.githubusercontent.com/106065813/170074238-bb0a6005-21e6-4999-aacf-148e4bd81912.png)

Pada nilai C=1 dan ad=0, terlihat bahwa polutan tidak bergerak. Hal itu ditunjukkan dengan gambar pertama dengan running model ke-5 dan gambar kedua adalah running model ke-210. Berbeda dari soal diatas, dalam kasus ini nilai C=1 sedangkan nilai ad=0. Nilai C akan mempengaruhi pergerakan dari polutan, sedangkan arah pergerakan akan ditentukan oleh nilai theta . Dari gambar diatas, nilai theta yang dipakai yaitu scenario 4 sebesar 373.

## 3. Hidrodinamika 1D

Model Hidrodinamika 1D dibangun dari adanya proses-proses yang mempengaruhi pergerakan massa air. Model ini juga dibangun berdasarkan hukum kontinuitas dan hukum momentum :

![image](https://user-images.githubusercontent.com/105978081/169936974-9e2318ad-5d86-4883-91a2-63e4b85658b4.png)  untuk momentum, dan

![image](https://user-images.githubusercontent.com/105978081/169937164-a3206f2a-87ab-4b37-a2da-1bc0698701be.png)  untuk kontinuitas

Selain itu, model hidrodinamika 1D ini memiliki persamaan pembangun sebagai berikut :

![image](https://user-images.githubusercontent.com/105978081/169935437-29706918-c617-471b-a78f-996bb8a0daab.png)

## 4. Hidrodinamika 2D



# III. SCRIPT DAN HASIL MODEL

## Modul 2 Adveksi Difusi 2D
```
import matplotlib.pyplot as plt
import numpy as np
import sys

def percentage(part, whole):
    percentage = 100 * float(part)/float(whole)
    return str(round(percentage,2)) + "x"

#Masukan Parameter Awal
C = 1.14
ad = 1.14

#Arah Arus
theta = 14
#theta = 74
#theta = 149
#theta = 329

#Parameter Lanjutan
q = 0.95 
x = 500 
y = 500 
dt = 0.5 
dx = 5 
dy = 5 

#Lama Simulasi
Tend = 101
#Tend = 0,5
dt = 0.5

#Polutan
px = 250
py = 231
Ic = 1014

#Perhitungan U dan V
u = C * np.sin(theta*np.pi/180)
v = C * np.cos(theta*np.pi/180)
dt_count = 1/((abs(u)/(q*dx))+(abs(v)/(q*dy))+(2*ad/(q*dx**2))+(2*ad/(q*dy*2)))

Nx = int(x/dx)  #number of mesh in x direction
Ny = int(y/dy)  #number of mesh in y direction
Nt = int(Tend/dt)

#perhitungan titik polutan di buang
px1 = int(px/dx)
py1 = int(py/dy)

#fungsi disederhanakan
lx = u*dt/dx
ly = v*dt/dy
ax = ad*dt/dx**2
ay = ad*dt/dy**2
cfl = (2*ax + 2*ay + abs(lx) + abs(ly))  #syarat kestabilan CFL

#perhitungan cfl
if cfl >= q:
    print('CFL Violated, please use dt :'+str(round(dt_count,4)))
    sys.exit ()
#%%

#pembuatan grid 
x_grid = np.linspace(0-dx, x+dx, Nx+2) #ghostnode boundary
y_grid = np.linspace(0-dx, y+dy, Ny+2) #ghostnode boundary
t = np.linspace(0, Tend, Nt+1)
x_mesh, y_mesh = np.meshgrid(x_grid,y_grid)
F = np.zeros((Nt+1, Ny+2, Nx+2))

#kondisi awal
F[0,py1,px1]=Ic
#%%

#Iterasi
for n in range (0, Nt):
    for i in range (1,Ny+1):
        for j in range (1, Nx+1):
         F[n+1,i,j]=((F[n,i,j]*(1-abs(lx)-abs(ly))) + \
                (0.5*(F[n,i-1,j]*(ly+abs(ly)))) + \
                (0.5*(F[n,i+1,j]*(abs(ly)-ly))) + \
                (0.5*(F[n,i,j-1]*(lx+abs(lx)))) + \
                (0.5*(F[n,i,j+1]*(abs(lx)-lx))) + \
                (ay*(F[n,i+1,j]-2*(F[n,i,j])+F[n,i-1,j])) +\
                (ax*(F[n,i,j+1]-2*(F[n,i,j])+F[n,i,j-1])))
    #syarat batas
    F[n+1,0,:] = 0 #bc bawah
    F[n+1,:,0] = 0 #bc kiri
    F[n+1,Ny+1,:] = 0 #bc atas
    F[n+1,:,Nx+1] = 0 #bc kanan
#%%

    #Output Gambar
    plt.clf()
    plt.pcolor(x_mesh, y_mesh, F[n+1, :, :], cmap = 'jet',shading='auto',edgecolor='k')
    cbar=plt.colorbar(orientation='vertical',shrink=0.95,extend='both')
    plt.clf()
    plt.pcolor(x_mesh,y_mesh,F[n+1,:,:],cmap='jet',shading='auto',edgecolor='k')
    cbar = plt.colorbar(orientation='vertical',shrink=0.95,extend='both')
    cbar.set_label(label='Concentration',size = 8)
    #plt.clim(0,100)
    plt.title('Kelompok 18 \n t='+str(round(dt*(n+1),3))+ ', Initial condition='+str(Ic),fontsize=10)
    plt.xlabel('x_grid',fontsize=9)
    plt.ylabel('y_grid',fontsize=9)
    plt.axis([0, x, 0, y])
    #plt.pause(0.01)
    plt.savefig(str(n+1)+'.jpg', dpi=300)
    plt.pause(0.01)
    plt.close()
    print('running timestep ke:' +str(n+1) + ' dari:' +str(Nt) + '('+ percentage(n+1,Nt)+')')
    print('Nilai CFL:' +str(cfl) + 'dengan arah: ' +str(theta))

```

## Modul 3 Pemodelan Hidrodinamika 1D
```
import matplotlib.pyplot as plt
import numpy as np

#Proses Awal

p = 5000 #Panjang grid
t = 1200 #Waktu simulasi
A = 0.5 #Amplitudo
D = 15 #Kedalaman
dt = 2
dx = 100 #Periode
To = 300

g = 9.8
pi = np.pi
C = np.sqrt(g*D) #Kecepatan arus
s = 2*pi/To #Kecepatan sudut gelombang
L = C*To #Panjang gelombang
k = 2*pi/L #Koefisien panjang gelombang
Mmax = int(p//dx)
Nmax = int(t//dt)

zo = [None for _ in range(Mmax)]
uo = [None for _ in range(Mmax)]

hasilu = [None for _ in range(Nmax)]
hasilz = [None for _ in range(Nmax)]

for i in range(1, Mmax+1):
  zo[i-1] = A*np.cos(k*(i)*dx)
  uo[i-1] = A*C*np.cos(k*((i)*dx+(0.5)*dx))/(D+zo[i-1])
for i in range(1, Nmax+1):
  zb = [None for _ in range(Mmax)]
  ub = [None for _ in range(Mmax)]
  zb[0] = A*np.cos(s*(i)*dt)
  ub[-1] = A*C*np.cos(k*L-s*(i)*dt)/(D+zo[-1])
  for j in range(1, Mmax):
    ub[j-1] = uo[j-1]-g*(dt/dx)*(zo[j]-zo[j-1])
  for k in range(2, Mmax+1):
    zb[k-1] = zo[k-1]-(D+zo[k-1])*(dt/dx)*(ub[k-1]-ub[k-2])
    hasilu[i-1] = ub
    hasilz[i-1] = zb
  for p in range(0, Mmax):
    uo[p] = ub[p]
    zo[p] = zb[p]

#Pembuatan grafik

def rand_col_hex_string():
  return f'#{format(np.random.randint(0,16777215), "#08x")[2:]}'

hasilu_np = np.array(hasilu)
hasilz_np = np.array(hasilz)

fig0, ax0 = plt.subplots(figsize=(12,8))
for i in range (1, 16):
  col0 = rand_col_hex_string()
  line, = ax0.plot(hasilu_np[:,i-1], c=col0, label=f'n={i}')
  ax0.legend()

  ax0.set(xlabel='Waktu', ylabel='Kecepatan Arus',
          title=''' Kelompok 18_Oseanografi 2020
          Perubahan Kecepatan Arus dalam Grid Tertentu di Sepanjang Waktu''')
  ax0.grid()

fig1, ax1 = plt.subplots(figsize=(12,8))
for i in range (1, 16):
  col1 = rand_col_hex_string()
  line, = ax1.plot(hasilz_np[:,i-1], c=col1, label=f'n={i}')
  ax1.legend()

  ax1.set(xlabel='Waktu', ylabel='Elevasi Muka Air',
          title=''' Zufar Tsaqiful Aryan_26050120140073
          Perubahan Elevasi Permukaan Air dalam Grid Tertentu di Sepanjang Waktu''')
  ax1.grid()

fig2, ax2 = plt.subplots(figsize=(12,8))
for i in range (1, 16):
  col2 = rand_col_hex_string()
  line, = ax2.plot(hasilu_np[i-1], c=col2, label=f't={i}')
  ax2.legend()

  ax2.set(xlabel='Grid', ylabel='Kecepatan Arus',
          title=''' Kelompok 18_Oseanografi 2020
          Perubahan Kecepatan Arus dalam Waktu Tertentu di Sepanjang Waktu''')
  ax2.grid()

fig3, ax3 = plt.subplots(figsize=(12,8))
for i in range (1, 16):
  col3 = rand_col_hex_string()
  line, = ax3.plot(hasilz_np[i-1], c=col3, label=f't={i}')
  ax3.legend()

  ax3.set(xlabel='Grid', ylabel='Elevasi Muka Air',
          title=''' Kelompok 18_Oseanografi 2020
          Perubahan Elevasi Permukaan Air dalam Waktu Tertentu di Sepanjang Waktu''')
  ax3.grid()

plt.show()
```

HASIL

![image](https://user-images.githubusercontent.com/106054022/169931383-d2843cc2-b4f0-4535-94b6-c9df86e2f2bc.png)
![image](https://user-images.githubusercontent.com/106054022/169931477-cb190429-4428-4407-b324-103b096431f5.png)
![image](https://user-images.githubusercontent.com/106054022/169931528-7e055d86-71de-4d07-8a2e-2f3fbc13a91c.png)
![image](https://user-images.githubusercontent.com/106054022/169931557-1bd22935-1c50-458f-981f-48926236065e.png)

## Modul 4 Model Hidrodinamika 2D
```
# Copyright (c) 2018 Siphon Contributors.
# Distributed under the terms of the BSD 3-Clause License.
# SPDX-License-Identifier: BSD-3-Clause
"""
NDBC Buoy Meteorogical Data Request
===================================
The NDBC keeps a 45-day recent rolling file for each buoy. This examples shows how to access 
the basic meteorological data from a buoy and make a simple plot.
"""

import matplotlib.pyplot as plt

from siphon.simplewebservice.ndbc import NDBC

#####################################################
# Get a pandas data frame of all of the observations, meteorological data is the default
# observation ser to query.
df = NDBC.realtime_observations('46014') #Station ID
df.head()

#####################################################
# Let's make a simple time series plot to checkout what the data look like.
fig, (ax1, ax2, ax3) = plt.subplots(3, 1, figsize=(12, 10))
ax2b = ax2.twinx()

# Pressure
ax1.plot(df['time'], df['pressure'], color='black')
ax1.set_ylabel('Pressure [hPa]')
fig.suptitle('Kelompok 18_Oseanografi 2020', fontsize=18)


# Wind speed, gust, direction
ax2.plot(df['time'], df['wind_speed'], color='tab:orange')
ax2.plot(df['time'], df['wind_gust'], color='tab:olive', linestyle='--')
ax2b.plot(df['time'], df['wind_direction'], color='tab:blue', linestyle='-')
ax2.set_ylabel('Wind Speed [m/s]')
ax2b.set_ylabel('Wind Direction')


# Water temperature
ax3.plot(df['time'], df['water_temperature'], color='tab:brown')
ax3.set_ylabel('Water Temperature [degC]')

plt.show()
```

HASIL

![image](https://user-images.githubusercontent.com/105978081/169940661-97aade09-7c97-4ce2-9dfb-260741b3f768.png)

# IV. PENERAPAN DALAM BIDANG OSEANOGRAFI
## Modul 1 Adveksi Difusi 1D
Persamaan model adveksi difusi 1D dapat digunakan dan diterapkan pada bidang oseanografi di antaranya dalam analisis perubahan konsentrasi polutan, pemodelan intrusi laut, pemodelan pergerakkan radionuklida, pemodelan sebaran nutrien, suhu permukaan laut dan salinitas hingga sebaran limbah. Metode ini memiliki skema hasil yang lebih konsisten. Selain itu, metode ini lebih mudah untuk penyelesaian pendekatan implisit dan lebih cepat untuk simulasi pendekatan eksplisit serta dapat memodelkan polutan sesuai stabilitas hitungan. Namun, metode ini tidak dapat menampilkan pergerakkan model berdasarkan arah.
## Modul 2 Adveksi Difusi 2D
Persamaan numerik adveksi difusi 2D dapat digunakan  untuk membuat scenario penyebaran konsentrasi polutan pada saat bulan kering atau basah. Penelitiannya dilakukan untuk menganalisis polutan sehingga kualitas air sungai dapat diketahui. Persamaan numerik tersebut dapat digunakan untuk melihat pergerakan polutan setiap waktu menggambarkan adanya penurunan konsentrasi polutan yang diakibatkan oleh adanya proses diffusi dari polutan yang terangkut oleh aliran air. Persamaan ini juga dapat digunakan dalam melakukan pemodelan air tanah, menghitung konsentrasi polutan pada pencemaran udara di lingkungan industri dan lain sebagainya.


# V. PENUTUP
Demikianlah tugas akhir praktikum pemodelan oseanografi 2022 ini kamu buat. Seluruh authors meminta maaf apabila masih terdapat banyak kekurangan dan kesalahan dalam pembuatan tugas akhir ini. Team 18 selaku authors dari tugas akhir ini mengucapkan terima kasih kepada:
1. Dr. Aris Ismanto, S.Si., M.Si. selaku dosen pengampu mata kuliah Pemodelan Oseanografi
2. Prof. Dr. Denny Nugroho Sugianto, S.T., M.Si. selaku dosen pengampu mata kuliah Pemodelan Oseanografi
3. Dr. Elis Indrayanti, S.T., M.Si. selaku dosen pengampu mata kuliah Pemodelan Oseanografi
4. Rikha Widiaratih, S.Si., M.Si. selaku dosen pengampu mata kuliah Pemodelan Oseanografi
5. Tim Asisten Praktikum Pemodelan Oseanografi 2022
6. Seluruh rekan-rekan Oseanografi 2020
