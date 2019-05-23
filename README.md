# lammps-gpu-docker
This is a Singularity container build on nvidia/cuda that runs LAMMPs with gpu acceleration package.

# Running LAMMPs

## Building

```sudo singularity build lmp_gpu.simg  lmp_gpu.def```

This will save the container to current working directory as lmp_gpu.simg

## Running

```mpirun -np <N> singularity exec --nv   lmp_gpu.simg  <LMP_CMD>```

Where:
- <N> : number of processors
- <LMP_CMD> :  standard LAMMPs command line options.

# Example

```mpirun -np 8 singualrity exec --nv lmp_gpu.simg  -sf gpu -pk pgu 1 -i in.lj -l lj.log```
