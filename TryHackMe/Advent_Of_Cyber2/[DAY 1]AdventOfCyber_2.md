# Advent of Cyber 2 

A ctf write up by [https://tryhackme.com/p/presto](presto)

## [Day 1] A Christmas Crisis

After deploying your machine paste its IP Adress in the browser's search tab to see the web page below: 

![logging christmas](https://image.prntscr.com/image/bpvTboAZRMyRFfMq5W788Q.png)

You can create any diferent nickname and password combination but I will use "**presto**" in bot loggin inputs. After logged in the system web page we can press _F12_, acess the _Application_ tab and select the _Cookies panel_, after this it's possible to see a cookie with the following aspects: _name_, _value_ and _domain_ like in the image below:

![cookie tab](https://i.imgur.com/fPWqKiD.png)

In this case the value of the **auth** cookie is encrypted in hexadecimal code so if we convert to plaintext will be possible to see its real value: _{"company":"The Best Festival Company", "username":"presto"}_, which is formatted in JSON.

If we change our username from "presto", which is a simple user nickname to "santa", a root nickname and encrypt back to hexadecimal we will be able to acess the sysadmin management. Using [Cyber Chef](http://icyberchef.com/) the code will look like this: 

_7b22636f6d70616e79223a22546865204265737420466573746976616c20436f6d70616e79222c2022757365726e616d65223a2273616e7461227d_

Refreshing the page and activating all the controls in the system a flag will appears in the page: 

- **THM{MjY0Yzg5NTJmY2Q1NzM1NjBmZWFhYmQy}** 
