# CBT147
Converted to GitHub via [cbt2git](https://github.com/wizardofzos/cbt2git)
This is still a work in progress. GitHub repos will be deleted and created during this period...
~~~~~~~~~~~~~~~~

//***FILE 147 is from Rick Fochtman, of Chicago Illinois, and       *   FILE 147
//*           contains a copy of "The ARCHIVER".  "The ARCHIVER"    *   FILE 147
//*           has been upgraded to Version 6.1.4.  This file is     *   FILE 147
//*           in IEBUPDTE SYSIN format.                             *   FILE 147
//*                                                                 *   FILE 147
//*           Rob Prins is the current maintainer of ARCHIVER.      *   FILE 147
//*                                                                 *   FILE 147
//*           Unfortunately, Rick Fochtman passed away several      *   FILE 147
//*           years ago.  Support emails are listed below.          *   FILE 147
//*                                                                 *   FILE 147
//*           ARCHIVER documentation has been put into PDF and      *   FILE 147
//*           MSWORD formats.  Members as follows:                  *   FILE 147
//*                                                                 *   FILE 147
//*           ARCHIVE#  - doc in PDF format                         *   FILE 147
//*           ARCHIVE@  - doc in MSWORD format                      *   FILE 147
//*                                                                 *   FILE 147
//*           Loadmodules for OS/390 and z/OS:                      *   FILE 147
//*           If you do a TSO RECEIVE of member LOADXMI, the        *   FILE 147
//*           LOADLIB has been created. Actually you don't need     *   FILE 147
//*           to assemble and link ARCHIVER, the loadmodules will   *   FILE 147
//*           run on an OS/390 or z/OS system.                      *   FILE 147
//*                                                                 *   FILE 147
//*           Loadmodules for MVS:                                  *   FILE 147
//*           If you do a TSO RECEIVE of member LOADXMIM, the       *   FILE 147
//*           LOADLIB has been created. Actually you don't need     *   FILE 147
//*           to assemble and link ARCHIVER, the loadmodules will   *   FILE 147
//*           run on a MVS system.                                  *   FILE 147
//*                                                                 *   FILE 147
//*           To my knowledge, there isn't any other software       *   FILE 147
//*           product like this, anywhere.  (SG - 10/99)            *   FILE 147
//*                                                                 *   FILE 147
//*           Please refer all questions to Sam Golob or Rob Prins  *   FILE 147
//*                                                                 *   FILE 147
//*              email:  sbgolob@cbttape.org    (Sam Golob)         *   FILE 147
//*                                                                 *   FILE 147
//*              email:  robprins2@kpnmail.nl   (Rob Prins)  -      *   FILE 147
//*                                                                 *   FILE 147
//*            Rob Prins is now the maintainer of the ARCHIVER.     *   FILE 147
//*                                                                 *   FILE 147
//*            Rob Prins is not to be confused with Robert A.H.     *   FILE 147
//*            Prins, who is a different person.                    *   FILE 147
//*                                                                 *   FILE 147
//*           ---------------------------------------------------   *   FILE 147
//*           Modification note:                                    *   FILE 147
//*                                                                 *   FILE 147
//*            Modified slightly by Rob Prins, (Version 6.1.2)      *   FILE 147
//*            The reason was that ARCHIVER was traditionally       *   FILE 147
//*            meant to be used in batch.  However, Rob, who is     *   FILE 147
//*            the author of RPF (Rob's Programming Facility -      *   FILE 147
//*            CBT File 415) wanted RPF to interactively be able    *   FILE 147
//*            to access and modify an Archive.  He found that      *   FILE 147
//*            some LOAD macros were not matched by corresponding   *   FILE 147
//*            DELETE macros, etc., plus a few other errors,        *   FILE 147
//*            which didn't show up when the ARCHIVER was run in    *   FILE 147
//*            batch.  These were fixed here.                       *   FILE 147
//*            Another modification is intruducing an EXEC PARM     *   FILE 147
//*            By specifying 'PARM=SYSIN=ddname1,SYSPRINT=ddname2'  *   FILE 147
//*            you can override the standard ddnames for SYSIN and  *   FILE 147
//*            SYSPRINT. If you omit the PARM the standard ddnames  *   FILE 147
//*            SYSIN and SYSPRINT are used.                         *   FILE 147
//*           ---------------------------------------------------   *   FILE 147
//*                                                                 *   FILE 147
//*           "The ARCHIVER" is a handy mechanism to store all of   *   FILE 147
//*           your software and data objects--source code, load     *   FILE 147
//*           modules, PSF objects, and the like--in one place,     *   FILE 147
//*           in a single VSAM cluster.  Version 4.0 and higher     *   FILE 147
//*           of The ARCHIVER provide a large amount of data        *   FILE 147
//*           compression, especially for source code.  Version     *   FILE 147
//*           4.0 and higher of "The ARCHIVER" allows item-by-item  *   FILE 147
//*           "export" to tape.  From the tape we can go directly   *   FILE 147
//*           back to pds uncompressed form, without need for the   *   FILE 147
//*           intermediate VSAM cluster.  Version 5.0 of The        *   FILE 147
//*           ARCHIVER was extensively reworked from previous       *   FILE 147
//*           versions.  Files created with previous versions of    *   FILE 147
//*           "The ARCHIVER" are upgradable with the "CONVERT"      *   FILE 147
//*           command.  Rick Fochtman plans to keep "The ARCHIVER"  *   FILE 147
//*           upwardly compatible.                                  *   FILE 147
//*                                                                 *   FILE 147
//*           Version 6.1 of The ARCHIVER is basically a            *   FILE 147
//*           Y2K-ization of Version 5.0.  (Remember here that      *   FILE 147
//*           the general CBT disclaimer about Y2K compatibility    *   FILE 147
//*           being "not guaranteed" applies - SG 10/12/99.)        *   FILE 147
//*                                                                 *   FILE 147
//*           "The ARCHIVER" makes it possible to handily store     *   FILE 147
//*           your personal software tool-kit for transport and     *   FILE 147
//*           archive purposes.  It may also be useful for the      *   FILE 147
//*           installation's stuff to help archive all your shop's  *   FILE 147
//*           software on a tape or two.                            *   FILE 147
//*                                                                 *   FILE 147
//*           THIS FILE CONTAINS SOURCE AND MACROS. ALSO A MEMBER   *   FILE 147
//*           CALLED SAMPLIB CONTAINS AN IEBUPDTE SYSIN STREAM FOR  *   FILE 147
//*           RICK'S SAMPLIB PDS. SEE MEMBER CALLED ARCHDOC.        *   FILE 147
//*                                                                 *   FILE 147
//*     >>>>  An adaptation was made to ARCHIVER, to be able to     *   FILE 147
//*     >>>>  assemble and run it on MVS 3.8J, under Hercules.      *   FILE 147
//*     >>>>  This update came from Dave Cartwright.  See his       *   FILE 147
//*     >>>>  members $ARCH370 and $INST370.  Since MVS 3.8J and    *   FILE 147
//*     >>>>  Hercules are accessible to all, they can provide a    *   FILE 147
//*     >>>>  suitable medium for archiving all your later MVS      *   FILE 147
//*     >>>>  software goodies for posterity.  And you won't have   *   FILE 147
//*     >>>>  to be dependent on an employer, to be able to         *   FILE 147
//*     >>>>  access, read, and update your stuff.  There are       *   FILE 147
//*     >>>>  also a couple of bug fixes to the main ARCHIVER       *   FILE 147
//*     >>>>  code.                                                 *   FILE 147
//*                                                                 *   FILE 147
//*           ARCHIVER FUNCTIONS:  (NOT ALL OF THEM LISTED HERE)    *   FILE 147
//*                                                                 *   FILE 147
//*           1. UNLOAD A PDS OR SELECTED PDS MEMBERS TO A VSAM     *   FILE 147
//*              CLUSTER, STORING HISTORICAL AND COMMENT DATA       *   FILE 147
//*              RELATED TO EACH ITEM.                              *   FILE 147
//*                                                                 *   FILE 147
//*           2. LOAD A PDS FROM A VSAM CLUSTER ARCHIVE.            *   FILE 147
//*                                                                 *   FILE 147
//*           3. LIST, COPY OR DELETE ITEMS FROM A VSAM CLUSTER     *   FILE 147
//*              ARCHIVE DATASET.  OPTIONALLY, ADD COMMENT DATA TO  *   FILE 147
//*              ITEMS ON THE ARCHIVE CLUSTER.                      *   FILE 147
//*                                                                 *   FILE 147
//*           4. ITEM-BY-ITEM "EXPORT" OF ALL ENTRIES IN THE VSAM   *   FILE 147
//*              CLUSTER TO TAPE -- STILL IN HIGHLY COMPRESSED      *   FILE 147
//*              FORMAT.  LISTT TO LIST CONTENTS AND LOADT TO       *   FILE 147
//*              LOAD A PDS DIRECTLY FROM TAPE, PARALLEL THE LIST   *   FILE 147
//*              AND LOAD FUNCTIONS DESCRIBED ABOVE FOR THE VSAM    *   FILE 147
//*              CLUSTER ARCHIVE DATASET.                           *   FILE 147
//*                                                                 *   FILE 147
//*           5. PROVIDE A DATA-COMPRESSION MECHANISM TO REDUCE     *   FILE 147
//*              THE MEDIA REQUIREMENTS OF THE VSAM CLUSTER         *   FILE 147
//*              ARCHIVE DATASET AND THE "ITEM-BY-ITEM EXPORT"      *   FILE 147
//*              TAPE.                                              *   FILE 147
//*                                                                 *   FILE 147
//*           6. BACKUP AND RECOVER USING STANDARD IBM UTILITY      *   FILE 147
//*              MECHANISMS.  YOU CAN USE THE "IDCAMS EXPORT"       *   FILE 147
//*              AND "IDCAMS IMPORT" TOO, BUT THEY AREN'T ITEM-     *   FILE 147
//*              BY-ITEM.  THEY MUST DO THE ENTIRE VSAM DATASET.    *   FILE 147
//*                                                                 *   FILE 147
//*    email address:   sbgolob@cbttape.org                         *   FILE 147
//*                                                                 *   FILE 147
//*    ANOTHER NOTE -- I MIGHT AS WELL MENTION THIS CONCEPT HERE.   *   FILE 147
//*                                                                 *   FILE 147
//*    "THE ARCHIVER" CLASSIFIES "ITEMS" BY FOUR 10-BYTE KEYS AND   *   FILE 147
//*    A VERSION NUMBER THAT CAN GO FROM 1 TO 16MB.  SOME EXAMPLE   *   FILE 147
//*    CONTROL STATEMENTS TO UNLOAD ALL MEMBERS OF A PDS INTO A     *   FILE 147
//*    VSAM CLUSTER MIGHT READ AS FOLLOWS:                          *   FILE 147
//*                                                                 *   FILE 147
//*    SET VSAM1DSN=TST.SAMPLE.SYSTEM.ARCHIVE                       *   FILE 147
//*   *   COMMENT (ASTERISK IN COLUMN 1)                            *   FILE 147
//*   *   SET STATEMENT INSTRUCTS DYNAMIC ALLOCATION.               *   FILE 147
//*   *   VSAM1DSN OR VSAM1DDN STATEMENTS ALLOCATE VSAM CLUSTERS.   *   FILE 147
//*    UNLOAD ITEM=(*,SYS1.LKLIB,10/05/90,MVSRES),DSN=SYS1.LINKLIB  *   FILE 147
//*   *   DSN OR DDN STATEMENTS ALLOCATE NON-VSAM DATASETS.         *   FILE 147
//*                                                                 *   FILE 147
//*    THE COMMAS DELIMIT THE KEY FIELDS.  THE "*" IN THE FIRST     *   FILE 147
//*    FIELD DENOTES THAT ALL MEMBERS OF THE PDS SHOULD BE UNLOADED.*   FILE 147
//*    SYS1.LINKLIB, IF IT IS CATALOGED, IS DYNAMICALLY ALLOCATED   *   FILE 147
//*    BY THE ARCHIVER PROGRAM, AS INSTRUCTED BY THE "DSN" KEYWORD. *   FILE 147
//*    VERSION NUMBER (THE FIFTH PARAMETER) DEFAULTS TO 1.          *   FILE 147
//*                                                                 *   FILE 147
//*    IF AN ITEM EXISTS ON THE VSAM ARCHIVE WITH ALL KEYS AND      *   FILE 147
//*    VERSION NUMBER MATCHING, A NEW COPY WILL BE ARCHIVED WITH    *   FILE 147
//*    VERSION NUMBER INCREMENTED BY ONE.  IT IS EASIER TO STORE    *   FILE 147
//*    AN EXTRA COPY THAN TO RECOVER A DELETED COPY.  IF THE        *   FILE 147
//*    VERSION NUMBER IS EXPLICITLY STATED AND ALL FIVE KEYS MATCH, *   FILE 147
//*    THEN AN ITEM REPLACE IS FORCED.  A VERSION NUMBER MAY BE     *   FILE 147
//*    EXPLICITLY STATED, BUT THIS IS USUALLY NOT PREFERABLE.       *   FILE 147
//*                                                                 *   FILE 147
//* >> PLEASE KEEP LOOKING HERE FOR REPORTS OF NEW DEVELOPMENTS. << *   FILE 147
//*                                                                 *   FILE 147
//*    A.  ARCHIVER VERSION 6.1 HAS A "COMPARE" FUNCTION AND AN     *   FILE 147
//*        "ALIAS" FUNCTION FOR ITEMS, WHICH ARE NEW.  THE FORMAT   *   FILE 147
//*        OF THE ARCHIVE HASN'T CHANGED--VERSION 6.1 WILL READ     *   FILE 147
//*        ARCHIVES CREATED BY VERSION 4.0 WITHOUT CONVERSION,      *   FILE 147
//*        (BUT NOT VICE-VERSA, BECAUSE OF THE NEW ALIAS HEADERS).  *   FILE 147
//*        THERE IS ALSO A NEW FEATURE TO LIST CATEGORIES OF        *   FILE 147
//*        ITEMS.  YOU MAY PICTURE THIS FUNCTION AS DESCRIBING      *   FILE 147
//*        "LOGICAL FILES" WITHIN A SINGLE ARCHIVE VSAM DATASET     *   FILE 147
//*        OR TAPE.  THE FUNCTION IS CALLED "LFILE" (FROM AN        *   FILE 147
//*        ARCHIVE) AND "LFILET" (FROM A TAPE).                     *   FILE 147
//*                                                                 *   FILE 147
//*    B.  IN VERSION 6.1, IF TWO ARCHIVED ITEMS COMPARE TO BE      *   FILE 147
//*        IDENTICAL, IT IS POSSIBLE TO STORE ONLY ONE COPY OF      *   FILE 147
//*        THE ACTUAL DATA, AND STILL GET TO THE ITEM VIA TWO       *   FILE 147
//*        KEYS--ONE IS THE ACTUAL KEY, AND THE OTHER IS AN         *   FILE 147
//*        ALIAS KEY.  THIS CAN RESULT IN ENORMOUS MEDIA SAVINGS.   *   FILE 147
//*        (RICK FOCHTMAN HAS DONE "WONDERS" WITH THIS FACILITY.    *   FILE 147
//*        HE HAS SENT ME A SINGLE CARTRIDGE CONTAINING "THE        *   FILE 147
//*        ARCHIVER 5.0" SOFTWARE, PLUS AN ITEM-BY-ITEM EXPORTED    *   FILE 147
//*        ARCHIVE CONTAINING SIX VERSIONS OF THE CBT TAPE, THE     *   FILE 147
//*        JES2 AND JES3 SHARE TAPES, THE CICS SHARE TAPE, AND      *   FILE 147
//*        MATERIAL FROM OTHER TAPES.  I THINK HE DESERVES AT       *   FILE 147
//*        LEAST A "WOW".)                                          *   FILE 147
//*                                                                 *   FILE 147
//* >>>>  NOTICE - NOTICE - NOTICE - NOTICE - NOTICE - NOTICE  <<<< *   FILE 147
//* >>                                                           << *   FILE 147
//* >>    FOR ARCHIVER USERS, ARCHIVER VERSIONS 1, 2, AND 3      << *   FILE 147
//* >>    WILL NOT BE SUPPORTED AFTER JUNE 1, 1994.  VERSION 6.1 << *   FILE 147
//* >>    WILL CONVERT FILES FROM THE EARLIER FORMATS, TO ITS    << *   FILE 147
//* >>    CURRENT FORMAT.                                        << *   FILE 147
//* >>                                                           << *   FILE 147
//* >>>>  NOTICE - NOTICE - NOTICE - NOTICE - NOTICE - NOTICE  <<<< *   FILE 147
//*                                                                 *   FILE 147
~~~~~~~~~~~~~~~~

