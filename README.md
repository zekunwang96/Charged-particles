# Charged-particles
CFD-DEM simulation of Charged particles. If employed, please also cite: doi: 10.1016/j.powtec.2020.06.086

If only DEM is needed, which considers drag forces as well, only files under liggghtssrc need to be compiled.
Back up the original files in your own LIGGGHTS/src, and replace them with the given files.use 'make mpi' to compile LIGGGHTS again.

If CFD-DEM coupling is employed, forceModels, cfdemCloud, averagingModel, solvers have to be replaced by the given ones as well.
CFDEM/CFDEMcoupling-PUBLIC-5.x/src/lagrangian/cfdemParticle/cfdemCloud/
CFDEM/CFDEMcoupling-PUBLIC-5.x/src/lagrangian/cfdemParticle/subModels/forceModel/
CFDEM/CFDEMcoupling-PUBLIC-5.x/src/lagrangian/cfdemParticle/subModels/averagingModel/
CFDEM/CFDEMcoupling-PUBLIC-5.x/applications/solvers/

NOTE: 
elelac/elec.C"
"vector x=mesh.faceCentres()[facei];"
should be
"vector x=mesh.Cf().boundaryField()[patchi][facei];"
