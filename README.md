# Website-Blocker

## Use Case
This is a simple python script that we can be used by Organization in their offices computers to block certain webistes for example www.bing.com or www.facebook.com during their working hours.

## How to run the program
**Please take a backup of your hostfile before running the script.**

You can directly excute the script website_blocker.py using the command:
```
	python website_blocker.py
```

## Functionality

The program first check the current time using the daytime module in python

* If the time is between the working hour of organization it will add the webistes from the website list to the host file of computer.

```python
with open(host_path, 'r+') as file:
            content = file.read()
            for website in website_list:
                if website in content:
                    pass
                else:
                    file.write(redirect+" "+website+"\n")

```


* If the current time is offtime in the organization the program will check the website in host file and remove it if it exist in the file.

```python
with open(host_path, 'r+') as file:
            content = file.readlines()
            file.seek(0)
            for line in content:
                if not any(website in line for website in website_list):
                    file.write(line)
            file.truncate()

```

## Contributing 
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.




