graph TD
    subgraph Microcontrolador LPC54608
        A[SD_CLK] --- CLK_PIN(Pin CLK)
        B[SD_CMD] --- CMD_PIN(Pin CMD)
        C[SD_D0] --- D0_PIN(Pin DAT0)
        D[SD_D1] --- D1_PIN(Pin DAT1)
        E[SD_D2] --- D2_PIN(Pin DAT2)
        F[SD_D3] --- D3_PIN(Pin DAT3)
        G[GPIO_CD<br>(Card Detect)] --- CD_PIN(Pin CD)
        H[GPIO_WP<br>(Write Protect)] --- WP_PIN(Pin WP)
        I[GPIO_PWR_EN<br>(Control de Energía)] --- PWR_CTRL(Circuito<br>Control de VCC)
        J[VCC_3V3<br>(Regulado)] --- VCC_FILT(Condensadores<br>de Filtrado)
        K[GND] --- GND_CON(GND)
    end

    subgraph Componentes Esenciales
        R1[47kΩ<br>Pull-up] --- CMD_PIN
        R2[47kΩ<br>Pull-up] --- D0_PIN
        R3[47kΩ<br>Pull-up] --- D1_PIN
        R4[47kΩ<br>Pull-up] --- D2_PIN
        R5[47kΩ<br>Pull-up] --- D3_PIN
        CAP1[10uF] --- VCC_FILT
        CAP2[.1uF] --- VCC_FILT
        PWR_CTRL --- VCC_FILT
    end

    subgraph Zócalo MicroSD
        CLK_PIN --- ZOC_CLK[CLK (Pin 5)]
        CMD_PIN --- ZOC_CMD[CMD (Pin 3)]
        D0_PIN --- ZOC_D0[DAT0 (Pin 7)]
        D1_PIN --- ZOC_D1[DAT1 (Pin 8)]
        D2_PIN --- ZOC_D2[DAT2 (Pin 1)]
        D3_PIN --- ZOC_D3[DAT3 (Pin 2)]
        CD_PIN --- ZOC_CD[CD (Switch Interno)]
        WP_PIN --- ZOC_WP[WP (Switch Interno)]
        VCC_FILT --- ZOC_VCC[VCC (Pin 4)]
        GND_CON --- ZOC_GND[GND (Pin 6)]
    end

    style ZOC_CLK fill:#f9f,stroke:#333,stroke-width:2px
    style ZOC_CMD fill:#f9f,stroke:#333,stroke-width:2px
    style ZOC_D0 fill:#f9f,stroke:#333,stroke-width:2px
    style ZOC_D1 fill:#f9f,stroke:#333,stroke-width:2px
    style ZOC_D2 fill:#f9f,stroke:#333,stroke-width:2px
    style ZOC_D3 fill:#f9f,stroke:#333,stroke-width:2px
    style ZOC_CD fill:#f9f,stroke:#333,stroke-width:2px
    style ZOC_WP fill:#f9f,stroke:#333,stroke-width:2px
    style ZOC_VCC fill:#f9f,stroke:#333,stroke-width:2px
    style ZOC_GND fill:#f9f,stroke:#333,stroke-width:2px

    style R1 fill:#fff,stroke:#333,stroke-width:2px
    style R2 fill:#fff,stroke:#333,stroke-width:2px
    style R3 fill:#fff,stroke:#333,stroke-width:2px
    style R4 fill:#fff,stroke:#333,stroke-width:2px
    style R5 fill:#fff,stroke:#333,stroke-width:2px
    style CAP1 fill:#fff,stroke:#333,stroke-width:2px
    style CAP2 fill:#fff,stroke:#333,stroke-width:2px
    style PWR_CTRL fill:#fff,stroke:#333,stroke-width:2px
