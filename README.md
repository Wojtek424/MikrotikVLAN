# Projekt Sieci Firmowej (Topologia VLAN z MikroTik)

## Opis projektu

Projekt przedstawia infrastrukturę sieciową firmy, rozłożoną na dwa piętra, z wykorzystaniem routerów i switchy MikroTik. Topologia zakłada segmentację VLAN, routing statyczny, NAT oraz redundancję routerów w celu zapewnienia wysokiej dostępności.

---

## Cechy projektu

- Podział na VLAN-y: **10**, **20**, **30**, **50**, **90**, **100**, **150**
- Izolacja VLAN-ów 
- Redundantna para routerów na piętrze A (VRRP)
- Zarządzanie wyłącznie z VLAN **50**
- NAT z VLAN **50** do VLAN **90** (dla sieci zarządzającej)
- Dostęp do serwera WWW z VLAN-ów **10**, **20** i **50**

---

## Opis plików

| Nazwa pliku                  | Opis                                                   |
|-----------------------------|--------------------------------------------------------|
| `Dokumentacja.pdf`          | Szczegółowy opis topologii i konfiguracji              |
| `nazwa_urzadzenia.txt`      | Plik konfiguracyjny dla danego urządzenia MikroTik     |
| `Topology.png`              | Graficzny diagram sieci                                |
| `mikrotik_vlan.unl`         | Plik projektu do zaimportowania w EVE-NG/PNetLab       |

---

## Jak uruchomić projekt

### Wymagania

- Maszyna wirtualna z zainstalowanym **EVE-NG** lub **PNetLab**
- Obraz RouterOS MikroTik w wersji **v7.19.3**:
  - Skopiuj do katalogu:
    ```
    /opt/unetlab/addons/qemu/Mikrotik-7
    ```
  - Wykonaj polecenie naprawiające uprawnienia:
    ```
    /opt/unetlab/wrappers/unl_wrapper -a fixpermissions
    ```
- Obraz serwera WWW z ustawionym statycznym adresem IP zgodnym z tabelą VLAN
- Możliwość połączenia przez **Telnet** (IP maszyny + port widoczny w GUI po najechaniu na node)

---

### Uruchomienie projektu

1. Zaimportuj plik `mikrotik_vlan.unl` do EVE-NG/PNetLab
2. Otwórz projekt i uruchom wszystkie węzły (nody)
3. Zaloguj się do każdego urządzenia
4. Wklej konfigurację z pliku `.txt` przypisanego do danego urządzenia
5. Na hostach VPC (lub innym systemie operacyjnym):
    - Pobierz adres IP:
      ```
      dhcp
      ```
    - Sprawdź komunikację między VLAN-ami i dostęp do serwera WWW

---

##Logowanie do urządzeń
 - Do testów laboratoryjnych pozostawiono domyślną nazwę użytkownika admin bez hasla

## Autor projektu

**Wojciech Wluka**
