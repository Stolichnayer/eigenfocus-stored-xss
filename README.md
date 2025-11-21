# Stored Cross-Site Scripting (XSS) in Issue Title and Description Field

<table>
  <tr>
    <td width="150" rowspan="2">
      <a href="https://github.com/Eigenfocus/eigenfocus" target="_blank">
        <img src="https://avatars.githubusercontent.com/u/191941878?s=200&v=4" alt="Eigenfocus Logo" width="120"/>
      </a>
    </td>
    <td>
      <h1>Eigenfocus - Free Edition</h1>
      <h3> Self-Hosted Project Management and Time Tracking App</h3>
    </td>
  </tr>
  <tr>
    <td>
      <table>
        <tr>
          <td>
            🔗 <a href="https://github.com/Eigenfocus/eigenfocus" target="_blank">Eigenfocus Github Repository</span></a>
          </td>
          <td style="padding-left: 15px;">
            🚀 <a href="https://github.com/Eigenfocus/eigenfocus/releases/tag/v1.4.1-free" target="_blank"> Patched Version (v1.4.1) </span></a>
          </td>
        </tr>
      </table>
    </td>
  </tr>
</table>

## 📜 Description
Eigenfocus Free Edition ≤ 1.4.0 contains a stored Cross-Site Scripting (XSS) vulnerability in Issue Title and Time Entry Description fields. User-supplied input is not properly sanitized, allowing attackers to store malicious payloads that execute in the browser of any user who views the affected entries. This can lead to arbitrary JavaScript execution, session hijacking, account compromise, and other unauthorized actions. The issue is resolved in version 1.4.1.

## 🔍 Affected Versions

| Status       | Version         |
|--------------|-----------------|
| 🔴 Vulnerable |  ≤ `1.4.0`      |
| 🟢  Fixed     |  &nbsp;&nbsp;`1.4.1`      |   

## 🛠️ Steps to Reproduce

#### 1️⃣ Add a new time entry

#### 2️⃣ Enter the following payload:

```html
<img src=x onerror=alert('Description')>
```
<img src="/Timeentry_Description_Saving_Payload.png" >

#### 3️⃣ Click Edit to open the time entry in edit mode.

#### 4️⃣ The stored payload is rendered, and the alert executes:

<img src="/Timeentry_Description_Executing_Payload.png">

## ⚠️ Disclaimer
This project is intended for **educational and ethical research purposes only**. Unauthorized testing on systems without explicit permission is illegal. Use responsibly and only on systems you own or have permission to test.

## 🧑‍💻 Discovery

This vulnerability was discovered by **Alex Perrakis** (Stolichnayer).

## 🔗 References:
- [Eigenfocus Github Repository](https://github.com/Eigenfocus/eigenfocus)
- [Patched Version (v4.7.2)](https://github.com/Eigenfocus/eigenfocus/releases/tag/v1.4.1-free)
- [Fix Commit](https://github.com/Eigenfocus/eigenfocus/commit/7dec94c9d1f3e513e0ee38ba68caaba628e08582)

