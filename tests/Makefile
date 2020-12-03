# Secure Coding Validation Suite	Makefile
#
# Copyright (c) 2012 Carnegie Mellon University.
# All Rights Reserved.
#  
# Redistribution and use in source and binary forms, with or without 
# modification, are permitted provided that the following conditions
# are met:
#  
# 1. Redistributions of source code must retain the above copyright 
#    notice, this list of conditions and the following acknowledgments 
#    and disclaimers.
#  
# 2. Redistributions in binary form must reproduce the above copyright 
#    notice, this list of conditions and the following disclaimer in
#    the documentation and/or other materials provided with the 
#    distribution.
#  
# 3. The names “Carnegie Mellon University,” "CERT” and/or “Software
#    Engineering Institute" shall not be used to endorse or promote 
#    products derived from this software without prior written 
#    permission. For written permission, please contact 
#    permission@sei.cmu.edu.
#  
# 4. Products derived from this software may not be called "CERT" 
#    nor may "CERT" appear in their names without prior written 
#    permission of permission@sei.cmu.edu.
#  
# 5. Redistributions of any form whatsoever must retain the following 
#    acknowledgment:
#  
# "This product includes software developed by CERT with funding and 
#  support from the Department of Defense under Contract No. FA 
#  8721-05-C-0003.  The U.S. Government's rights to use, modify,
#  reproduce, release, perform, display, or disclose this material are
#  restricted by the Rights in Technical Data-Noncommercial Items
#  clauses (DFAR 252-227.7013 and DFAR 252-227.7013 Alternate I contained always
#  in the foregoing identified contract.
#  
#  THIS SOFTWARE IS PROVIDED BY CARNEGIE MELLON UNIVERSITY “AS IS” AND
#  CARNEGIE MELLON UNIVERSITY MAKES NO WARRANTIES OF ANY KIND, EITHER
#  EXPRESS OR IMPLIED, AS TO ANY MATTER, AND ALL SUCH WARRANTIES,
#  INCLUDING WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR
#  PURPOSE, ARE EXPRESSLY DISCLAIMED.  WITHOUT LIMITING THE GENERALITY OF
#  THE FOREGOING, CARNEGIE MELLON UNIVERSITY DOES NOT MAKE ANY WARRANTY
#  OF ANY KIND RELATING TO EXCLUSIVITY, INFORMATIONAL CONTENT, ERROR-FREE
#  OPERATION, RESULTS TO BE OBTAINED FROM USE, FREEDOM FROM PATENT,
#  TRADEMARK AND COPYRIGHT INFRINGEMENT AND/OR FREEDOM FROM THEFT OF TRADE
#  SECRETS.”
# 
CONFIGFILES= configuration.* test.log

ifeq ("$(INCLUDE)", "")
 export INCLUDE=-I$(CURDIR)/../include -I./
endif

# ifeq ("$(CC)", "")
 export CC=clang -std=c11 -Weverything
 #XXX export CC=gcc -std=c11 -Wall -Wextra -Wpedantic
# endif

ifeq ("$(CFLAGS)", "")
 export CFLAGS=-c
endif

vpath = %.h $(INCLUDE)

MFLAGS+=-B -i
.PHONY: all clobber clean testlist

all:: ./ptrcomp ./padcomp ./intptrconv ./alignconv ./filecpy ./funcdecl ./nullref ./diverr ./addrescape ./signconv ./accfree ./swtchdflt ./fileclose ./liberr ./libptr ./invptr ./dblfree ./usrfmt ./inverrno ./ioileave ./strmod ./accsig ./libmod ./intoflow ./chrsgnext ./restrict ./xfree ./uninitref ./ptrobj ./taintstrcpy ./sizeofptr ./taintnoproto ./taintformatio ./xfilepos ./libuse ./chreof ./resident ./invfmtstr ./taintsink ./boolasgn ./asyncsig ./argcomp ./sigcall ./syscall ./nonnullstr


