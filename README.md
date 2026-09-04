# Learning Flow
```mermaid
flowchart TD
A(Student Buka Course) --> B{memilih Module}
B --> A2[module 1]
B --> A3[module 2]
B --> A4[module 3]
A2 --> A1
A3 --> A1
A4 --> A1[Load Module & Lesson List]
A1 --> C[Pilih section]
C --> D{Section 1}
D --> E{Bab 1}
D --> F[Ujian praktek]
E --> G[video & materi]
E --> H[practice]
G --> H
H --> I{Lulus practice?}
I --> |lulus| J[ke bab selanjutnya]
I --> |gagal| K[Mengulang practice]
K --> H
J --> L[next bab]
L --> F
F --> M{Lulus ujian praktek?}
M --> |lulus| N[Next section]
M --> |gagal| O[Mengulang ujian praktek]
O --> F


N --> R[setelah ujian praktek terakhir]
R --> S[Ujian akhir]
S --> U{Lulus Ujian Akhir?}
U --> |lulus| V[Menyelesaikan Module]
U --> |gagal| W[Mengulang ujian akhir]
W --> S


   
```
---

# Landing Page guide
```mermaid
flowchart TD
A(User Membuka Landing Page) --> B[Navbar]
B --> C[Hero Section-Download App]
C --> D{CTA Download}
D --> |Play store| E[Android] 
D --> |iOS| F[iOS]
E --> G[Download & Install]
F --> G
G --> H[Login/Register]
H --> I[Gunakan Aplikasi]


```
