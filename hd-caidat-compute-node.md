### E. CÀI Ð?T TRÊN COMPUTE NODE (COMPUTE1)
Luu ý: C?n th?c hi?n bu?c t?i script t? github v? nhu hu?ng d?n ? bu?c B.1 và B.2 (n?u có thay d?i IP)
Th?c hi?n các shell du?i d? thi?t l?p hostname, gán ip và cài d?t các thành ph?n c?a nove trên máy COMPUTE NODE
- T?i các gói c?n thi?t 
```sh
apt-get update

apt-get install git -y

git clone https://github.com/vdcit/openstack-3node-vdcit.git

mv /root/openstack-3node-vdcit/script-ubuntu1204/ script-ubuntu1204

cd script-ubuntu1204

chmod +x *.sh
```
#### E.1. Ð?t hostname, IP và các gói b? tr?


    bash com1-ipdd.sh

Sau khi th?c hi?n xong shell trên các NICs c?a COMPUTE NODE s? nhu sau: (gi?ng v?i khai báo trong file 

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
    <td>Ð? tr?ng</td>
    <td>Ð? tr?ng</td>
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
    <td>Ð? tr?ng</td>
    <td>Ð? tr?ng</td>
    <td>Ch? d? VMNET3</td>
  </tr>
</table>
-->

COMPUTE node s? kh?i d?ng l?i, c?n ph?i dang nh?p b?ng t?i kho?n root d? th?c hi?n shell du?i
    

#### E.2. Cài d?t các gói c?a NOVA cho COMPUTE NODE

Ðang nh?p b?ng tài kho?n root và th?c thi các l?nh du?i d? ti?n hành cài d?t nova

    cd script-ubuntu1204
	
    bash com1-prepare.sh

Ch?n YES ? màn hình trên trong quá trình cài d?t

![Alt text](http://i.imgur.com/jlRegTI.png)

K?t thúc bu?c cài d?t trên COMPUTE NODE, chuy?n v? CONTROLLER NODE.