<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Computer) (EVERYTHING IS DONE HERE)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Webserver (w/ URL Rewrite module installed)
- PHP
- MySQL database (w/ an account with full privileges)

<h2>Installation Steps:</h2>
Let's turn on IIS
<p>
<img src="https://i.imgur.com/mNMxUjz.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<h2>Open your control panel inside your VM and click on programs </h2>

</p>
<br />

<p>
<img src="https://i.imgur.com/cIQc9Jw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<h2>Next "Turn Windows Features on or off"</h2>
</p>
<br />

<p>
<img src="https://i.imgur.com/BNRK4fi.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<h2>From there we can check Internet Information Services (IIS)</h2>
</p>
<br />
<h2>osTicket needs PHP to work...</h2>
<p>
<img src="https://i.imgur.com/Orh3bYC.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<h2>While we're here let's enable CGI</h2>
</p>
<br />

<h2>Next we'll have to create the directory C:\PHP</h2>
Go to your File explorer click on your C: drive 
<p>
<img src="https://i.imgur.com/98qb7Hl.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create a new folder.
</p>
<br />

<p>
<img src="https://i.imgur.com/OiP6k2l.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Name it "PHP". You can right click the folder and rename it if you messed up.
</p>
<br />


<p>
<img src="https://i.imgur.com/PU9556R.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
This is where all the binaries for php are going to go.
</p>
<br />

Now we need to put the binaries into the folder we just created.
<p>
<img src="https://i.imgur.com/eERtYi2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
That's it for PHP 
</p>
<br />

Next we'll have to install PHP Manager
<p>
<img src="https://i.imgur.com/d5UGDEe.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Since osTicket is a PHP application we need this so everything will run smoothly.
</p>
<br />

Now we're going to install the URL rewrite module

<p>
<img src="https://i.imgur.com/aJWkkj7.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
This makes osTicket easier to use and helps it handle requests properly.
</p>
<br />

We'll also need a Visual C++ Redistributable (we're using the x86 version here)
<p>
<img src="https://i.imgur.com/OIwRU8X.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
This is essentially for compatibility purposes.
</p>
<br />

<h2>Finally, our last prerequisite </a>☺</h2>
Let's set up our MySQL server 
<p>
<img src="https://i.imgur.com/OCvYwgI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
All of our data will be stored here (user accounts and management, ticketing information, configurations, etc)
</p>
<br />

When you get to this page ↓
<p>
<img src="https://i.imgur.com/WCB5OHT.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Choose the "Typical" setup and click next
</p>
<br />

As we finish setting this up we'll launch the configuration wizard
<p>
<img src="https://i.imgur.com/1WzwY1J.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
This'll make the process of setting up our sever alot easier
</p>
<br />

When you get to this page ↓
<p>
<img src="https://i.imgur.com/FpjB1h8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Choose "Standard Configuration"
</p>
<br />

Then make sure "Install As Windows Service" is checked
<p>
<img src="https://i.imgur.com/KBU2Vrb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

For the security options make sure the first box is checked and create your password. DON'T FORGET IT!!!!! Write it down if you have to.
<p>
<img src="https://i.imgur.com/4GuBEcd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
This is that account with full privileges that we need!
</p>
<br />

<h2>Now we're going to register PHP inside of IIS</h2>
If we dont then we wont be able to run osTicket.
Go to your desktop and search "IIS"
<p>
<img src="https://i.imgur.com/W3sONpH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

From here we should be able to run IIS as an admin
<p>
<img src="https://i.imgur.com/mBq1FIl.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

Now lets open PHP manager
<p>
<img src="https://i.imgur.com/OskzJUA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

Inside lets click "Register New PHP version"
<p>
<img src="https://i.imgur.com/eDnqOBg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
This lets our webserver (IIS) execute php scripts.
</p>
<br />

We'll need to find the file php-cgi.exe in our directory C:\PHP we setup earlier
<p>
<img src="https://i.imgur.com/IOF0gP6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />


<p>
<img src="https://i.imgur.com/cICfQUx.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />


<p>
<img src="https://i.imgur.com/Tx4IJyr.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

