# **Model SIR dengan memperhitungkan dampak vaksinasi dan misinformasi vaksin terhadap penyebaran COVID-19**
![alt text](image.png)
---

### **Kompartemen dalam Model**
1. **$S$ (Susceptible)**  
   - Individu yang rentan terhadap infeksi karena belum terinfeksi, belum divaksinasi, atau belum memiliki imunitas.
   - Rentan terhadap infeksi melalui kontak dengan individu yang terinfeksi $I$.

2. **$V$ (Vaccinated)**  
   - Individu yang telah divaksinasi dan memiliki kekebalan parsial terhadap penyakit.  
   - Masih memiliki kemungkinan kecil untuk terinfeksi jika terkena paparan.

3. **$Vm$ (Misinformed Susceptible)**  
   - Individu yang rentan terhadap infeksi karena dipengaruhi oleh misinformasi vaksin sehingga menolak vaksinasi.

4. **$I$ (Infected)**  
   - Individu yang terinfeksi COVID-19 dan dapat menularkan penyakit kepada individu rentan ($S$, $V$, $Vm$).

5. **$R$ (Recovered)**  
   - Individu yang telah pulih dari infeksi dan memiliki kekebalan.

6. **$N$**  
   - Total populasi:  
     
     $N$ $=$ $S$ $+$ $V$ $+$ $Vm$ $+$ $I$ $+$ $R$

---

### **Persamaan Diferensial Model**

#### 1. **Persamaan untuk Susceptible ($S$)**  
$$
\frac{dS}{dt} = \alpha N - \frac{\beta_1 S I}{N} - \gamma_1 S - \gamma_2 S - \mu S
$$
- $ \alpha N $: Laju kelahiran populasi baru yang masuk ke $ S $.  
- $ \frac{\beta_1 S I}{N} $: Infeksi yang terjadi pada individu rentan melalui kontak dengan $ I $.  
- $ \gamma_1 S $: Individu rentan yang beralih ke $ V $ karena divaksinasi.  
- $ \gamma_2 S $: Individu rentan yang beralih ke $ Vm $ karena terpengaruh misinformasi.  
- $ \mu S $: Kematian alami pada individu rentan.

#### 2. **Persamaan untuk Vaccinated ($ V $)**  
\[
\frac{dV}{dt} = \gamma_1 S - \frac{\beta_2 V I}{N} - \mu V
\]
- $ \gamma_1 S $: Individu rentan yang divaksinasi.  
- $ \frac{\beta_2 V I}{N} $: Infeksi pada individu yang telah divaksinasi.  
- $ \mu V $: Kematian alami pada individu yang divaksinasi.

#### 3. **Persamaan untuk Misinformed ($ Vm $)**  
\[
\frac{dVm}{dt} = \gamma_2 S - \frac{\beta_3 Vm I}{N} - \mu Vm
\]
- $ \gamma_2 S $: Individu rentan yang menjadi kelompok $ Vm $ karena misinformasi.  
- $ \frac{\beta_3 Vm I}{N} $: Infeksi pada individu yang menolak vaksin karena misinformasi.  
- $ \mu Vm $: Kematian alami pada individu $ Vm $.

#### 4. **Persamaan untuk Infected ($ I $)**  
\[
\frac{dI}{dt} = \frac{\beta_1 S I}{N} + \frac{\beta_2 V I}{N} + \frac{\beta_3 Vm I}{N} - \gamma_3 I - \mu I
\]
- $ \frac{\beta_1 S I}{N} $: Infeksi dari individu $ S $.  
- $ \frac{\beta_2 V I}{N} $: Infeksi dari individu $ V $.  
- $ \frac{\beta_3 Vm I}{N} $: Infeksi dari individu $ Vm $.  
- $ \gamma_3 I $: Individu yang pulih dari infeksi.  
- $ \mu I $: Kematian alami atau karena penyakit pada individu yang terinfeksi.

#### 5. **Persamaan untuk Recovered ($ R $)**  
\[
\frac{dR}{dt} = \gamma_3 I - \gamma R
\]
- $ \gamma_3 I $: Individu yang pulih dari infeksi.  
- $ \gamma R $: Kehilangan kekebalan, jika kekebalan tidak bersifat permanen.

---

### **Parameter Penting dalam Model**
- **$ \beta_1, \beta_2, \beta_3 $:** Tingkat kontak efektif antara individu yang terinfeksi dengan $ S $, $ V $, dan $ Vm $.  
- **$ \gamma_1, \gamma_2 $:** Laju vaksinasi dan laju terpengaruh misinformasi.  
- **$ \gamma_3 $:** Laju pemulihan dari infeksi.  
- **$ \mu $:** Laju kematian alami.  
- **$ \alpha $:** Laju kelahiran.

---
