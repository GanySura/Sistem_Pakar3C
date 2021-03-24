# Sistem_Pakar3C GanyBerduSura - 1184008

 BFS  melakukan pencarian secara melebar yang  mengunjungi simpul secara preorder yaitu mengunjungi suatu simpul kemudian mengunjungi semua simpul yang bertetangga dengan simpul tersebut terlebih dahulu. Selanjutnya, simpul yang belum dikunjungi dan bertetangga dengan simpul-simpul yang tadi dikunjungi , demikian seterusnya. Jika graf berbentuk pohon berakar, maka semua simpul pada aras d dikunjungi lebih dahulu sebelum simpul-simpul pad aras d+1.
Sedangkan DFS sendiri lebih pada pencarian dilakukan pada satu node dalam setiap level dari yang paling kiri. Jika pada level yang paling dalam, solusi belum ditemukan, maka pencarian dilanjutkan pada node sebelah kanan. Node yang kiri dapat dihapus dari memori. Jika pada level yang paling dalam tidak ditemukan solusi, maka pencarian dilanjutkan pada level sebelumnya. Demikian seterusnya sampai ditemukan solusi. Jika solusi ditemukan maka tidak diperlukan proses backtracking (penelusuran balik untuk mendapatkan jalur yang dinginkan).
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
