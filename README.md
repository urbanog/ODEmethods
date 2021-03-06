# ODEmethods

`ODEmethods` package is composed of different methods primarily used for solving systems of ordinary differential equations 
in the case of initial value problems (ODE-IVP).

## Description

`ODEmethods` package is composed of three separate classes that define three different types of methods 
used primarily in solving systems of ordinary differential equations, initial value problems. 
These three classes are:

* `RKMethod` (Runge-Kutta methods e.g. RK4, Dormand-Prince),
* `PECE` (predictor-corrector methods),
* `SymIntegrator` (symplectic integrator methods e.g. Verlet, PEFRL).

Each class can use different subtypes of methods of different orders and ranks. 
A substantial list of different sub-methods can be found in the file `ODEmethods.methods`.
There you can see the format in which methods are saved and can easily add your own.

The main purpose of this package is to perform cross comparisson of different methods with relative ease.
Sub-methods are saved in iterable objects so one can easily iterate over all sub-methods and perform an extensive analysis. 
Sub-methods are formatted in arrays (e.g. *Butcher tableau* for RK methods) and contain coefficients which are defined in `ODEmethods.coefficients`.

## Getting Started

The repository is equipped with six test examples which present the simple usage of the package in diverse applications.
The purpose of examples can be roughly summarised:

* **Newton's law of cooling**: comparisson and error analysis of different Runge-Kutta and/or predictor/corrector methods,
* **SIR model**: usage of RK and PECE methods in epidemiological models,
* **Iodine clock**: usage in the simulations in chemical kinetics,
* **Mathematical pendulum**: comparisson of all methods on a Hamiltonian system with analysis of method energy conservation,
* **Two-body problem**: animation of method comparissons on a Hamiltonian system,
* **Three-body problem**: animation of chaotic behaviour in a Hamiltonian system using the method of symplectic integrators.

### Dependencies

* Python3
* numpy

### Installing

Package can be installed by running the following command:
```
pip install git+git://github.com/KSpenko/ODEmethods.git#egg=ODEmethods
```
It can be than imported in your program with just one line of code:
```
import ODEmethods
```

## Help

The method classes are equipped with **Class Docstrings** which you can easily acces by calling:
```
>>> help(RKMethod)
```

A cruical component for the methods functioning is the `function` that gets passed to the class on initialisation.
The `function` needs to be constructed so that it can accept and calculate the output for **one or more** input values (single variable/numpy array).
Otherwise you will get undefined behaviour especially while using the `PECE` class.

## Authors

Contributors names and contact info:

* Krištof Špenko [@KSpenko](https://twitter.com/KSpenko)

## Version History

* 0.1
    * Initial Release

## License

This project is licensed under the MIT License - see the `LICENSE.txt` file for details