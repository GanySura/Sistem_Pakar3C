# Sistem_Pakar3C

Logika fuzzy adalah suatu cara yang tepat untuk memetakan suatu ruang input ke dalam suatu ruang output.
sebagai contoh pada codingan berikut untuk mengecek dimana keluarga pada data yang telah ditwntukan apakah eluarga tersebut layak dengan aturan atruan yang ditetakan
1. mendefinisikan rule-rule yg nanti akan dipakai contohnya
aturan1 = ["kecil","rendah","sangat layak"]
aturan2 = ["kecil","menengah","sangat layak"]

2.kemudian ada fungsi trapesium yang berfungsi sebagai penentuan nilai anggota dengan x sebagai penentu dari variabel a,b,c,d
def trapesium(x,a,b,c,d):
    if x<=a and x>=d:
        return 0
    elif a<x and x<b:
        return (x-a)/(b-a)
    elif b<=x and x<=c:
        return 1
    elif c<x and x<=d:
        return -(x-d)/(d-c)
    else:
        return 0

3. kemudian adakan fungsi duplicat agar tidak terjadi error
4. fungsi untuk menguji hasil nilai keanggotaan yg telah dilabeli kedalam rule yg telah dibuat
def interference(x,y):
    hasil_interference = []

5. fungsi untuk melabeli nilai keanggotaan dari pendapatan yang di dapat    
def cbcbP(dtListP):
    listData2 = []
    for c in range(1, len(dtListP)):
        if c==1:
            listDataP = ['kecil',dtListP[c]]
            listData2.append(listDataP)
            #print(listDataP)
6.fungsi untuk melabeli nilai keanggotaan dari utang
def cbcbU(dtListU):
    listData1 = []
    for b in range(1, len(dtListU)):
        if b==1:
            listDataU = ['rendah',dtListU[b]]
            listData1.append(listDataU)    

7.fungsi untuk mengembalikan hasil nilai dari beberapa kelayakan/ satu kelayakan menjadi satu nilai presentase
def defuzzifikasi(interference):
    if len(interference) == 1:
        area1_atas = 0
        area1_bawah = interference[0][1]
        if interference[0][0] == 'tidak layak':
            area1_atas = interference[0][1] * 40
        elif interference[0][0] == 'layak':
            area1_atas = interference[0][1] * 60
        elif interference[0][0] == 'sangat layak':
            area1_atas = interference[0][1] * 80
        return area1_atas / area1_bawah 
8. membaca data dari csv untuk dimasukan ke dalam list
with open('DataTugas2.csv', newline='') as datatugas2:
    next(datatugas2)
    spamreader = csv.reader(datatugas2, delimiter=' ', quotechar='|')
    listDataA = []

9.mengubah nilai awal menjadi nilai keanggotaan
        smallP = trapesium(a[1], 0, 0, 0.5, 0.8)
        mediumP = trapesium(a[1], 0.5, 0.8, 1.3, 1.6)
        largeP = trapesium(a[1], 1.3, 1.6, 2.0, 2.0)
        
        lowU = trapesium(a[2], 0, 0, 20, 40)
        mediumU = trapesium(a[2], 20, 40, 60, 80)
        highU = trapesium(a[2], 60, 80, 100, 100)

10.memasukan nilai keanggotaan ke dalam list masing-masing
        dtListP = [a[0],smallP,mediumP,largeP]
        dtListU = [a[0],lowU,mediumU,highU]

11. melakukan fuzzifikasi
        cbcb2P = cbcbP(dtListP)
        cbcb1U = cbcbU(dtListU)
        
12. melakukan interference
        cbcb1 = interference(cbcb2P,cbcb1U)
        
13. melakukan defuzzifikasi
        cbcb2 = defuzzifikasi(cbcb1)

14. melakukan pengecekan skor
        if cbcb2 > 30:
            tebakan.append([a[0], cbcb2])

15. melakukan sortir dan menyisakan 20 keluarga terlayak
      tebakan.sort(key=lambda z:int(z[1]), reverse=True)
      tebakan = tebakan[:20]
