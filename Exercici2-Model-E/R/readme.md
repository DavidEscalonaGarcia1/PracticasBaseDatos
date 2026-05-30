erDiagram
    PERSONATGE ||--o{ ENEMIC : enfronta
    PERSONATGE }o--|| MASCOTA : acompanya
    PERSONATGE }o--o{ HABILITAT : posseeix
    PERSONATGE }o--o{ ITEM : equipa
    HABILITAT }o--o{ HABILITAT : combina
    MASCOTA }o--o{ ITEM : transporta

    PERSONATGE {
        string dni PK "NOT NULL"
        string nom "NOT NULL"
        string cognom "NOT NULL"
        int vida "NOT NULL"
        int forca "NOT NULL"
        int agilitat "NOT NULL"
        int carisma "NOT NULL"
    }

    ENEMIC {
        int codi PK "NOT NULL"
        string nom "NOT NULL"
        string tipus "NOT NULL"
        int nivell "NOT NULL"
        int vida "NOT NULL"
        int forca
        int agilitat
        int carisma
    }

    HABILITAT {
        int codi PK "NOT NULL"
        string nom "NOT NULL"
        string tipus "NOT NULL"
        int cost "NOT NULL"
        int dany "NOT NULL"
        int cooldown "NOT NULL"
    }

    ITEM {
        int codi PK "NOT NULL"
        string nom "NOT NULL"
        boolean equipable "NOT NULL"
        boolean comercable "NOT NULL"
        string tipus
        float pes
        string qualitat
        float mesura_x
        float mesura_y
        float mesura_z
    }

    MASCOTA {
        int num_xip PK "NOT NULL"
        string nom "NOT NULL"
        int motxilla
    }