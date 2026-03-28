# HTB-Dancing---writeup-and-PT-report

# HTB — Dancing

![Difficulty](https://img.shields.io/badge/Difficulty-Very%20Easy-brightgreen)
![OS](https://img.shields.io/badge/OS-Windows-blue)
![Status](https://img.shields.io/badge/Status-Pwned-red)

## Machine Info

| Field      | Details              |
|------------|----------------------|
| IP         | 10.129.1.12          |
| OS         | Windows              |
| Difficulty | Very Easy            |
| Date       | 2026-03-28           |

## Summary

SMB share (WorkShares) on port 445/TCP accessible without
authentication. User directories exposed including sensitive files.

## Steps

1. Nmap scan → ports 135, 139, 445, 5985 open (Windows/SMB)
2. `smbclient -L 10.129.1.12 -N` → found WorkShares share
3. `smbclient \\\\10.129.1.12\\WorkShares -N` → connected without credentials
4. `ls` → found Amy.J and James.P directories
5. `get flag.txt` from James.P → submit flag

## Files

- `PT_Report_Dancing_Public.docx` — Full penetration test report
- `screenshots/` — Evidence screenshots
- `notes/` — Notes from the assessment
