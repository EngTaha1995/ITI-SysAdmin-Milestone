## Win Server Notes :
-------
Every pc joined to domain can leave with local admin in login (./USERNAME) or DC admin user.

# WORKGROUP Vs Domain : 

Wokrgroup : is peer to peer connection, users are saved in  system32/config/SAM.
with local policies.

Domain : is Client / Server Connection, Users are saved on DC(Domain Controller).

# Remote connection with winServer :

SSH, Telnet, RSAT, Group Policy, Remote Desktop Connection.

# Partition Tables : 

	MBR Vs GPT 
	MBR (Basic Disks) : is limited only to four partitions.
	GPT (Dynamic Disks) : Changing Partitions sizes without restarting windows.
	GPT allow more than one hard disk to be used as one disk for extending storage
	GPT can make up to 128 partitions.


ReFS : new filesystem presented by Microsoft for more enhanced security / speed / large volume size or directories
maximizes reliability, Metadata integrity with ChekSum.

.vhd extension stands for virtual hardisk can be managed by diskpart.

# Disk Volumes : 

	Simple : uses free space on single disk.
	Spanned : uses free spaces from multiple disks.
	Striped (RAID 0): Spread across two or more physical disks.
	Mirrored (RAID 1) : (Fault tolerant) All data duplicated on two physical disks.
	RAID 5 : data is striped across three or more physical disks, parity aso striped across disk array.


# Various Notes : 

Ticketing system, when you save some policies to some users to use certain services like databases.

Always BackUp before upgrade.

ADC(Additional Domain Controller) : Takes copies of databases of active directories / users / configurations ...etc.

AD DS Schema : active directory database schema everything is accessed as an object (for advanced users of winServer only).

Powershell vs CMD : every cmd command can be run on powershell opposite isn`t true.

Sysprep : is a tool that makes windows back to default config (where you can config PC as newly installed windows).
you can also use sysprep to make multiple copies of windows for multi uses.

always close connection setting IPv6 when not used to prevent future problems.

SAM File is very secure as it contains users & passwords.

# NIC Teaming (Link aggregation) : 

To provide High-Availability(HA) to server using multiple networking cards.
Using certain protocols to use two or more NIC`s appear as one interface.
Also prevents failure and server down.
Doubling transfer speed of server & also services running on it.
Aggregate all nic`s as one NIC to be used by network.
NIC Teaming setting is present at Start screen of Server Manager.

# Server Storage




# Network setting for Domain Controller : 
DNS Server : 127.0.0.1 //LoopBack Address to connect to itself and request dns server.


# Powershell Commands : 

dir //list directories
cd //change directory
ipconfig //ip configurations
sconfig //server configurations
start powershell //open powershell for further configs
Get-NetFirewallprofile //show firewall status
Get-NetFirewallprofile | select name,Enabled // piping result
Set-NetFirewallprofile -profile Domain,public,private -Enabled Enabled //turn on firewall

# Disk Management :
	run diskmgmt.msc
	or use disks on server gui
	or use powershell dirctly using diskpart

#Spanned Volumes
	Created from free disk spaces on multiple volumes.

# RAID Tips :
	Parity info is about saved data across disks.
	RAID 10 (1+0) is about striped disks then mirrored as whole RAID 10 isnt supported by microsoft.
	RAID 6 using 6 disk to duplicate data as four copies with thier partiy info in ever disk.
	RAID 0 no raid at all ! data is striped in two disks.
	RAID 1 data is mirrored in two disks.
	RAID 5 (at least 3 disks) data is striped and mirrored in 5 disks.

# Logical or extended partition
	just one partition seen as multi partitions but only saved as one in partition table,
	to eleminated MBR limitation of 4 partitions.

* Disk Management in windows can apply RAID levels and other useful techniques.
*MBR Limited to partition extend only by freespace next to it or use(Spanned disk).
*GPT Disks are Dynamic disks can be extended by any free space on disk.
*Spanned Volume(partition) can use multpile disks on GPT Scheme!
*You Can create VHD (Virtual Hard disk) of any size based on multiple disks.
*Data Deduplication is available at windows server features.
*Data Deduplication is applied to chunks of files but not applied to databases.
