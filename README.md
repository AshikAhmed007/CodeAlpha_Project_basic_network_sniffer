
# 🐍 Packet Sniffer using Scapy

A simple yet effective Python-based packet sniffer that captures HTTP requests on a specified network interface using **Scapy**.

## 📌 Features

- Captures live network traffic
- Filters only HTTP requests
- Displays detailed packet information using `scapy`’s `show()` method
- Uses `scapy` and `scapy.layers.http` for deep packet inspection

## 🛠 Requirements

- Python 3.x
- `scapy` library

### Install Scapy

```bash
pip install scapy
```

## 🚀 Usage

### 1. Clone or download the script

```bash
git clone https://github.com/your-repo/packet-sniffer.git
cd packet-sniffer
```

### 2. Run the script with root privileges

```bash
sudo python3 sniffer.py
```

By default, it sniffs traffic on `eth0`. You can change the interface in the script:

```python
sniff('eth0')  # Replace 'eth0' with 'wlan0' or your actual interface
```

## 🧠 How It Works

- `scapy.sniff()` captures packets in real-time on a given interface.
- `process_packet()` filters HTTP requests using:
  ```python
  if packet.haslayer(http.HTTPRequest)
  ```
- Displays each matching packet using `packet.show()`.

## 🔐 Note

- This tool only captures **HTTP** traffic, not HTTPS.
- Run it with administrative/root privileges to access network interfaces.

## ⚠️ Disclaimer

Use this tool only on networks you own or have explicit permission to monitor. Unauthorized packet sniffing may be illegal.
