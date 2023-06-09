# FAQ

## How does this differ to `jax.numpy.solve`, `jax.scipy.{...}` etc.?

Lineax offers several improvements. Most notably:

- Several new solvers. For example, [`lineax.QR`][] has no counterpart in core JAX. (And is much faster than `jax.numpy.linalg.lstsq`, which is the closest equivalent, and uses an SVD decomposition instead.)

- Several new operators. For example, [`lineax.JacobianLinearOperator`][] has no counterpart in core JAX.

- A consistent API. The built-in JAX operations all differ from each other slightly, and are split across `jax.numpy`, `jax.scipy`, and `jax.scipy.sparse`.

- Numerically stable gradients. The existing JAX implementations will sometimes return `NaN`s!

- Some faster compile times and run times in a few places.

Most of these are because JAX aims to mimc the existing NumPy/SciPy APIs. (I.e. it's not JAX's fault that it doesn't take the approach that Lineax does!)
