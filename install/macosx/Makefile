# Makefile to build a Mac OS X distribution package (.dmg)
#
#
#
# Uncomment the correct TARGET and RELDIR below:
#TARGET=pwsafe
#TARGET=pwsafe-i386
###TARGET=pwsafe64
TARGET=pwsafe
#TARGET=pwsafe-llvm
#RELDIR=../../Xcode/build/Release/
#RELDIR=../../Xcode/build-i386/Release/
###RELDIR=../../Xcode/build64/Release/
#RELDIR=../../Xcode/build-llvm/Release/
RELDIR=$(HOME)/Library/Developer/Xcode/DerivedData/pwsafe-xcode6-*/Build/Products/Release/

CPBIN=/bin/cp
RMBIN=/bin/rm
MDBIN=/bin/mkdir -p

RELEASENAME := 1.12.0

SRCDIR=./dmg/
RESOURCES=$(SRCDIR)/pwsafe.app/Contents/Resources
DMGNAME = ../../$(TARGET)-$(RELEASENAME).dmg
PWSAFE-APP=$(TARGET).app
DOCS := ../../README.md ../../docs/LICENSE.rtf ../../docs/ReleaseNotes.md 
HELP := ../../help/helpEN.zip ../../help/helpRU.zip ../../help/helpDE.zip ../../help/helpES.zip ../../help/helpFR.zip ../../help/helpZH.zip ../../help/helpPL.zip
MOS := ../../src/ui/wxWidgets/I18N/mos

all: dist

dist:
	$(MDBIN) $(SRCDIR)
	$(RMBIN) -f $(SRCDIR).DS_Store
	$(CPBIN) $(DOCS) $(SRCDIR)
	$(CPBIN) -R $(RELDIR)$(PWSAFE-APP) $(SRCDIR)
	$(CPBIN) $(HELP) $(RESOURCES)
	$(MDBIN) $(RESOURCES)/da.lproj
	$(CPBIN) $(MOS)/da/LC_MESSAGES/pwsafe.mo $(RESOURCES)/da.lproj
	$(MDBIN) $(RESOURCES)/de.lproj
	$(CPBIN) $(MOS)/de/LC_MESSAGES/pwsafe.mo $(RESOURCES)/de.lproj
	$(MDBIN) $(RESOURCES)/es.lproj
	$(CPBIN) $(MOS)/es/LC_MESSAGES/pwsafe.mo $(RESOURCES)/es.lproj
	$(MDBIN) $(RESOURCES)/it.lproj
	$(CPBIN) $(MOS)/it/LC_MESSAGES/pwsafe.mo $(RESOURCES)/it.lproj
	$(MDBIN) $(RESOURCES)/sv.lproj
	$(CPBIN) $(MOS)/sv/LC_MESSAGES/pwsafe.mo $(RESOURCES)/sv.lproj
	$(MDBIN) $(RESOURCES)/ko.lproj
	$(CPBIN) $(MOS)/ko/LC_MESSAGES/pwsafe.mo $(RESOURCES)/ko.lproj
	$(MDBIN) $(RESOURCES)/nl.lproj
	$(CPBIN) $(MOS)/nl/LC_MESSAGES/pwsafe.mo $(RESOURCES)/nl.lproj
	$(MDBIN) $(RESOURCES)/pl.lproj
	$(CPBIN) $(MOS)/pl/LC_MESSAGES/pwsafe.mo $(RESOURCES)/pl.lproj
	$(MDBIN) $(RESOURCES)/ru.lproj
	$(CPBIN) $(MOS)/ru/LC_MESSAGES/pwsafe.mo $(RESOURCES)/ru.lproj
	$(MDBIN) $(RESOURCES)/sv.lproj
	$(CPBIN) $(MOS)/sv/LC_MESSAGES/pwsafe.mo $(RESOURCES)/sv.lproj
	$(MDBIN) $(RESOURCES)/zh.lproj
	$(CPBIN) $(MOS)/zh/LC_MESSAGES/pwsafe.mo $(RESOURCES)/zh.lproj
	./create-dmg \
			--window-size 410 370 \
			--background ./background.png \
			--icon-size 40 \
			--volname "Password Safe" \
			--volicon ../../src/ui/wxWidgets/graphics/pwsafe.icns \
			--icon "$(PWSAFE-APP)" 00 110 \
			--app-drop-link 240 110 \
			--icon "README.md" 60  290 \
			--icon "ReleaseNotes.md" 150 290 \
			--icon "LICENSE.rtf" 250 290 \
		$(DMGNAME) \
		$(SRCDIR)

clean-dist:
	$(RMBIN) -f $(DMGNAME)

clean: clean-dist
	$(RMBIN) -rf $(SRCDIR)




