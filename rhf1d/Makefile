## ------- file: ------------------------- Makefile ----------------- ##
#
#      Version:       rh2.0, 1-D plane-parallel
#      Author:        Han Uitenbroek (huitenbroek@nso.edu)
#      Last modified: Wed Apr 22 09:37:39 2009 --
#
##     --------------------------                      ----------RH-- ##

include ../Makefile.config

## --- If no FORTRAN compiler is available remove -lrh_f90 in following

      LIBS = -lrh -lrh_f90


## --- Define groups of object files --                -------------- ##


ONE_D_OBJS = anglequad.o  feautrier.o  formal.o  hydrostat.o  multiatmos.o \
             rhf1d.o  piecestokes.o  piecewise.o  project.o  riiplane.o \
             writeflux_xdr.o  writegeom_xdr.o 

   ONEDOBJ = solve1d.o  iter_1d.o  feautrier.o

  RAY_OBJS = anglequad.o  feautrier.o  formal.o  hydrostat.o  multiatmos.o \
             project.o  piecestokes.o  piecewise.o  riiplane.o  solveray.o

BACKGROPAC = anglequad.o  backgrcontr.o  multiatmos.o  project.o


## --- Rules for the executables --                    -------------- ##

all:   rhf1d  solve1d  solveray  backgrcontr

rhf1d:  $(ONE_D_OBJS)  librh
	$(LD) -o $@  $(LDFLAGS) $(ONE_D_OBJS) $(LIBS)

solve1d:  $(ONEDOBJ)  librh
	$(LD) -o $@  $(LDFLAGS) $(ONEDOBJ) $(LIBS)

solveray:  $(RAY_OBJS)  librh
	$(LD) -o $@  $(LDFLAGS) $(RAY_OBJS) $(LIBS)

backgrcontr:  $(BACKGROPAC) librh
	$(LD) -o $@  $(LDFLAGS) $(BACKGROPAC) $(LIBS)


## --- If no FORTRAN compiler is available remove librh_f90.a in following

librh:
	cd ..; $(MAKE) librh.a  librh_f90.a


## --- Clean up --                                     -------------- ##

clean:
	rm -f *.o  rhf1d  solve1d  solveray  backgrcontr


## --- Explicit dependencies on include files --       -------------- ##


anglequad.o:            ../rh.h  ../atom.h  ../atmos.h  \
                        geometry.h

backgrcontr.o:          ../rh.h  ../atom.h  ../atmos.h  \
                        ../spectrum.h  geometry.h  ../background.h  \
                        ../inputs.h  ../error.h  ../statistics.h

feautrier.o:            ../rh.h  ../atom.h  ../atmos.h  \
                        geometry.h  ../spectrum.h  ../error.h

formal.o:               ../rh.h  ../atom.h  ../atmos.h  \
                        geometry.h  ../spectrum.h  ../constant.h  \
                        ../background.h  ../inputs.h  ../error.h  ../xdr.h

hydrostat.o:            ../rh.h  ../atom.h  ../atmos.h  geometry.h \
                        ../background.h  ../constant.h  ../accelerate.h \
                        ../error.h

iter_1d.o:              ../rh.h  ../atom.h  ../atmos.h  \
                        geometry.h  ../accelerate.h  ../error.h  \
                        ../statistics.h

multiatmos.o:           ../rh.h  ../atom.h  ../atmos.h  \
                        geometry.h  ../spectrum.h  ../background.h  \
                        ../constant.h  ../error.h  ../inputs.h  \
                        ../statistics.h  ../xdr.h

piecestokes.o:          ../rh.h  ../atom.h  ../atmos.h  \
                        geometry.h  ../spectrum.h

piecewise.o:            ../rh.h  ../atom.h  ../atmos.h  \
                        geometry.h  ../spectrum.h

project.o:              ../rh.h  ../atom.h  ../atmos.h  \
                        geometry.h

rhf1d.o:                ../rh.h  ../atom.h  ../atmos.h  \
                        geometry.h  ../spectrum.h  ../background.h  \
                        ../statistics.h  ../error.h  ../inputs.h  ../xdr.h

riiplane.o:             ../rh.h  ../atom.h  ../atmos.h  \
                        geometry.h  ../constant.h  ../error.h

solve1d.o:              ../rh.h  ../atom.h  ../atmos.h  \
                        geometry.h  ../spectrum.h  ../accelerate.h  \
                        ../constant.h  ../statistics.h  ../inputs.h

solveray.o:             ../rh.h  ../atom.h  ../atmos.h  \
                        geometry.h  ../spectrum.h  ../background.h  \
                        ../statistics.h  ../inputs.h  ../error.h  ../xdr.h

writeflux_xdr.o:        ../rh.h  ../atom.h  ../atmos.h  \
                        geometry.h  ../spectrum.h  ../constant.h  \
                        ../error.h  ../xdr.h

writegeom_xdr.o:        ../rh.h  ../atom.h  ../atmos.h  \
                        geometry.h  ../error.h  ../inputs.h  ../xdr.h

## ------- end ---------------------------- Makefile ---------------- ##
