-- Exercici Model Conceptual --

erDiagram
    PERSONATGE ||--o{ HABILITAT : té
    PERSONATGE ||--o{ ARMA : posseeix
    PERSONATGE ||--o{ ENEMIC : enfronta
    PERSONATGE ||--|| VIDA : té
    ARMA ||--|| MESURES : té
    HABILITAT ||--o{ TIPUS_HABILITAT : és
    ENEMIC ||--|| TIPUS_ENEMIC : és

    PERSONATGE {
        int DNI PK
        string Nom
        string Cognom
        int Força
        int Agilitat
        int Carisma
        int Nivell
        int Experiència
    }

    VIDA {
        int Vida_ID PK
        int Punts_Vida_Actuals
        int Punts_Vida_Maxims
        int Regeneracio
    }

    ARMA {
        int Arma_ID PK
        string Nom
        string Tipus
        float Pes
        string Qualitat
        float Preu
        int Dany
        int Velocitat_Atac
    }

    MESURES {
        int Mesura_ID PK
        float X
        float Y
        float Z
    }

    HABILITAT {
        int Habilitat_ID PK
        string Nom
        int Dany
        int Cost_Energia
        int Cooldown_Segons
        int Alcance
        string Descripcio
    }

    TIPUS_HABILITAT {
        int Tipus_ID PK
        string Nom_Tipus
        string Descripcio
    }

    ENEMIC {
        int Enemic_ID PK
        string Nom
        int Nivell
        int Punts_Vida
        int Força_Atac
        string Tipus
        int Experiència_Recompensa
    }

    TIPUS_ENEMIC {
        int Tipus_Enemic_ID PK
        string Nom_Tipus
        string Debilitat
        string Fortalesa
    }


-- Model E/R --

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
