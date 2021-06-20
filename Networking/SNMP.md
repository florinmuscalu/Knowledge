# Simple Network Management Protocol
- SNMP runs over **UDP** on ports 161/162.
- Traps are sent by the Agent running on the managed device over port **162**.
- Normal messages go back and forth between NMS and Agent over port **161**.
- It is used for transmitting management messages between two points.
- MIB (Management Information Base):
    - Abstract collection of managed objects.
	- Organized as a tree. Each managed object maps a leaf in the MIB tree.
	- The NMS reads and writes the data of managed devices from or into the MIB to manage the devices.
- Security
	- Communities define a collection of one SNMP agent and a group of SNMP managers for authentication and access control.
	- Authentication: if the community names match, the manager can operate the agent.
	- Each agent has two community names. One is read only (read community), the other one is read/write (write community).
	- Community names:
	    - Case sensitive.
		- Default read: public
		- Default write: private.
## SNMPv1 
Uses plain text community names for access.
## SNMPv2
Can use digest authentication, encryption and authorization.
## SNMPv3 
Supports the management of network security and access control.