This project successfully demonstrated how SSH and SCP work together to securely transfer files, how to capture and analyze encrypted SSH traffic in Wireshark, and how to troubleshoot unexpected behaviors like session termination anomalies.Secure Shell (SSH) is a network protocol that allows for secure remote access to another machine over an encrypted connection. In our setup:
The MacBook acts as the SSH server (listens for incoming connections).
The Dell acts as the SSH client (initiates the connection).

**🔑 How SSH Works in This Project**
1️⃣ The Dell (client) sends an SSH request to the MacBook (server), establishing an encrypted connection.
2️⃣ The MacBook responds, initiating an SSH handshake, where both devices agree on:
Supported encryption algorithms
Authentication methods
Session keys for encryption
3️⃣ Once the SSH session is established, the Dell requests a file transfer using SCP (Secure Copy Protocol), which runs over SSH.
4️⃣ The MacBook encrypts and transmits the file securely to the Dell.
5️⃣ Finally, the SSH session is terminated either gracefully (FIN/ACK) or forcefully (RST packet).

**📌 Key Insight:**
SSH ensures all data, including authentication and file transfers, remains encrypted, preventing eavesdropping.
SCP (Secure Copy Protocol) is a simple, secure way to transfer files over SSH.

**🔹 Project Objectives & Execution**
📝 Goals of the Project
✔️ Enable SSH on the MacBook and confirm it is listening for connections.
✔️ Use **Nmap** on the Dell to verify that SSH (port 22) is open and available.
✔️ Capture SSH session traffic in Wireshark to analyze encryption and connection behavior.
✔️ Perform an SCP file transfer from the MacBook to the Dell.
✔️ Investigate the SSH session closure to ensure the connection terminates properly.
✔️ Confirm encryption in Wireshark to verify that the file contents are never visible in plaintext.

