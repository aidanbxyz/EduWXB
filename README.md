# EduWXB

SSWA Educational Weather Balloon

Code and diagrams for an educational weather balloon with optional experiment payloads

README.md is documentation for the code itself. For instructions and documentation on the EduWBX, use the [wiki](https://github.com/aidanbxyz/EduWXB/wiki)

## Payloads.txt Format

The purpose of Payloads.txt is so that you do not have to update the ground station program or change the source code in order to use a new or custom payload, you only have to add a line to Payload.txt.

Each line in Payloads.txt is formatted like:

```
ID,Name,[[Number of Hex Digits,Number of 10 Multipliers,'Units','Description']...]
```

Each payload has a unique ID. It can be one or two digits, but not three digits currently. The Name is the name of the payload kit, not the data that it transmits. Name is not in quotes. Next comes an array of the transmitted data. The array contains a smaller array for each data type transmitted that includes the number of hex digits it uses, the 10^x multiplier, the units, and a short description.

For example:

```
99,Example Payload,[[1,0,'DpM','Ducks Detected'],[2,1,'QpH','Duck Noises']]
```

The ID is 99 and the payload kit is called "Example Payload". It measures two fields. The first field uses only one hex digit and the second uses two hex digits. The first field has a 10^x multiplier of 0 and the second has 1. The units are 'DpM' and 'QpH' and the field descriptions are 'Ducks Detected' and 'Duck Noises'.

An example transmission for this payload would be `99a35`. It would be decoded as:

```
99 - Payload ID -> Example Payload
a  - First Field -> Ducks Detected = 10 DpM
35 - Second Field -> Duck Noises = 530 QpH
```