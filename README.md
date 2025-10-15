# CCNA-router-on-a-stick

-pick a good ip range for the pcs make sure no overlap-

pc0 vlan 10 --> ip address=192.168.0.2, subnet mask=255.255.255.252, default gateway=192.168.0.1

pc1 vlan 20 --> ip address=192.168.0.6, subnet mask=255.255.255.252, default gateway=192.168.0.5

--------------------------------------------------------------------------------------------------

switch access layer

\>en

#conf t

fig#int ra f0/1-2

range-if#sw mo acc

range-if#exit

fig#vlan 10

vlan#exit

fig#vlan 20

vlan#name (name it what you want)

vlan#exit

fig#int f#/#

-To an end point-

if#sw mod access

if#sw acc vlan 10

-to the router/mls-

if#sw mod trunk

----------------------------------------------------------------------------------------------------

Router 

\>en

#conf t

fig#int g#/#.<vlan number> (int g0/0.10)

subif#enc dot <vlan number>

subif#ip address 192.168.0.1 255.255.255.252

subif#exit

fig#int g#/#.<vlan number> (int g0/0.20)

subif#enc dot <vlan number>

subif#ip address 192.168.0.1 255.255.255.252

----------------------------------------------

now the two pcs should be able to ping each other.
