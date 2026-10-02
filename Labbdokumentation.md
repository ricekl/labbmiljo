# Labbdokumentation

## Introduktion

Jag heter Rickard Eklund. Det är den 2 oktober 2026 och jag studerar i kursen IT-Infrastruktur och Secure Cloud.

Labbmiljön består av två virituella maskiner; en Windows 11-vm och en Lubuntu-vm. De är kopplade till varandra i ett internt nätverk.

## Labbmiljö & Nätverk (Kursmål 8)

| Hostname      | Operativsystem  | IP-adress    | Subnätmask    | Standard Gateway |
|---------------|-----------------|--------------|---------------|------------------|
| ri-windows-vm | Windows 11 Pro  | 192.168.1.50 | 255.255.255.0 | 192.168.1.51     |
| ri-lubuntu-vm | Lubuntu 26.04.1 | 192.168.1.51 | 255.255.255.0 | 192.168.1.50     |

## Kommandoradsgenomförande (Kursmål 9)

### Linux

**1: Skapa mappen /var/systementor/konsultdata och filen anteckningar.txt via CLI:**

```sudo mkdir -p /var/systementor/konsultdata && sudo touch /var/systementor/konsultdata/anteckningar.txt```

Man behöver använda sudo för att mappen /var/ ägs av root. mkdir skapar mappen, -p gör att mappen /var/systementor/ skapas om den inte finns. touch skapar en tom fil.

**2: Skapa en ny användargrupp (konsulter):**

```sudo groupadd konsulter```

**3.1: Tilldela mappen och filen till gruppen:**

```sudo chgrp -R konsulter /var/systementor/konsulter```

chgrp ändrar vilken grupp som äger en fil eller mapp. -R gör att alla filer i mappen man pekar på också blir ägda av gruppen

**3.2: Ställ in behörigheter till mappen och filen:**

```sudo chmod 750 /var/systementor/konsulter && sudo chmod 640 /var/systementor/konsulter/antäckningar.txt```

chmod ändrar behörigheter på mappar och filer

**4: Inspektera och dokumentera behörigheterna via CLI:**

Rättigheterna för mappen konsultdata (som man får av ```ls -la /var/systementor```) är: ```drwxr-x--- root konsulter``` 

Detta betyder i ordning: Det är en mapp (directory), ägaren kan läsa (read), ägaren kan skriva (write), ägaren kan exekvera, gruppen kan läsa,gruppen kan *inte* skriva (-), gruppen kan exekvera, andra användare kan *inte* läsa, skriva eller exekvera, root är ägar-användaren, konsulter är ägar-gruppen.

Rättigheterna för filen antäckningar.txt (som man får av ```ls -la /var/systementor/konsulter```) är: ```-rw-r----- root konsulter```

Detta betyder i ordning: Det är inte en mapp, ägaren kan läsa, skriva, *inte* exekvera, gruppen kan läsa, men *inte* skriva eller exekvera, andra användare kan inte läsa, skriva eller exekvera, root är ägar-användaren, konsulter är ägargruppen.

### Windows

**1: Skapa mappen C:\Systementor\KonsultData via CLI.:**

```New-Item -ItemType Directory -Path "C:\Systementor\KonsultData"```



## Git & Versionshantering (Kursmål 10)

https://github.com/ricekl/labbmiljo

## AI-logg & Reflektion (Kursmål 11)
