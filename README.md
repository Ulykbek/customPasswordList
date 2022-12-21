# customPasswordList with JTR Custom Rules
My custom password list


Edit file password_list1, enter main words from which a complex password will be constructed.
```
for i in $(cat password_list1); do echo $i; echo ${i}2019; echo ${i}2020; echo ${i}2021; echo ${i}2022; done > password_list2
```

```
hashcat --force --stdout password_list2 -r /usr/share/hashcat/rules/ > password_list3
```

```
hashcat --force --stdout password_list2 -r /usr/share/hashcat/rules/best64.rule -r /usr/share/hashcat/rules/toggles1.rule | sort -u | awk ‘length($0) > 8 ’ > password_list4
```
