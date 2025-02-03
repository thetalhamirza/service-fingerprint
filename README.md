# Service Fingerprint Scanner

A simple yet effective Python script designed to perform service banner grabbing from specified ports on a target IP. This script helps identify services running on open ports by retrieving their banners.

## Features

- **Service Banner Grabbing:** Connects to specified ports and retrieves service banners.
- **Custom Port Selection:** Allows scanning multiple ports by specifying them as comma-separated values.
- **Color-Coded Output:** Enhances readability with clear, color-coded messages.
- **Timeout Handling:** Ensures the script doesn't hang on unresponsive ports.

## Usage

```bash
python services.py <ip> -p <ports>
```

### Parameters:

- `<ip>`: The target IP address to scan.
- `-p`, `--ports`: Comma-separated list of ports to scan (e.g., `80,443,22`).

### Example:

```bash
python services.py 192.168.1.5 -p 21,22,80,443
```

This command scans ports **21, 22, 80, and 443** on IP `192.168.1.5` for service banners.

## Requirements

- **Python 3**
- **Libraries:**
    - `colorama`
    - `termcolor`

Install dependencies with:

```bash
pip install colorama termcolor
```

## How It Works

1. **Socket Connection:** Establishes a TCP connection to the specified ports.
2. **Banner Request:** Sends an HTTP request to trigger a banner response.
3. **Response Handling:** Captures and displays the banner if available.
4. **Timeout Control:** Skips ports that do not respond within 3 seconds.

## Example Output

```
[+] Scanning IP: 192.168.1.5
[+] Scanning port 80 on IP 192.168.1.5
[>] Service banner for port 80 on IP 192.168.1.5:
HTTP/1.1 200 OK
Server: Apache/2.4.29 (Ubuntu)
...

[+] Scanning port 22 on IP 192.168.1.5
[>] No service banner found for port 22 on IP 192.168.1.5
```

## Credits

Special thanks to **faanross** for the tutorial that inspired the development of this script.

## License

This project is for educational and ethical use only. Always ensure you have permission before scanning networks.
