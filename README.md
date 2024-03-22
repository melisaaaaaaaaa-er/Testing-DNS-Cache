# Testing DNS Cache

<h3>Purpose</h3>

- Observe and test the functioning of DNS cache on Windows Server.

#
<img src="https://raw.githubusercontent.com/melisaaaaaaaaa-er/dns-images/main/8.png"/>

<img src="https://raw.githubusercontent.com/melisaaaaaaaaa-er/dns-images/main/9.png"/>

Change the IP address record of mainframe from DC-1’s private IP address to 8.8.8.8.

#
<img src="https://raw.githubusercontent.com/melisaaaaaaaaa-er/dns-images/main/10.png"/>

<img src="https://raw.githubusercontent.com/melisaaaaaaaaa-er/dns-images/main/11.png"/>

On Client-1, ping mainframe again. Notice how the previous IP address is brought up even though the IP address has been changed.

This is because Client-1’s DNS cache is still storing the old mapping record. 

#
<img src="https://raw.githubusercontent.com/melisaaaaaaaaa-er/dns-images/main/12.png"/>

Input the command "ipconfig /flushdns".

DNS caches do not change instantly when the records in a DNS server change. Typically, they don’t change at all unless the Time-To-Live (TTL) value of a record has been reached, after which a DNS server will be queried again, or a DNS flush is performed where all the records in a DNS cache are erased, forcing the host to query the DNS server, thus retrieving the new records.

Notice how the new  IP address is shown after the DNS flush.
