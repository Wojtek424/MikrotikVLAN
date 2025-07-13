# Projekt Sieci Firmowej (Topologia VLAN z Mikrotik)

## Opis projektu:
Projekt przedstawia infrastrukturę sieciową firmy podzieloną na dwa piętra z wykorzystaniem routerów i switchy MikroTik. Topologia zakłada segmentację VLAN, routing statyczny, NAT oraz redundancję na poziomie routerów.

##Cechy projektu:
- Podział na VLAN-y: 10, 20, 30, 50, 90, 150
- Izolacja VLAN-ów z selektywnym routingiem
- Redundantna para routerów na piętrze A
- Zarządzanie wyłącznie z VLAN 50
- NAT z VLAN 50 do VLAN 90
- Dostęp do serwera WWW z VLAN 10, 20 i 50

##Opis plików:
 - Dokumentacja projektu: Dokumentacja.pdf
 - Pliki konfiguracyjne dla poszczególnego urządzenia: "nazwa_urzadzenia".txt 
 - Topologia: Topology.png
 - Projekt: mikrotik_vlan.unl

##Jak uruchomić projekt:
 # Wymagania:
    - Maszyna wirtualna z zainstalowanym eve-ng lub pnetlab
    - Obraz RouterOs Mikrotik v7.19.3 wgrany do folderu /opt/unetlab/addons/qemu/Mikrotik-7 a następnie użycie komendy /opt/unetlab/wrappers/unl_wrapper -a fixpermissions
    - Obraz serwera WWW z ustawionym statycznym adresem IP (zgodny z adresacją w tabeli)
    - Dostęp do maszyny przez wirtualny telnet (Adres IP maszyny + port przypisany do węzła; port widoczny po najechaniu na node w GUI)
  #Uruchomienie:
    1)Plik z .unl należy zaimportować do maszyny eve-ng/pnetlab
    2)Po otworzeniu projektu należy uruchomić wszystkie node
    3)Po zalogowaniu się na każde urządzenie Wklej konfigurację z pliku .txt odpowiadającego danemu urządzeniu 
    4)Na hostach VPC (lub innym systemie operacyjnym):
   	- Pobierz adres IP komendą: dhcp
   	- Sprawdź komunikację między VLAN-ami oraz dostęp do serwera WWW 


Autor Projektu:
Wojciech Wluka 