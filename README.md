# FinalKM
REMOTE DESKTOP SERVICES (RDS)
MS technology that allows users to remotely access apps & desktops securely from anywhere.
RDS DEPLOYMENT TYPES
1. Session Based
Multiple users share single server
Cost effective
Shared resources
2. VDI (Virtual Desktop Infrastructure)
Dedicated VM for each user
Personalized desktop
Better performance & isolation

RDS ROLES
RD Session Host (RDSH)
Runs apps/desktops for users using RDP
Multiple users connect to single server
Formerly Terminal Services
RD Connection Broker
Load balancing
Session assignment
Reconnect disconnected sessions
RD Web Access
Web portal for accessing RDS resources
RD Gateway
Secure internet access to RDS
No VPN required
Uses HTTPS/443
RD Licensing
Issues & tracks RDS CALs
Enforces licensing policy

RDS ENCRYPTION LEVELS
Low (0)
Only client → server encrypted
56-bit
Not recommended
Client Compatible (1)
Uses max encryption supported by client
High (2)
128-bit encryption
Client must support 128-bit
FIPS Compliant (3)
Highest security
Uses FIPS-approved encryption

RDP SECURITY LAYER
Determines authentication/security before RDP session.
RDP Security Layer (0)
Uses native RDP authentication
Negotiate (1) DEFAULT
Client & server negotiate best method
SSL/TLS (2)
Uses TLS authentication
More secure
TLS
Secures communication channel
Verifies server identity
Encrypts traffic

RDS CALs
PER DEVICE
Assigned to device
Tracked by LS
Temp CAL available
Can revoke 20%
Cannot overallocate
PER USER
Assigned to AD user
Not fully tracked
No temp CAL
Cannot revoke
Can overallocate

COLLECTION
Pool/set of RD Session Hosts.

Multiple hosts possible
One host cannot belong to multiple collections

Collection Config
Security layer
Encryption
Load balancing
RDP settings
Security groups

DRAIN MODE
Blocks new connections
Existing users continue

GRACEFUL SIGNOUT
Proper logout from Session Host
Prevents profile/session issues

QWINSTA
Command used to check active/disconnected sessions

USER PROFILE DISK (UPD)
Alternative to roaming profiles.
Stores profile in VHD/VHDX
Attached at login
Detached at logout
Faster login/logoff
Stored on SMB share
Collection specific
Single connection only

RDS AUTHENTICATION
Kerberos
Ticket-based auth
Uses symmetric encryption
Built into AD
No password sent over network

NTLM
Used when Kerberos unavailable
Default on RD Gateway over WAN

CredSSP
Authenticates client & server
Secure credential delegation

SPNEGO (Negotiate)
Chooses Kerberos or NTLM
Creates shared session key

AUTH FLOW SUMMARY
TLS secures channel
SPNEGO selects Kerberos/NTLM
Mutual authentication
Public key validation
Credentials delegated securely
Session established
