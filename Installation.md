1. Convert text to number with RegEx, Zabbix preprocessing [https://catonrug.blogspot.com/2019/01/convert-text-to-number-zabbix-preprocessing.html]

2. install jq utility to list JSON data more beautifully:
### curl -sL https://github.com/stedolan/jq/releases/download/jq-1.5/jq-linux64 -o /usr/bin/jq && chmod +x /usr/bin/jq

3. Test if there is nice service list with nice additional attribute {#STATUS}:
### echo "{\"data\":[$(systemctl list-unit-files|grep "\.service"|grep -v "@"|sed -E -e "s/\.service\s+/\",\"{#STATUS}\":\"/;s/(\s+)?$/\"},/;s/^/{\"{#NAME}\":\"/;$ s/.$//")]}" | jq .

4. UserParameter:
### cd /etc/zabbix/zabbix_agentd.d
