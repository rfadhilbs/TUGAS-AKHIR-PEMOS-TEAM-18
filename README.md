# TUGAS-AKHIR-PEMOS-TEAM-18
Repository ini dibuat sebagai pemenuhan tugas akhir Praktikum Pemodelan Oseanografi 2022. Repository ini berisi script dan hasil pemodelan adveksi-difusi 1D dan 2D serta model hidrodinamika 1D dan 2D yang dilakukan selama keberlangsungan praktikum sebagai penyelesaian dari suatu fenomena atau dinamika oseanografi. Pengerjaan repository ini dilakukan menggunakan bahasa pemrograman Phyton yang dapat dilakukan pada beberapa Text Editor seperti Google Colaboratory, Jupyter Notebook, dan Micorsoft VS Code. Adapun library yang digunakan antara lain Numpy, Matplotlib dan Siphon. Seluruh script yang ada merupakan hasil dari Team 18 Oseanografi 2020. Terima kasih semoga bermanfaat.


# I. AUTHORS TEAM 18
1. Raihan Anandra Rahmansyah_26050120140041_B
2. Zalfa Apricia Durotunasha_26050120140133_B
3. Zufar Tsaqiful Aryan
4. Audrya Indra Wardana_26050120140162_B
5. Raihan Fadhil Budi Saputra_26050120130055_A
6. Luthfan Nurcahyo Wibowo


# II. METODE PENGERJAAN
## 1. Adveksi-Difusi 1D

Adveksi merupakan proses terjadinya pergerakan partikel fluida akibat adanya aliran. Adveksi adalah mekanisme perpindahan massa suatu materi dari satu titik ke titik lainnya. Persamaan adveksi 1 dimensi dapat ditulis sebagai berikut :

∂F/∂t=-u ∂F/∂x  


## 2. Adveksi-Difusi 2D

Adveksi merupakan mekanisme perpindahan suatu massa atau materi dari satu titik ke titik lainnya dalam satu horizontal akibat adanya aliran maupun perbedaan tekanan. Sedangkan difusi merupakan mekanisme penyebaran suatu materi akibat adanya kecepatan aliran dan perbedaan konsentrasi suatu materi. Adapun persamaan adveksi dan difusi 2D adalah sebagai berikut:

## 3. Hidrodinamika 1D

Model Hidrodinamika 1D dibangun dari adanya proses-proses yang mempengaruhi pergerakan massa air. Model ini juga dibangun berdasarkan hukum kontinuitas dan hukum momentum :

ΣFx=∂u/∂t+u ∂/∂x+v ∂/∂x  untuk momentum, dan

(∂(ρζ))/∂t-∂(ρUh)/∂x=ρq_x  untuk kontinuitas

Selain itu, model hidrodinamika 1D ini memiliki persamaan pembangun sebagai berikut :

∂u/∂t+g ∂ζ/∂x=0, dan

∂ζ/∂t+H ∂u/∂x=0 



## 4. Hidrodinamika 2D


# III. SCRIPT DAN HASIL MODEL

Modul 3 Pengolahan Adveksi-Difusi 1D
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

HASIL

![image](https://user-images.githubusercontent.com/106054022/169931383-d2843cc2-b4f0-4535-94b6-c9df86e2f2bc.png)
![image](https://user-images.githubusercontent.com/106054022/169931477-cb190429-4428-4407-b324-103b096431f5.png)
![image](https://user-images.githubusercontent.com/106054022/169931528-7e055d86-71de-4d07-8a2e-2f3fbc13a91c.png)
![image](https://user-images.githubusercontent.com/106054022/169931557-1bd22935-1c50-458f-981f-48926236065e.png)


# IV. PENERAPAN DALAM BIDANG OSEANOGRAFI


# V. PENUTUP
Demikianlah tugas akhir praktikum pemodelan oseanografi 2022 ini kamu buat. Seluruh authors meminta maaf apabila masih terdapat banyak kekurangan dan kesalahan dalam pembuatan tugas akhir ini. Team 18 selaku authors dari tugas akhir ini mengucapkan terima kasih kepada:
1. Dr. Aris Ismanto, S.Si., M.Si. selaku dosen pengampu mata kuliah Pemodelan Oseanografi
2. Prof. Dr. Denny Nugroho Sugianto, S.T., M.Si. selaku dosen pengampu mata kuliah Pemodelan Oseanografi
3. Dr. Elis Indrayanti, S.T., M.Si. selaku dosen pengampu mata kuliah Pemodelan Oseanografi
4. Rikha Widiaratih, S.Si., M.Si. selaku dosen pengampu mata kuliah Pemodelan Oseanografi
5. Tim Asisten Praktikum Pemodelan Oseanografi 2022
6. Seluruh rekan-rekan Oseanografi 2020
