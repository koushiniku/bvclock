# SPDX-License-Identifier: MIT
# Makefile

.SUFFIXES:

SHELL	= /bin/sh
srcdir	= .

PLDS	:= $(wildcard *.pld)
JEDS	:= $(PLDS:.pld=.jed)

COMP	= 5vcomp
PROG	= minipro
CHIP	= ATF22V10C

.PHONY: all
all: $(JEDS)

%.jed: %.pld
	$(COMP) $<

.PHONY: clean
clean:
	rm -f $(JEDS)

.PHONY: write-%
write-%: %.jed
	$(PROG) -p $(CHIP) -w $<
