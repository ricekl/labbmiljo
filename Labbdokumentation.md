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

1: Skapa mappen /var/systementor/konsultdata och filen anteckningar.txt via CLI:

```sudo mkdir -p /var/systementor/konsultdata && sudo touch /var/systementor/konsultdata/anteckningar.txt```

2: Skapa en ny användargrupp (konsulter):

```sudo groupadd konsulter```

3.1: Tilldela mappen och filen till gruppen:

```sudo chgrp -R konsulter /var/systementor/konsulter```

3.2: Ställ in behörigheter till mappen och filen:

```sudo chmod 750 /var/systementor/konsulter && sudo chmod 640 /var/systementor/konsulter/antäckningar.txt```

4: Inspektera och dokumentera behörigheterna via CLI:

Rättigheterna för mappen konsultdata (som man får av ```ls -la /var/systementor```) är: ```drwxr-xr-x root konsulter```

Rättigheterna för filen antäckningar.txt (som man får av ```ls -la /var/systementor/konsulter```) är: ```-rw-r--r-- root konsulter```

## Git & Versionshantering (Kursmål 10)

https://github.com/ricekl/labbmiljo

## AI-logg & Reflektion (Kursmål 11)
