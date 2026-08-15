See: https://github.com/derv82/wifite2 for application details

Used to crack and attack wifi passwords.
Terminal Command - **wifite

Basic settings - Can be added after the wifite command

SETTINGS:
  -v, --verbose                              Shows more options (-h -v). Prints commands and outputs. 
  -i [interface]                             Wireless interface to use, e.g. wlan0mon (default: ask)
  -c [channel]                               Wireless channel to scan e.g. 1,3-6 (default: all 2Ghz channels)
  -inf, --infinite                           Enable infinite attack mode. Modify scanning time with -p 
  -mac, --random-mac                         Randomize wireless card MAC address (default: off)
  -p [scan_time]                             Pillage: Attack all targets after scan_time (seconds)
  --kill                                     Kill processes that conflict with Airmon/Airodump (default: off)
  -pow [min_power], --power [min_power]      Attacks any targets with at least min_power signal strength
  --skip-crack                               Skip cracking captured handshakes/pmkid (default: off)
  -first [attack_max], --first [attack_max]  Attacks the first attack_max targets
  -ic, --ignore-cracked                      Hides previously-cracked targets. (default: off)
  --clients-only                             Only show targets that have associated clients (default: off)
  --nodeauths                                Passive mode: Never deauthenticates clients (default: deauth targets)
  --daemon                                   Puts device back in managed mode after quitting (default: off)

WEP:
  --wep                                      Show only WEP-encrypted networks
  --require-fakeauth                         Fails attacks if fake-auth fails (default: off)
  --keep-ivs                                 Retain .IVS files and reuse when cracking (default: off)

WPA:
  --wpa                                      Show only WPA-encrypted networks (includes WPS)
  --new-hs                                   Captures new handshakes, ignores existing handshakes in hs
  --dict file                              File containing passwords for cracking              

WPS:
  --wps                                      Show only WPS-enabled networks
  --wps-only                                 Only use WPS PIN & Pixie-Dust attacks
  --bully                                    Use bully program for WPS PIN & Pixie-Dust attacks
  --reaver                                   Use reaver program for WPS PIN & Pixie-Dust attacks
  --ignore-locks                             Do not stop WPS PIN attack if AP becomes locked

PMKID:
  --pmkid                                    Only use PMKID capture, avoids other WPS & WPA attacks 
  --no-pmkid                                 Don't use PMKID capture (default: off)
  --pmkid-timeout [sec]                      Time to wait for PMKID capture (default: 300 seconds)

COMMANDS:
  --cracked                                  Print previously-cracked access points
  --check [file]                             Check a .cap file (or all hs/* .cap files) for WPA handshakes
  --crack                                    Show commands to crack a captured handshake