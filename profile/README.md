<div align="center">

# Orbit OS

**A modern operating system built for edge devices and embedded systems.**

Orbit OS combines a powerful system runtime — **Gravity** — with a high-level SDK, giving developers full access to every hardware service through a clean, typed API over gRPC.

[![Website](https://img.shields.io/badge/Website-orbit--os.org-blue?style=for-the-badge)](https://orbit-os.org/)
[![Getting Started](https://img.shields.io/badge/Getting%20Started-Docs-green?style=for-the-badge)](https://orbit-os.org/getting_started.html)
[![Downloads](https://img.shields.io/badge/Downloads-Latest-orange?style=for-the-badge)](https://orbit-os.org/downloads.html)
[![YouTube](https://img.shields.io/badge/YouTube-@orbit--os--edge-red?style=for-the-badge&logo=youtube)](https://www.youtube.com/@orbit-os-edge)

</div>

---

## What is Orbit OS?

Orbit OS is an edge operating system designed for devices that need real-time hardware control, networking, AI inference, and application hosting — all from a single, unified runtime called **Gravity**.

Applications communicate with Gravity over gRPC, either on-device via a Unix socket or remotely over TCP+TLS. Every system capability is exposed as a service with a consistent, versioned API.

---

## Capabilities

| Category | Services |
|----------|----------|
| **Hardware I/O** | GPIO, I2C, SPI, UART, PWM, Camera |
| **Connectivity** | Wi-Fi, Ethernet, Bluetooth (BLE), VPN (WireGuard / OpenVPN) |
| **Security** | Auth, Firewall |
| **AI / ML** | ONNX & TFLite model loading, inference, streaming results |
| **System** | OTA Updates, Package Manager (ORB), Events, Power, System stats |
| **Apps** | AppHub — host and proxy WebUI applications through the Gravity portal |

---

## SDK

The official Go SDK exposes every Gravity service as a typed manager on a single client:

```go
c, err := client.NewClientAuto("192.168.1.100")

networks, _ := c.WiFiManager.Scan()
c.GpioManager.SetValue("GPIO17", client.GpioLevelHigh)

model, _ := c.AIManager.LoadModel("/models/yolov8n.onnx", "")
result, _ := model.RunInference(inputTensor)
```

→ [`OrbitOS-org/sdk-go`](https://github.com/OrbitOS-org/sdk-go) — `go get github.com/OrbitOS-org/sdk-go/v26`

---

## Get Started

- **[orbit-os.org](https://orbit-os.org/)** — product overview and documentation
- **[Getting Started](https://orbit-os.org/getting_started.html)** — set up your first Orbit OS device and build your first app
- **[Downloads](https://orbit-os.org/downloads.html)** — firmware images and tools
- **[YouTube — @orbit-os-edge](https://www.youtube.com/@orbit-os-edge)** — demos, tutorials and release walkthroughs
