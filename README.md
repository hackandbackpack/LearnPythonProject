# LearnPythonProject
10 projects geared towards offensive security to help you learn Python.


Project 1 - The Scope!

Scenario: Congrats, your Penetration testing company Red Planet has landed an external assessment for Microsoft! Your point of contact has give you a few IP addresses for you to test. Like with any test you should always verify the scope given to you to make sure there wasn't a mistake.

Beginner Task: Write a script that will have the user input an IP address. The script should output the ownership and geolocation of the IP. The output should be presented in a way that is clean and organized in order to be added to your report.

Intermediate Task:  Have the script read multiple IP addresses from a text file and process them all at once.

Expert Task:Have the script read from a file containing both single IP addresses and CIDR notation, having it process it both types.

Here are your IP addresses to check:
131.253.12.5
131.91.4.55
192.224.113.15
199.60.28.111

For the Expert Task here are two networks in CIDR notation:
20.128.0.0/16
208.76.44.0/22

Project 2 - Web Header Reporting

Scenario: Red Planet has assigned you to do a web app penetration test against a few target domains. There are a few findings that your team regularly report on, but aren't very fun to detect or write up. As such, you are looking to automate this portion of your test so that you can spend more time going for something more critical. 

Beginner Task: Write a script that will have the user input a HTTPS URL. The script should pull down the web headers for the URL entered and report back if the Strict-Transport-Security header is missing. 

Intermediate Task: Have the script run multiple URLs from a file and process them all at once. Additionally, have it output both the URL and the IP address of each URL missing the Strict-Transport-Security header.

Expert: Have the code perform all of the tasks above while also checking for the Content-Security-Policy and X-Frame-Options header, also reporting back if they are missing. It should also detect if a Server header is present, if it is it should return the value of the header.

Bonus: Have the script evaluate if the URL is HTTP or HTTPS. If it is HTTP, it should ignore the need for a Strict-Transport-Security header while still evaluating all the others.


URLs to start with:
https://www.redsiege.com/
https://www.yahoo.com/
https://www.usbank.com/index.html
https://www.sidretail.com/
https://www.microsoft.com/en-us

Project 3 - Brute Force!

Scenario: You are working on an internal penetration test for Red Planet and have found a system that your point of contact labeled as "mission critical" has SSH enabled. Due to other findings on the network you know that the security administrator has weak passwords on lots of critical systems. Knowing this, you believe that you can password spray/brute force your way to victory.

Beginner Task: Write a script that will perform a password spray against the SSH service using a single username and password list. It should output each time a username/password combination is failed, and stop on a successful log in.

Intermediate Task: Give your script the added functionality to spray using a list of usernames and a single password, using lists for both usernames and passwords, as well as a traditional brute force options.

Expert Task: Add the option to limit login attempts based on time. Example, run 5 login attempts, wait 60 seconds, run 5 more attempts, wait 60 seconds, repeat.

In order to test this you will need a service running SSH. I suggest setting up something on your local network to test against. Be mindful when setting this up, if you put something internet facing with a weak username/password combination you run the risk at someone on the internet doing the same thing we are and getting popped.

If anyone has an issue building up something to test against I will setup a VPS and share. If you want to setup your own, Digital Ocean has hosts you can setup/rent for $5 a month, and if you've never done something like that before ... it is good experience. Something every pentester should be familiar with.

Project 4 - Pilfer for Passwords!

Scenario: While working with your teammates at Red Planet on an internal penetration test, you found lots of files spread across open SMB shares. Using another tool you have downloaded these files to your local machine. Now you need to find out if these files contain any sensitive data!

Beginner Task: Write a script that will search file names for files that could contain sensitive information. Names such as web.config, passwords.txt, SiteList.xml, etc.

Intermediate Task: Add functionality to the script that will enable it to search the contents of files for strings containing sensitive information like "password" "username", "apikey", etc.

Expert Task: Allow the user to specify the combinations of file names, types, and strings to search for. 

Bonus Task: Add recursive search.

For this task I would suggest creating several dummy files containing junk data and then a few with "sensitive" information. You don't need a pleothera of files to demonstrate if it works but I would suggest a few different common file types including txt, doc, docx, xls, xlsx, etc.

Project 5 - Living on the Land!

Scenario: You successfully delivered a phishing payload and now have access to a machine inside your target's network. It appears that your user is pretty locked down and you can't seem to get some of your favorite tools to run on the machine. Luckily for you, Python is installed on the machine and can be utilized in place of what's normally in your toolkit.

Beginner Task: Write a script that can perform a ping sweep of a range of IP addresses and port scan any host that responds.

Intermediate Task: Add "smart" functionality. Only port scan alive hosts, add functionality to allow the user to only scan the top 10, 100, 1000 Nmap ports. The list can be found in /usr/share/nmap/nmap-services if you have nmap installed on a system. sudo sort -r -k3 /usr/share/nmap/nmap-services

Advanced Task: Add some additional service enumeration based on open ports. This is a rabbit hole you can go down very deep. For this exercise, pick three different services and add some enumeration functionality of your choosing. 
