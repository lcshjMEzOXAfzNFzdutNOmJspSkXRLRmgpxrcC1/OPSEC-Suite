# OPSEC Suite — Operational Security & Privacy Toolkit

A complete, professional-grade Python privacy and security toolkit. Every function performs real operations — no placeholders.

## Features

- **OPSEC Education** — threat modeling, checklists, best practices
- **Metadata Tools** — EXIF extraction/removal, batch file cleaning
- **Security Tools** — local encrypted password manager, file encryption, threat intelligence
- **Identity & Anonymity** — persona generator, temp email, phone number analysis, PGP guide
- **Networking** — DNS leak test, MAC randomization, Tails OS and VM guides
- **Defensive Tools** — HaveIBeenPwned breach check, antivirus detection, fingerprint guide
- **VPN & Proxy** — VPN detection, proxy checker/verifier, free/paid provider lists

## Installation

```bash
cd OPSEC_Suite
pip install -r requirements.txt
python main.py
```

## Requirements

- Python 3.8+
- pip packages: see `requirements.txt`

## Usage

Run the interactive menu:

```bash
python main.py
```

Navigate using number keys. Type `s` from the main menu for a quick VPN/IP status check.

### Individual Module Examples

```python
# Check your IP and VPN status
from modules.vpn.vpn_checker import check_vpn_active, full_vpn_test
full_vpn_test()

# Check email for data breaches
from modules.defensive.breach_check import check_hibp_email
results = check_hibp_email("test@example.com", api_key="YOUR_HIBP_KEY")

# Check if a password was pwned (uses k-Anonymity, password never sent)
from modules.defensive.breach_check import check_password_pwned
count = check_password_pwned("my_password_here")

# Generate a fake persona
from modules.opsec.persona_creation import generate_persona
persona = generate_persona(gender="female")

# Extract EXIF data from an image
from modules.metadata.exif_tool import extract_exif_pillow
data = extract_exif_pillow("photo.jpg")

# Remove EXIF data from an image
from modules.metadata.exif_tool import remove_exif
remove_exif("photo.jpg", "photo_clean.jpg")

# Encrypt text
from modules.security.decryption import encrypt_text, decrypt_text
ciphertext = encrypt_text("Secret message", "my_password")
plaintext  = decrypt_text(ciphertext, "my_password")

# Generate Firefox privacy config
from modules.opsec.privacy_browser import generate_user_js
generate_user_js("user.js", profile="strict")

# Analyze a phone number
from modules.identity.phone_number import analyze_phone_number
info = analyze_phone_number("+15555551234")

# Test a proxy
from modules.vpn.proxy_checker import test_proxy
result = test_proxy("192.168.1.1:8080")

# IP geolocation
from utils.network import get_ip_info
info = get_ip_info("8.8.8.8")

# Port scan
from utils.network import port_scan
results = port_scan("example.com", [80, 443, 22, 21])
```

## Module Descriptions

| Category | Module | Description |
|---|---|---|
| OPSEC | `what_opsec.py` | OPSEC principles and threat model worksheet |
| OPSEC | `opsec_checklist.py` | Scored interactive security checklist |
| OPSEC | `privacy.py` | Privacy best practices by category |
| OPSEC | `darkweb.py` | Tor/dark web educational resources |
| OPSEC | `persona_creation.py` | Fake identity generator |
| OPSEC | `privacy_browser.py` | Firefox user.js hardening config generator |
| OPSEC | `search_engines.py` | Private search engine comparison |
| Metadata | `exif_tool.py` | EXIF data viewer and remover |
| Metadata | `clean_metadata.py` | Batch metadata cleaner |
| Metadata | `metadata.py` | Metadata privacy overview |
| Security | `password_manager.py` | Local encrypted password vault + generator |
| Security | `decryption.py` | AES file/text encryption, RSA key generation |
| Security | `reverse_security.py` | IP reputation and hash lookup |
| Security | `signal.py` | Signal messenger setup guide |
| Security | `veracrypt.py` | VeraCrypt disk encryption guide |
| Identity | `phone_number.py` | Phone number validator and analyzer |
| Identity | `secure_email.py` | Encrypted email provider comparison |
| Identity | `temp_email.py` | Temporary email inbox via Guerrilla Mail |
| Identity | `kleopatra.py` | GPG/PGP key management guide |
| Networking | `network_setting.py` | DNS leak test, MAC randomization guide |
| Networking | `tails_os.py` | Tails OS installation and usage guide |
| Networking | `virtual_machine.py` | VM compartmentalization for OPSEC |
| Defensive | `breach_check.py` | HaveIBeenPwned email + password check |
| Defensive | `antivirus.py` | AV detection + ClamAV scanning |
| Defensive | `fingerprint.py` | Browser fingerprinting countermeasures |
| Defensive | `ad_nauseam.py` | Ad obfuscation privacy tools |
| Defensive | `track_me_not.py` | Tracking methods and defenses |
| VPN | `ip_lookup.py` | IP geolocation and VPN detection |
| VPN | `vpn_checker.py` | VPN + DNS + IPv6 leak test |
| VPN | `proxy_checker.py` | Proxy list tester with anonymity levels |
| VPN | `proxy_verifier.py` | Detailed proxy anonymity verifier |
| VPN | `proxy_generator.py` | Fetch free proxy lists from APIs |

## Configuration

Edit `config.json` to add API keys:

```json
{
    "api_keys": {
        "hibp": "your-haveibeenpwned-key",
        "virustotal": "your-virustotal-key"
    }
}
```

- **HIBP API key**: https://haveibeenpwned.com/API/Key (~$3.50/month)
- **VirusTotal API key**: https://www.virustotal.com/gui/join-us (free tier available)

The password check function works **without** an API key using k-Anonymity.

## Disclaimer

This toolkit is intended for **educational purposes** and **legitimate defensive security** use only.

- Use only on systems and accounts you own or have explicit permission to test.
- Always comply with applicable laws and regulations.
- The authors are not responsible for any misuse or illegal activity.
- Information about dark web and anonymity tools is provided purely for education.

## License

Apache License 2.0 — See individual module files for details.
