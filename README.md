# EduWXB

SSWA Educational Weather Balloon

Code and diagrams for an educational weather balloon with optional experiment payloads

README.md is documentation for the code itself. For instructions and documentation on the EduWBX, use the [wiki](https://github.com/aidanbxyz/EduWXB/wiki)

## Payloads.txt Format

The purpose of Payloads.txt is so that you do not have to update the ground station program or change the source code in order to use a new or custom payload, you only have to add a line to Payload.txt.

Each line in Payloads.txt is formatted like:

```
ID,Name,[[Number of Hex Digits,Number of 10 Multipliers,Offset,'Units','Description']...]
```

Each payload has a unique ID. It should be two digits (00-99). The Name is the name of the payload kit, not the data that it transmits. Name is not in quotes. Next comes an array of the transmitted data. The array contains an array for each data type transmitted that includes the number of hex digits it uses, the 10^x multiplier, an offset, the units, and a short description.

For example:

```
02,Radiation,[[3,0,0,'CPM','Geiger Counter']]
```

The ID is 02 and the payload kit is called "Radiation". It measures one field that uses three hex digits, no 10^x multiplier and no offset.

An example transmission for this payload would look like `022c8`.

We have a website where you can play around with the format and check the formatting on custom payloads. This is located at [sswa.tv/projects/eduwxb.html](https://sswa.tv/projects/eduwxb.html). You can load example data or the current version of Payload.txt from this repo.
