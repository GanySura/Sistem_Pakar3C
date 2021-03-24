# Sistem_Pakar3C GanyBerduSura - 1184008

Pada kedua codingan terdapat perbedaan

Perbedaan bisa dilihat pada codingan dibawah ini
jika pada bfs maka barisan data akan berada pada posisi belakangan

#Queue atau antrian adalah barisan elemen/data, dimana ketika elemen/data baru ditambah maka penambahannya akan berada di posisi belakang (rear) dan jika dilakukan pengambilan elemen dilakukan di elemen paling depan (front). Queue dikenal bersifat FIFO (first in first out).
           
     def bfs(graf, mulai, tujuan):
        queue = [[mulai]] 
        visited = set()
     while queue:
     #masukkan antrian paling depan ke variabel jalur
     jalur = queue.pop(0)
        
     #simpan node yang dipilih ke variabel state, misal jalur = C,B maka simpan B ke variabel state
     state = jalur[-1]


Sedangkan pada pada dfs 
#Stack atau tumpukan adalah sebuah kumpulan data yang diletakkan di atas data yang lain. Dengan demikian stack adalah struktur data yang menggunakan konsep LIFO (Last in first out). Pada stack, elemen terakhir yang disimpan (push) akan menjadi elemen pertama yang diambil (pop)
  
        
        
        def dfs(graf, mulai, tujuan):
             stack = [[mulai]] 
             visited = set()
        while stack: 
         # masukkan antrian paling depan ke variabel jalur
        jalur = stack.pop(-1)
        
        # simpan node yang dipilih ke variabel state, misal jalur = C,B maka simpan B ke variabel state
        state = jalur[-1]
        
        # cek state apakah sama dengan tujuan, jika ya maka return jalur
        if state == tujuan:
            return jalur

Kedua algoritma dengan proses yang berbeda namun menghasilkan output yang sama
