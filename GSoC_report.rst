*************
Google Summer of Code 2022 Final Report
*************
Summary
=======
During this project I optimized `Disimpy's <https://github.com/kerkelae/disimpy>`_ code, a GPU-accelerated diffusion-weighted magnetic resonance simulator that is used for developing and validating neuroimaging methods, by improving simulation runtimes and reducing memory usage. First, I started by learning more about dMRI, diffusion simulations, Numba, and general-purpose GPU-computing. Then, I ran large simulations of diffusion inside realistic neurons to profile the code and to identify performance bottlenecks. Finally, after understanding the code and the problems, I made changes to the source code to improve the simulator. 

What has been done so far
=============
1) A code profiling.
2) An implementation of permeable boundary conditions.
3) An optimization of `mesh_space_subdivision <https://github.com/kerkelae/disimpy/blob/df59c33a42d1c208827c9cf59dc33306a4c92642/disimpy/substrates.py#L456>`_ function.

What needs to be done
=======================
1) Reviewing my `pull requests <https://github.com/kerkelae/disimpy/pulls>`_ and doing the necessary changes to ensure that my code gets merged.

Fine points
=======================
In this section, I will briefly discuss my work over the duration of the program.

It all started in February, when I first contacted my mentor via mail. I submitted my proposal in April after reading about the project and exchanging several emails and video calls to discuss my ideas. I was chosen at the end of May and immediately began working on the project.

To begin, I spoke with my mentor about introducing everyone on the team and organizing the work for the summer. Then I started researching diffusion-weighted MRI and general-purpose GPU computing. To continue, I profiled the code, ran diffusion simulations within real and large models, and performed some tests to identify bugs and bottlenecks. Then, by the end of July and beginning of August I started the implementation of the permeable triangles, a new feature that could be used for future simulations that may be more complicated. It would enable us, for instance, to simulate intra-axonal and extra-axonal diffusion with some exchange between the compartments (permeable surfaces). Finally, I spent the last part of the project optimizing the mesh_space_subdivision function, a method that divides the voxel into subvoxels and lets you know the triangles intersecting with a given subvoxel. We needed to optimize this step because we wanted to simulate realistic cells with hundreds of millions of triangles.

Overall, it has been a rewarding experience that taught me a lot. Thank you to my mentors and Google for your assistance and support!