Now we need to restart IIS.
<p>
<img src="https://i.imgur.com/p62q9HE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />


<p>
<img src="https://i.imgur.com/jvWUHv5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
This makes sure that our changes are applied to the servers configuration settings
</p>
<br />

<h2>Now we can finally install osTicket </a>☺</h2>

Unzip osTickets file
<p>
<img src="https://i.imgur.com/PeeVNTE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
<img src="https://i.imgur.com/lrirMRG.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<h2>Now we have to copy the upload folder into our wwwroot directory</h2>
Lets find it
<p>
<img src="https://i.imgur.com/D8d3Zuk.png" height="30%" width="30%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
<img src="https://i.imgur.com/c5NB1ce.png" height="30%" width="30%" alt="Disk Sanitization Steps"/>
</p>
<br />

Now we have to drag the "upload" folder into the "wwwroot" folder
<p>
<img src="https://i.imgur.com/rG1nI7E.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
This will let your users reach osTicket through a browser.
</p>
<br />

<h2>Rename the upload folder osTicket</h2>
Right click on the "upload" folder and click "Rename"
<p>
<img src="https://i.imgur.com/iYDC2JU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

Now type "osTicket" EXACTLY. You can copy and paste it if you need to.
<p>
<img src="https://i.imgur.com/6N3YtXo.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
This will help by giving us a straightforward url structure. (You'll see later)
</p>
<br />

Now we need to restart IIS again.
<p>
<img src="https://i.imgur.com/jvWUHv5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<h2>Let's access our website through our IIS.</h2>

We'll follow the same steps we took before... (If you don't remember how to get to IIS you can look [here](https://github.com/vinohef/osticket-prereqs/tree/main?tab=readme-ov-file#now-were-going-to-register-php-inside-of-iis). Once IIS is open come back!

<p>
<img src="https://i.imgur.com/6MzDvKr.png" height="30%" width="30%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
<img src="https://i.imgur.com/G9CnTGV.png" height="30%" width="30%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
<img src="https://i.imgur.com/yAfNFcX.png" height="30%" width="30%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
<img src="https://i.imgur.com/UBwYhBB.png" height="30%" width="30%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
<img src="https://i.imgur.com/sYedzao.png" height="30%" width="30%" alt="Disk Sanitization Steps"/>
</p>
<br />

You should see something like this...

<p>
<img src="https://i.imgur.com/8064b39.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

osTicket will run alot better if we enable a couple of these extensions

<p>
<img src="https://i.imgur.com/NlQg3zn.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
<img src="https://i.imgur.com/ugq0SfV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
<img src="https://i.imgur.com/BWn78mZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
<img src="https://i.imgur.com/Zkf5tJA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

Now if we refresh our browser we can see...

<p>
<img src="https://i.imgur.com/NrGiOh4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Some of the features have checkmarks next to them now!
</p>
<br />
We dont need ALL of them enabled. OsTicket will run just fine without the last two. 
<br />

<h2>We setup our MySQL database already. Its common to have HeidiSQL so we can actually manage our database without needding to know SQL.</h2>

Pretty straightforward

<p>
<img src="https://i.imgur.com/ZY4n0gX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />


<p>
<img src="https://i.imgur.com/IAQtTRi.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
<img src="https://i.imgur.com/CTLDgFy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
<img src="https://i.imgur.com/RzlB65x.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
<img src="https://i.imgur.com/lN9tnrp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
<img src="https://i.imgur.com/NRZWMkg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

Make sure "Launch HeidiSQL" is checked

<p>
<img src="https://i.imgur.com/o9piZ5u.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

Do you remember your Password when you setup MySQL????

<p>
<img src="https://i.imgur.com/ns55zn3.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
<img src="https://i.imgur.com/iU5xuMJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />


<p>
<img src="https://i.imgur.com/X0JaeUj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />


<p>
<img src="https://i.imgur.com/usqr1qW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />


<p>
<img src="https://i.imgur.com/F7bgiGg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />


<p>
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />


<p>
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />


<p>
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />


<p>
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />


<p>
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />


<p>
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />


<p>
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />


<p>
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />


<p>
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />


<p>
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

