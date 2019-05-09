# Development Ideas

## Regarding ddosdb.nl:
- v1.0
	- give access to whitelisted people
	- connect ddosdb.org and ddosdb.nl (in a single way)
	- create sub-groups
	- create rules for making ‘some information’ available to only a specific group
- v2.0
	- add a dashboard to the system
	- create a feed to contact CERT/CSIRT (via shadow server?)
	- test feeds with CERTS in The Netherlands

## Regarding DDoS Fingerprint Parsers/Converters:
- v1.0:
	- Create a converter based on the main tool used by the clearinghouse: BGP flowspec? a specific Firewall?
	- create a module to measure the impact of the detection/mitigation rule
- v2.0:
	- Create a converter based on the 2nd main tool used by the clearing house;
	- improve the DDoS rule impact module

## Regarding DDoS Dissector:
- v1.0: Based on (1) ONE Destination IP address; (2) Transport Protocol; (3) Source and Destination Ports; (4) Application Protocol; (5) at least ONE specific field of the application protocol; (6) indication of spoofing; (7) enrichment on the AS level; (8) enrichment on the geolocation (country level); (9) enrichment on the open ports (using shodan); 
	- cover the main types of volumetric and semantic-based attacks (top X);
	- for each protocol used in the attacks, it should extract at least one ‘additional field’;
	- add an indication whether we find evidences of IP spoofing or not;
	- add the number of packets sent by each IP;
	- enrich the IP to AS 
	- enrich the IP or the AS to Geolocation (country)
	- cover input types: pcap and netflow/ipfix;
	- anonymize (dst_ip,  ‘dst_ip in the payload’, MAC address, and the time);
	- make ‘attack_starttime’ field as a ‘private field’ (in ddosdb);
		- suggestion: backup scenario;
		- cert to cert!
		- put the sidn legal, kpn legal,   
	- add the possibility of including annotation from the operator;

- v2.0 improving v1.0 by adding (1) MULTIPLE destination IP addresses; (2) more input information from the operator  about the target machine; (3) include sflow as input file; (4) analyse all the field of the filtered anonymised DDoS attack; 
	- solve possible operator mistakes (flash crowd ‘attacks’)
	- add sflow as input file
	- analyse all the fields in the filtered attack (for identifying additional valuable information) 

## Rights
- User: can see, query and download (fingerprint and filtered anonymised data)
- Collaborator: is a user that can upload (fingerprints and filtered anonymised data) AND get the automatically generated rules
- Maintainer: is a collaborator that that
