CC = gcc
MPICC = mpicc
CFLAGS = -O2 -g
OMP = -fopenmp
LIBS =

all: pi_serial.exe pi_openmp.exe pi_mpi.exe pi_hybrid.exe

pi_serial.exe: pi.c
	$(CC) $(CFLAGS) -o $@ $< $(LIBS)

pi_openmp.exe: pi.c
	$(CC) $(CFLAGS) $(OMP) -o $@ $< $(LIBS)

pi_mpi.exe: pi.c
	$(MPICC) $(CFLAGS) -DWITH_MPI -o $@ $< $(LIBS)

pi_hybrid.exe: pi.c
	$(MPICC) $(CFLAGS) -DWITH_MPI $(OMP) -o $@ $< $(LIBS)

clean:
	rm -f *.o *.exe core
