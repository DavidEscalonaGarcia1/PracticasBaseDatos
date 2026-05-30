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