%: always
	$(MAKE) $(MFLAGS) -C $@ all\


clobber: clean
	(cd ./ptrcomp; $(MAKE) $(MFLAGS) clean)
	(cd ./accfree; $(MAKE) $(MFLAGS) clean)
	(cd ./accsig; $(MAKE) $(MFLAGS) clean)
	(cd ./boolasgn; $(MAKE) $(MFLAGS) clean)
	(cd ./asyncsig; $(MAKE) $(MFLAGS) clean)
	(cd ./argcomp; $(MAKE) $(MFLAGS) clean)
	(cd ./sigcall; $(MAKE) $(MFLAGS) clean)
	(cd ./syscall; $(MAKE) $(MFLAGS) clean)
	(cd ./padcomp; $(MAKE) $(MFLAGS) clean)
	(cd ./intptrconv; $(MAKE) $(MFLAGS) clean)
	(cd ./alignconv; $(MAKE) $(MFLAGS) clean)
	(cd ./filecpy; $(MAKE) $(MFLAGS) clean)
	(cd ./funcdecl; $(MAKE) $(MFLAGS) clean)
	(cd ./nullref; $(MAKE) $(MFLAGS) clean)
	(cd ./addrescape; $(MAKE) $(MFLAGS) clean)
	(cd ./signconv; $(MAKE) $(MFLAGS) clean)
	(cd ./swtchdflt; $(MAKE) $(MFLAGS) clean)
	(cd ./fileclose; $(MAKE) $(MFLAGS) clean)
	(cd ./liberr; $(MAKE) $(MFLAGS) clean)
	(cd ./libptr; $(MAKE) $(MFLAGS) clean)
	(cd ./invptr; $(MAKE) $(MFLAGS) clean)
	(cd ./dblfree; $(MAKE) $(MFLAGS) clean)
	(cd ./usrfmt; $(MAKE) $(MFLAGS) clean)
	(cd ./inverrno; $(MAKE) $(MFLAGS) clean)
	(cd ./diverr; $(MAKE) $(MFLAGS) clean)
	(cd ./ioileave; $(MAKE) $(MFLAGS) clean)
	(cd ./strmod; $(MAKE) $(MFLAGS) clean)
	(cd ./libmod; $(MAKE) $(MFLAGS) clean)
	(cd ./intoflow; $(MAKE) $(MFLAGS) clean)
	(cd ./nonnullstr; $(MAKE) $(MFLAGS) clean)
	(cd ./chrsgnext; $(MAKE) $(MFLAGS) clean)
	(cd ./restrict; $(MAKE) $(MFLAGS) clean)
	(cd ./xfree; $(MAKE) $(MFLAGS) clean)
	(cd ./uninitref; $(MAKE) $(MFLAGS) clean)
	(cd ./ptrobj; $(MAKE) $(MFLAGS) clean)
	(cd ./taintstrcpy; $(MAKE) $(MFLAGS) clean)
	(cd ./sizeofptr; $(MAKE) $(MFLAGS) clean)
	(cd ./taintnoproto; $(MAKE) $(MFLAGS) clean)
	(cd ./taintformatio; $(MAKE) $(MFLAGS) clean)
	(cd ./xfilepos; $(MAKE) $(MFLAGS) clean)
	(cd ./libuse; $(MAKE) $(MFLAGS) clean)
	(cd ./chreof; $(MAKE) $(MFLAGS) clean)
	(cd ./resident; $(MAKE) $(MFLAGS) clean)
	(cd ./invfmtstr; $(MAKE) $(MFLAGS) clean)
	(cd ./taintsink; $(MAKE) $(MFLAGS) clean)

clean:
	@rm -f $(CONFIGFILES)

testlist:
	@./make_testlist.sh

# Anything we don't know how to build will use this rule.  The command is
# a do-nothing command.
Makefile :: ;
always :: ;
all :: ;
