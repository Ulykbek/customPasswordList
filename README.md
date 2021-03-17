# customPasswordList
My custom password list


for i in $(cat password_list1); do echo $i; echo ${i}2019; echo ${i}2020; done > password_list2
hashcat --force --stdout password_list2 -r /usr/share/hashcat/rules/ > password_list3
hashcat --force --stdout password_list2 -r /usr/share/hashcat/rules/best64.rule -r /usr/share/hashcat/rules/toggles1.rule | sort -u | awk ‘length($0) > 8 ’ > password_list4
