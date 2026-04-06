# dagmc-spack

A [Spack](https://spack.io/) repository providing the `dagmc` package with support for CAD-based geometry.

## Adding This Repository

```bash
spack repo add https://github.com/Fuad-HH/dagmc-spack
```

To verify the repository was added:

```bash
spack repo list
```

## Installing DAGMC with OpenMC Support

Once the repository is added, install `dagmc` with the `+openmc` variant to enable CAD-based geometry in OpenMC:

```bash
spack install dagmc +openmc
```

## Note on OpenMC with DAGMC Support

The builtin Spack `openmc` package currently does **not** support the `+dagmc` variant.
To use OpenMC with DAGMC (CAD-based particle transport), use the `openmc-pumi` package from the
[SCOREC/pumi-pic-spack](https://github.com/SCOREC/pumi-pic-spack) external repository instead:

```bash
# Add the pumi-pic-spack repository
spack repo add https://github.com/SCOREC/pumi-pic-spack

# Install openmc-pumi with DAGMC support
spack install openmc-pumi +dagmc
```

This repository will be maintained until the builtin `openmc` Spack package officially supports the `+dagmc` variant.
