# SpoolerScanner
Check if the spooler (MS-RPRN) is remotely available with powershell/c#

This is a follow-up of the DerbyCon presentation "The Unintended Risks of Trusting Active Directory @ DerbyCon 2018" made by @tifkin_ (Lee Christensen), @harmj0y(Will Schroeder), @enigma0x3(Matt Nelson)

Reference:
- https://www.slideshare.net/harmj0y/derbycon-the-unintended-risks-of-trusting-active-directory
- https://github.com/leechristensen/SpoolSample
- https://adsecurity.org/?p=4056
- https://msdn.microsoft.com/en-us/library/cc244528.aspx

As an alternative, it can be tested by OpenPrinter but the API does not clearly expose if the parameter is incorrect or if the service is unaccessible.

My understanding of the spooler API is:
- if you share a printer on the network, the spooler is remotely accessible on the computer sharing the printer
- on a domain, the DC spooler may be accessible after the printer has been shared. A restart of the service on the DC switch it to an unavailable state until the printer is browser on the DC (like in the explorer when browsing a computer and its printer)
- else the printer is not available

