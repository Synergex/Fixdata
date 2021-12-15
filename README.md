# Fixdata<br />
**Created Date:** 10/23/2009<br />
**Last Updated:** 10/12/2010<br />
**Description:** This program will read through a Synergy DBMS file, and will modify data to match the repository definition. The program requires the Repository data files and two of three other pieces of information: SDBMS filename and RPS structure or RPS filename (and optionally RPS structure) (Update for Synergy 9.5 compatibility)<br />
**Platforms:** Windows; Unix; OpenVMS<br />
**Products:** Synergy DBL; Repository<br />
**Minimum Version:** 9.1.5b<br />
**Author:** William Hawkins
<hr>

**Additional Information:**
If you provide SDBMS filename and RPS structure, the entire file will be
processed using the provided RPS structure. Note, if structure tags are
defined, only matching records will be processed.

If you provide RPS filename, the file will be processed using the assigned
structures. It will use the RPS structure tags to apply each structure to
it's appropriate record. If you do not have tags defined, and you have
multiple structures assigned to the RPS file, the last structure wins. You
can restrict the processing to just a single structure, by specifying the
RPS structure name, note tags (if present) still apply. The RPS file must
be "DBL ISAM" if the file is a SDBMS isam file, any other value will treat
the file as a relative file.

Overlay fields are ignored.

Currently, only Synergy decimal fields are processed.

Dates with a 4 digit year, and the year < 1900 are treated as invalid.

Compiler command: DBL fixdata
Link command DBLINK fixdata WND:tklib.elb, RPSLIB:ddlib.elb
