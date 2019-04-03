# Audit 2 JSON
This directory contains a script to convert auditd logs to json.The script can convert a single log line passed as an argument, or an entire log file.

### Setup
- Run ````pip3 install -r requirements.txt````

### Usage
See the following examples on how to use this script:

````
python3 audit2json.py -l "type=USER_CMD msg=audit(1501012518.198:52): pid=4188 uid=1000 auid=4294967295 ses=4294967295 msg='cwd="/home/steve" cmd=617564697463746C202D6120657869742C616C77617973202D4620706174683D2F6574632F706173737764202D46207065726D3D777261 terminal=pts/17 res=success"
````
This will output:
````
Running audit2json...

Converting line...

{
    "cmd": "auditctl -a exit,always -F path=/etc/passwd -F perm=wra",
    "terminal": "pts/17",
    "timestamp": "2017-07-25 19:55:18",
    "result": "success",
    "cwd": "/home/steve",
    "ses": "4294967295",
    "audit_user_id": "4294967295",
    "process_id": "4188",
    "user_id": "1000",
    "type": "USER_CMD"
}

Conversion completed!
````

Or using the script like this will convert the entire file and output it to json in output.json
````
python3 audit2json.py -f "/path/to/audit.log/" -o "/path/to/desired/output.json"
````
