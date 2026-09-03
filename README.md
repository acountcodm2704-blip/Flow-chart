```mermaid
flowchart TD
    A([Mulai]) --> B[Input Data]
    B --> C{Data benar?}
    C -->|Ya| D([Selesai])
    C -->|Tidak| B
