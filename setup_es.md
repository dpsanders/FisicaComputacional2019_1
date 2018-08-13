## Correr Julia en linea: JuliaBox
La forma más fácil de correr Julia es en línea usando el servicio [JuliaBox](http://www.juliabox.com).
Este provee una versión en línea de una [Jupyter notebook](http://www.jupyter.org), que se usara durante el curso. Se usa `Shift-Enter` para ejecutar una celda.

Una alternativa es [CoCalc](http://www.cocalc.com), que permite la edición simultanea de las notebooks por distintas personas.

## Instalar Julia y Jupyter localmente
Para instalar Julia y Jupyter localmente en sus computadoras se siguen los siguientes pasos.

[Nota que *no* es necesario instalar Anaconda de manera separada; Julia hará esto por ti.]

1. Descarga e instala la versión estable de Julia (0.6.3) de [aqui](http://www.julialang.org/downloads) para el sistema operativo que uses.

2. Corre la copia de Julia que instalaste.

    Ejecuta los siguientes comandos en la teminal del entorno de Julia ("REPL"), en donde veras un `julia> `.

3. Si usas Linux, primero teclea:
```jl
julia> ENV["JUPYTER"] = ""
```

4. Ahora instala el paquete IJulia, que automáticamente instalará Jupyter (usando `miniconda`):
```
julia> Pkg.add("IJulia")
```

5. Abre la libreta como sigue.
```jl
julia> using IJulia
julia> notebook()
```
Por default, notebooks nuevas seran creadas en tu directorio principal. Abre o crea una carpeta diferente de tu preferencia para guardarlos en la locación de tu elección.

6. Instala algunos otros paquetes que usaremos durante el curso (Necesitaras una conexión a Internet):
```jl
julia> packages = split(
    """Plots GR PlotlyJS Interact
    BenchmarkTools
    ForwardDiff
    TaylorSeries
    DynamicalSystems
    DifferentialEquations
    IntervalArithmetic
    IntervalRootFinding
    """)    

julia> for package in packages
    Pkg.add(package)
end
```
## Poniendose al día con la sintaxis básica de Julia

Si no has tenido un acercamiento a Julia, puedes usar [este video turorial](https://youtu.be/4igzy3bGVkQ) para ponerte al día con la sintaxis basica de Julia, en particular las notebooks del 1 al 8 (incluyendo "Plotting"). Las libretas estas disponibles directamente en JuliaBox o [aqui](https://github.com/JuliaComputing/JuliaBoxTutorials/tree/master/intro-to-julia).

Sugerimos que añadas a favoritos, descargues o incluso imprimas los siguientes "acordeones" que resume la sintaxis basica de Julia:
- A [one-page summary by Steven Johnson](https://github.com/stevengj/1806/blob/master/julia/Julia-cheatsheet.pdf)

- A [more extensive summary](https://juliadocs.github.io/Julia-Cheat-Sheet)

Existe una siempre creciente lista de recursos para aprender Julia disponibles en la [learning page](http://www.julialang.org/learning) de Julia; en particular revisa [QuantEcon lectures](https://lectures.quantecon.org/jl).


## Julia IDE: Juno

Existen dos IDEs (Integrated Development Environments) disponibles para Julia: Juno, basada en el editor de texto [Atom](https://atom.io/), y una extensión de Julia para el editor Visual Studio Code.

Descargue Atom e instale el paqeute `uber-juno`; Esto te dara un entorno de desarrollador de Julia. Más información disponible en [Juno IDE homepage](http://junolab.org/).


## Preguntas y Comentarios
Por favor contactar a [David](dpsanders@ciencias.unam.mx) si tienes alguna duda o comentario.
