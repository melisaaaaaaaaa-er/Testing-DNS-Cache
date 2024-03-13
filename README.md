# Testing DNS Cache

![8](https://github.com/melisa-er/Testing-DNS-Cache/assets/157723219/4b045f8a-cf71-4196-9682-038556d4a690)

![9](https://github.com/melisa-er/Testing-DNS-Cache/assets/157723219/f8640ccf-f0aa-4267-ad7f-29bd73ba6948)

Change the IP address record of mainframe from DC-1’s private IP address to 8.8.8.8.

#
![10](https://github.com/melisa-er/Testing-DNS-Cache/assets/157723219/b774e23e-2609-4b9f-889c-7b9cb76daea5)

![11](https://github.com/melisa-er/Testing-DNS-Cache/assets/157723219/f0a9ec80-1b14-432c-b2d1-65b2554f9d51)

On Client-1, ping mainframe again. Notice how the previous IP address is brought up even though the IP address has been changed.

This is because Client-1’s DNS cache is still storing the old mapping record. 

#
![12](https://github.com/melisa-er/Testing-DNS-Cache/assets/157723219/42a90b73-dad2-41dc-b837-0b9c11f5992b)

DNS caches do not change instantly when the records in a DNS server change. Typically, they don’t change at all unless the Time-To-Live (TTL) value of a record has been reached, after which a DNS server will be queried again, or a DNS flush is performed where all the records in a DNS cache are erased, forcing the host to query the DNS server, thus retrieving the new records.
Notice how the new  IP address is shown after the DNS flush.
