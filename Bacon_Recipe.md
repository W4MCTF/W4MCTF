Bacon_Recipe

## Brown Sugar (25)

The accounts received a suspicious email with attachments today, and after opening the attachment it was all gibberish to them.

After noticing some unusual behavior, scared of being infected, the operator shut down the system.

Here's the network log of the system in question:

bacon_recipe.pcapng

There is a free gift from the organizers, find it!

- PCAP: 

[bacon_recipe.pcapng](../_resources/ba697cad0b2c49458f816e9715cda1d0.pcapng)

Packet #88 is chock full of information! 

![flag.png](../_resources/702e9017773442a9b812a108ae51e641.png)

### FLAG: flag{g1f7_fr0m_th3_0rg4niz3r5}

* * *

## Morton Tender Quick (25)

Can you give a quick count on how many @bacon.threatsims.com emails are mentioned in the network log?

Back to Packet #88. Look throught the chat/email logs for email addresses. There will be several that are included that are *not* @bacon.threatsims.com. Disregard those and count only the unique addresses for the correct domain. 

Flag format: flag{N}

1. pwneip@bacon.threatsims.com
2. nopresearcher@bacon.threatsims.com
3. conehead@bacon.threatsims.com
4. rayhan0x01@bacon.threatsims.com
5. 0xsn1pe@bacon.threatsims.com
6. gocharan_@bacon.threatsims.com
7. accounts@bacon.threatsims.com

### FLAG: flag{7}

* * *

## Bacon Shipment (25)


Who sent the email with attachment?

Flag format: flag{email}

Once again, Packet #88 has the answer. 

Look for the message received by "accounts@bacon.threatsims.com". It should be one of the last objects in Packet #88. 

![sender-attachment-flag.png](../_resources/ed5fb6a959b741afb25e373ab6336dfe.png)

### FLAG: flag{payments@shipify.org}

The last thing present in Packet #88 is the attachment filename. 

Uncollapse the "Member Key: attachments" header to view information about the file that sent by payments@shipify.org. 


![file-name-attachment.png](../_resources/ab2c1e934354480ab9ad0d0a37b37cff.png)


* * *

## Bacon Delivery (25)

Once a known filename is found, use WireShark's "Export Objects" function to export "HTTP" files. 

File-> Export Objects-> HTTP.

A window opens that contains files found in the log's HTTP streams. 


![file-exportobjects-http-list.png](../_resources/d21f50fa70d7406c83c99049a82caa02.png)


Packet #513 contains the .xlsm spreadsheet. Select this packet from the list and click "Save". 

Open the file with any application that can read .xlsm files (i.e.- OpenOffice). 

The flag is easily located among some seemingly random garbage entries. 


![xls-file-flag.png](../_resources/21c76dbe318c409ab27e07cc04b805be.png)

### FLAG: flag{r3turn_0f_th3_m4cr0s_xlm_4.0}

* * *

## Bacon Unpacked (25)

Looks like the attackers deployed a Cobalt Strike c2 on the victim machine.

What is the full URL that delivered the initial payload?

Flag format: flag{http://ATTACKER/PATH}

The payload is likely a file, so using File->Export Objects->HTTP should again produce a list of files found in HTTP streams. If not, exporting objects from TFTP or SMB could be another source of information. 

In the list of files found in HTTP streams, one particular file has a name that just *sounds* like a payload: 

"gitgud"

![payload-file.png](../_resources/df9de1480840464cb18262e20f16d0ee.png)


**NOTE: THE FILE APPEARS TO BE ACTUAL MALWARE. HANDLE WITH CAUTION.**


* * *



