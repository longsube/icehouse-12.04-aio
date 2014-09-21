### E. C�I �?T TR�N COMPUTE NODE (COMPUTE1)
Luu �: C?n th?c hi?n bu?c t?i script t? github v? nhu hu?ng d?n ? bu?c B.1 v� B.2 (n?u c� thay d?i IP)
Th?c hi?n c�c shell du?i d? thi?t l?p hostname, g�n ip v� c�i d?t c�c th�nh ph?n c?a nove tr�n m�y COMPUTE NODE
- T?i c�c g�i c?n thi?t 
```sh
apt-get update

apt-get install git -y

git clone https://github.com/vdcit/openstack-3node-vdcit.git

mv /root/openstack-3node-vdcit/script-ubuntu1204/ script-ubuntu1204

cd script-ubuntu1204

chmod +x *.sh
```
#### E.1. �?t hostname, IP v� c�c g�i b? tr?


    bash com1-ipdd.sh

Sau khi th?c hi?n xong shell tr�n c�c NICs c?a COMPUTE NODE s? nhu sau: (gi?ng v?i khai b�o trong file 

<!--
<b><i>config.cfg</i></b>)

<table>
  <tr>
    <th>Hostname</th>
    <th>NICs</th>
    <th>IP ADDRESS</th>
    <th>SUBNET MASK</th>
    <th>GATEWAY</th>
    <th>DNS</th>
    <th>NOTE</th>
  </tr>
  <tr>
    <td rowspan="3">compute1</td>
    <td>eth0</td>
    <td>10.10.10.73</td>
    <td>255.255.255.0</td>
    <td>�? tr?ng</td>
    <td>�? tr?ng</td>
    <td>Ch? d? VMNET2</td>
  </tr>
  <tr>
    <td>br-ex</td>
    <td>192.168.1.73</td>
    <td>255.255.255.0</td>
    <td>192.168.1.1</td>
    <td>8.8.8.8</td>
    <td>Ch? d? bridge</td>
  </tr>
  <tr>
    <td>eth2</td>
    <td>10.10.20.73</td>
    <td>255.255.255.0</td>
    <td>�? tr?ng</td>
    <td>�? tr?ng</td>
    <td>Ch? d? VMNET3</td>
  </tr>
</table>
-->

COMPUTE node s? kh?i d?ng l?i, c?n ph?i dang nh?p b?ng t?i kho?n root d? th?c hi?n shell du?i
    

#### E.2. C�i d?t c�c g�i c?a NOVA cho COMPUTE NODE

�ang nh?p b?ng t�i kho?n root v� th?c thi c�c l?nh du?i d? ti?n h�nh c�i d?t nova

    cd script-ubuntu1204
	
    bash com1-prepare.sh

Ch?n YES ? m�n h�nh tr�n trong qu� tr�nh c�i d?t

![Alt text](http://i.imgur.com/jlRegTI.png)

K?t th�c bu?c c�i d?t tr�n COMPUTE NODE, chuy?n v? CONTROLLER NODE.