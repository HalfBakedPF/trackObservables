# ----------------------------------------
# inputs 

FASTJETLOCATION=/afs/cern.ch/user/h/hinzmann/workspace/Wmass/trackObservables/processing/fastjet/fastjet-install
FASTJETINC :=`$(FASTJETLOCATION)/bin/fastjet-config --cxxflags --plugins`
FASTJETLIB :=`$(FASTJETLOCATION)/bin/fastjet-config --libs --plugins`

HEPMCLOCATION=/afs/cern.ch/user/h/hinzmann/workspace/Wmass/trackObservables/processing/HepMC/HepMC-install
HEPMCINC :=-I$(HEPMCLOCATION)/include
HEPMCLIB :=-L$(HEPMCLOCATION)/lib  -lHepMC

ROOTINC := `root-config --glibs --cflags`

# ----------------------------------------

all: anaSubstructure

anaSubstructure: anaSubstructure.cpp
#	c++ -o anaSubstructure $(ROOTINC) $(FASTJETINC) $(FASTJETLIB) -lRecursiveTools -lEnergyCorrelator anaSubstructure.cpp 
	c++ -o anaSubstructure $(ROOTINC) $(FASTJETINC) $(FASTJETLIB) $(HEPMCINC) $(HEPMCLIB) anaSubstructure.cpp -lEnergyCorrelator -lRecursiveTools -lNsubjettiness -lz puppiContainer.cc PU14.cc EventMixer.cc CmdLine.cc ParticleIDMethods.cc ParticleName.cc EventSource.cc zfstream.cc Version.cc EnergyCorrelations.cc

clean:
	rm anaSubstructure
