# CBT1016
Converted to GitHub via [cbt2git](https://github.com/wizardofzos/cbt2git)

This is still a work in progress. GitHub repos will be deleted and created during this period...

```
//***FILE1016 is from Steve Myers and contains some of the uniquely *   FILE1016
//*           written TSO commands that he has produced.            *   FILE1016
//*                                                                 *   FILE1016
//*           email:  Steve Myers <mvsprog@yahoo.com>               *   FILE1016
//*                                                                 *   FILE1016
//*     A description of the contents of this file, follows:        *   FILE1016
//*                                                                 *   FILE1016
//*     This data set contains a mashup of Steve Myers' TSO         *   FILE1016
//*     commands.  Each command is packaged as an unloaded PDS;     *   FILE1016
//*     retrieve the PDS using the RECEIVE command, for example:    *   FILE1016
//*                                                                 *   FILE1016
//*     RECEIVE INDATASET('hlq.TSOCMND.CBT.PDS(DSSTAT)')            *   FILE1016
//*                                                                 *   FILE1016
//*     Note:  The latest versions of the REVIEW TSO command        *   FILE1016
//*            (File 134 - source, File 135 - load), if later       *   FILE1016
//*            than version 51.3) can expand an XMIT-format         *   FILE1016
//*            file.  Just REVIEW the file, and all the members     *   FILE1016
//*            will be expanded.  This will speed up the process    *   FILE1016
//*            of viewing all these members.  Just REVIEW them..!!  *   FILE1016
//*                                                                 *   FILE1016
//*     Each PDS has more detailed documentation about the          *   FILE1016
//*     command and how to prepare, install and use the command.    *   FILE1016
//*                                                                 *   FILE1016
//*     The default name of the PDS allocated by the RECEIVE        *   FILE1016
//*     command is userid.command.CBT.PDS.  If possible, use        *   FILE1016
//*     this name as it will make preparation of the command        *   FILE1016
//*     easier as the data set name will match the data set         *   FILE1016
//*     name used in the documentation.                             *   FILE1016
//*                                                                 *   FILE1016
//*     Member                                                      *   FILE1016
//*     $DOC     - This member                                      *   FILE1016
//*     ALLOCVOL - ALLOCVOL simulates a volume definition DD        *   FILE1016
//*                statement used by some IBM batch utilities.      *   FILE1016
//*     DSSTAT   - A command loosely modeled on the IBM LISTDS      *   FILE1016
//*                command, but with more detailed, and in my       *   FILE1016
//*                opinion, more useful output.                     *   FILE1016
//*     FINDCMD  - TSO command to report the library where a        *   FILE1016
//*                TSO command, or any binary program, can be       *   FILE1016
//*                found.  findcmd asma90                           *   FILE1016
//*                 ASMA90 IN LINKLIST ASM.SASMMOD1                 *   FILE1016
//*                 READY                                           *   FILE1016
//*                findcmd iefactrt                                 *   FILE1016
//*                 IEFACTRT IN MLPA                                *   FILE1016
//*                 READY                                           *   FILE1016
//*     FREESYS  - TSO command to free all SYSnnnnn allocations,    *   FILE1016
//*                where nnnnn is 5 numerics.                       *   FILE1016
//*     IDUMP    - TSO command to create an image dump of one or    *   FILE1016
//*                more tracks of a data set.                       *   FILE1016
//*     INVCP    - TSO command to run a program in the link         *   FILE1016
//*                list or a private library as a TSO command.      *   FILE1016
//*                With the TSOLIB TSO command, the need for        *   FILE1016
//*                something like INVCP is limited.                 *   FILE1016
//*     KEEPITUP - A TSO command processor to keep your TSO         *   FILE1016
//*                session active with no terminal activity.        *   FILE1016
//*                It periodically updates your screen with the     *   FILE1016
//*                current date & time and the time your            *   FILE1016
//*                session has been active.  Many installations     *   FILE1016
//*                discourage or forbid the use of a tool like      *   FILE1016
//*                this; verify it is OK with your management       *   FILE1016
//*                before using KEEPITUP.                           *   FILE1016
//*     LISTTSOU - List TSO users currently logged on.              *   FILE1016
//*                listtsou asid                                    *   FILE1016
//*                 THE FOLLOWING TSO USERS ARE CURRENTLY ACTIVE -  *   FILE1016
//*                  BENMAR(X'003E') SMYERS(X'002D')                *   FILE1016
//*     LMATTR   - List a simplified module map of load modules.    *   FILE1016
//*     LOGTIMED - List logon information about your TSO session.   *   FILE1016
//*     RESETPDS - Delete all members of a PDS or PDSE, and         *   FILE1016
//*                arrange a PDS so the next member added to the    *   FILE1016
//*                data set immediately follows the directory.      *   FILE1016
//*     TIOT     - A TSO command to list the TIOT for your TSO      *   FILE1016
//*                session.  A useful enhancement is TIOT lists     *   FILE1016
//*                the current EXCP count for each DD statement.    *   FILE1016
//*                tiot f(sys0)                                     *   FILE1016
//*                 SMYERS QCBTPROC QCBTPROC                        *   FILE1016
//*                 SYS00047 5103 CBT004 10 SMYERS.LOAD             *   FILE1016
//*                The 10 between the volume serial and data        *   FILE1016
//*                set name is the current EXCP count for the       *   FILE1016
//*                DD.  This is not as useful as one might          *   FILE1016
//*                expect as z/OS frequently resets these           *   FILE1016
//*                counters.                                        *   FILE1016
//*     TSO      - A command that will execute the command          *   FILE1016
//*                string that follows the TSO command.  TSO is     *   FILE1016
//*                a convenience for TSO users accustomed to        *   FILE1016
//*                entering TSO command on an ISPF Command line     *   FILE1016
//*                when in TSO READY.                               *   FILE1016
//*     TSOLPDIR - (alias LISTPDS) A TSO command to list PDS        *   FILE1016
//*                directory entries.  When run in TSO in batch,    *   FILE1016
//*                TSOLPDIR is a useful replacement for the         *   FILE1016
//*                IEHLIST LISTPDS command without requiring the    *   FILE1016
//*                the difficult JCL setup and the                  *   FILE1016
//*                VOL=device-type=VVVVVV parameter on the          *   FILE1016
//*                LISTPDS command.                                 *   FILE1016
//*     XI       - A command that permits several TSO commands      *   FILE1016
//*                to be stacked on one line.  The original idea    *   FILE1016
//*                for XI was PCF, a long forgotten TSO add on.     *   FILE1016
//*                More often than not, PCF command stacking        *   FILE1016
//*                simply did not seem to work.  It is a viable     *   FILE1016
//*                alternate to using the "Field Mark" key on       *   FILE1016
//*                real 3270 terminals, but its use has declined    *   FILE1016
//*                as most 3270 emulators do not seem to provide    *   FILE1016
//*                the "Field Mark" key, require multiple key       *   FILE1016
//*                presses to enter a "Field Mark," or change       *   FILE1016
//*                what a terminal operator must enter to enter     *   FILE1016
//*                a "Field Mark" from release to release of the    *   FILE1016
//*                terminal emulator.                               *   FILE1016
//*                                                                 *   FILE1016
```
