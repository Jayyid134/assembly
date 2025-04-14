# Nama: Jayyid Zakaria
# Kelas: SKU2B

```nasm

section .text
   global _start           
	
_start:                     
   mov    al, 5            
   mov    bl, 3            
   or     al, bl             
   add    al, byte '0'      
	
   mov    [result],  al
   mov    eax, 4
   mov    ebx, 1
   mov    ecx, result
   mov    edx, 1 
   int    0x80
    
outprog:
   mov    eax,1             
   int    0x80              
	
section    .bss
result resb 1
```

output = 7

## Penjelasan
Program Assembly di atas merupakan sebuah kode sederhana yang melakukan operasi logika OR antara dua nilai dan menampilkan hasilnya. Pertama, program menginisialisasi register AL dengan nilai 5 (binary 0101) dan register BL dengan nilai 3 (binary 0011). Kemudian, instruksi OR dilakukan antara AL dan BL, menghasilkan nilai 7 (binary 0111), karena operasi OR akan mengembalikan 1 jika salah satu bit yang dibandingkan adalah 1. Hasil ini kemudian diubah dari bilangan biner ke karakter ASCII dengan menambahkan '0' (nilai 48 dalam ASCII), sehingga nilai 7 berubah menjadi karakter '7'. Karakter ini disimpan dalam variabel result dan ditampilkan ke layar menggunakan syscall write (interrupt 0x80 dengan EAX=4).

Setelah menampilkan hasil, program keluar dengan syscall exit (interrupt 0x80 dengan EAX=1). Variabel result dideklarasikan dalam section .bss sebagai penyimpanan 1 byte. Output dari program ini adalah karakter '7', yang sesuai dengan hasil operasi OR antara 5 dan 3. Program ini menggambarkan bagaimana operasi logika dasar dapat diimplementasikan dalam Assembly, serta bagaimana mengonversi dan menampilkan hasilnya sebagai karakter yang dapat dibaca oleh pengguna.
