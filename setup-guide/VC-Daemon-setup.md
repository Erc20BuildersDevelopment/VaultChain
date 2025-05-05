# 🛠️ VaultChain Daemon Setup Guide

This guide walks you through setting up the **VaultChain Daemon**, a core component that enables your system to interact with the VaultChain network, participate in staking, and perform validation tasks.

---

## 📍 Step 1: Locate the VaultChain Daemon

Navigate to the directory where VaultChain binaries are stored:

```
VaultChain_Software/bin
```

In this folder, you will find compiled essential software for the VaultChain network. Look specifically for:

```
VaultChain-Daemon-[VERSION]
```

> 🔍 **Tip:** Multiple versions may be available. Review the changelogs or accompanying release notes to determine:
> - Stability
> - Known issues
> - Fixes specific to your platform or network version
>
> Choosing the correct version ensures compatibility and optimal performance.

---

## 📦 Step 2: Download the Daemon Build Folder

Once you've chosen a version:
1. Download the entire `VaultChain-Daemon-[VERSION]` **build folder**.
2. Save it in a directory where you intend to run the daemon.

Ensure the **whole folder** is preserved during download. It contains:
- The executable
- Essential libraries (`.dll`, `.so`, `.dylib`, etc.)
- Configuration templates

---

## 🗃️ Step 3: Unpack the Folder

After download, unpack the folder if it's compressed (`.zip`, `.tar.gz`, etc.) using your OS’s archive tool or a utility like:

- Windows: [7-Zip](https://www.7-zip.org/)
- macOS: The default Archive Utility
- Linux: `tar`, `unzip`, etc.

The unpacked directory should resemble:

```
VaultChain-Daemon-1.2.3/
├── VaultChainDaemon.exe     # Main executable
├── libssl-3.dll             # Required dependency
├── daemon_config.yaml       # Default configuration file
├── README.txt
└── ...
```

---

## 🚫 DO NOT MODIFY THE FOLDER STRUCTURE

> ⚠️ **WARNING:**  
> Do **not rename, move, or alter** the contents of the build folder.
>
> The VaultChain Daemon relies on internal references and paths to locate:
> - **Dynamic libraries** (DLLs / shared objects)
> - **Configuration files**
> - **Execution dependencies**
>
> Any changes may **break functionality**, cause **startup errors**, or disrupt **network communication**.

---

## 🚀 Step 4: Run the Daemon

Open a terminal or command prompt and navigate into the folder:

```bash
cd VaultChain-Daemon-1.2.3
```

Then run the executable:

- On **Windows**:
  ```cmd
  VaultChainDaemon.exe
  ```

- On **Linux/macOS**:
  ```bash
  ./VaultChainDaemon
  ```

> 🔄 On first launch, the daemon may:
> - Generate initial configuration
> - Sync with the VaultChain network

The more you let it sync the more VaultChain Tokens you will gain for contributing on the network.

---

## ✅ Success!

Once successfully launched, the VaultChain Daemon will:
- Connect to peers in the VaultChain network
- Expose a local RPC or CLI interface (depending on config)
- Enable staking, validation, and other operations

You are now ready to stake or run Validator services on VaultChain!

---

## 🧩 Troubleshooting

- **Daemon doesn't start?**
  - Ensure you're in the correct directory
  - Check for missing libraries (use `ldd` on Linux or Dependency Walker on Windows)
  - Re-download the full build if needed

- **Firewall or connection issues?**
  - Allow the executable through your firewall
  - Ensure port access (check `daemon_config.yaml` for defaults)