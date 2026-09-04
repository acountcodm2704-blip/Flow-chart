```mermaid
flowchart TD
A(Student Buka Course) --> B[Load Module & Lesson List]
B --> C[Pilih Lesson]
C --> D{Section HTMl}
D --> E{Bab 1}
D --> F[Ujian praktek]
E --> G[video & materi]
E --> H[practice]
G --> H
H --> I{Lulus practice?}
I --> |lulus| J[ke bab selanjutnya]
I --> |gagal| K[Mengulang practice]
J --> L{next bab}
L --> F
F --> M{Lulus ujian praktek?}
M --> |lulus| N[ke section selanjutnya]
M --> |gagal| O[Mengulang ujian praktek]
N --> P[Next section]
P --> Q[Section css-js]
Q --> R[setelah ujian praktek js]
R --> S[Ujian akhir]
S --> U{Lulus Ujian Akhir?}
U --> |lulus| V[Menyelesaikan Materi Preprogram]
U --> |gagal| W[Mengulang ujian akhir]


   
```

**Langkah:**

- Progress video: FE throttle `PUT /progress` tiap 10 detik + `onEnded` → 100%.
- Quiz: `quizzes` + `quiz_questions` → `quiz_attempts` hitung `passed`. Jika passed → lesson COMPLETED.
- Assignment: `submissions` status PENDING → Instructor `PATCH /submissions/:id/grade` → jika semua assignment lulus → course COMPLETED.
- XP & Leaderboard: service `Gamification` listen event `LESSON_COMPLETED` → `xp_logs` + `redis.zincrby(leaderboard:{tenantId}:{season}, xp, userId)`.
- Sertifikat: `certificates` dengan `code = nanoid(10)` → FE `/verify/[code]`.
