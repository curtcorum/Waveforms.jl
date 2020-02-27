# Waveforms

_Waveform functions for Julia._

| Build Status | Code Coverage |
| ------------ | ------------- |
| [![Linux and macOS build status][travis-img]][travis-url] [![Windows build status][appveyor-img]][appveyor-url] | [![Coverage Status][coverage-img]][coverage-url] [![Coverage Status][codecov-img]][codecov-url] |

Waveform functions library. Following functions are supported:

- Square wave
- Sawtooth wave
- Triangle wave

## Installation

```julia
(v1.0) pkg> add https://github.com/Paalon/Waveforms.jl
```

## Usage

| Waveform | 2π-periodic    | 1-periodic      |
| -------- | -------------- | --------------- |
| Square   | `squarewave`   | `squarewave1`   |
| Sawtooth | `sawtoothwave` | `sawtoothwave1` |
| Triangle | `trianglewave` | `trianglewave1` |

```julia
julia> using Waveforms

julia> squarewave(0.4)
1.0

julia> sawtoothwave(0.4)
0.12732395447351627

julia> trianglewave(0.4)
0.2546479089470326

julia> using UnicodePlots

julia> lineplot([squarewave, sin], -π/2, 2π)
           ┌────────────────────────────────────────┐
         1 │⠀⠀⠀⠀⠀⠀⠀⠀⢸⠉⠉⠉⠉⢉⠟⠉⠉⢫⠉⠉⠉⠉⢹⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀│ squarewave(x)
           │⠀⠀⠀⠀⠀⠀⠀⠀⢸⠀⠀⠀⢠⠊⠀⠀⠀⠀⠣⡀⠀⠀⢸⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀│ sin(x)
           │⠀⠀⠀⠀⠀⠀⠀⠀⢸⠀⠀⢠⠇⠀⠀⠀⠀⠀⠀⢱⠀⠀⢸⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀│
           │⠀⠀⠀⠀⠀⠀⠀⠀⢸⠀⠀⡜⠀⠀⠀⠀⠀⠀⠀⠀⢧⠀⢸⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀│
           │⠀⠀⠀⠀⠀⠀⠀⠀⢸⠀⢸⠀⠀⠀⠀⠀⠀⠀⠀⠀⠘⡄⢸⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀│
           │⠀⠀⠀⠀⠀⠀⠀⠀⢸⢀⠇⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢱⢸⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀│
           │⠀⠀⠀⠀⠀⠀⠀⠀⢸⡜⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⣾⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀│
   f(x)    │⠤⠤⠤⠤⠤⠤⠤⠤⢼⠧⠤⠤⠤⠤⠤⠤⠤⠤⠤⠤⠤⠤⠼⡤⠤⠤⠤⠤⠤⠤⠤⠤⠤⠤⠤⠤⢤⠤⠤⠤│
           │⠀⠀⠀⠀⠀⠀⠀⠀⣿⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣧⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢀⠇⠀⠀⠀│
           │⠀⠀⠀⠀⠀⠀⠀⡸⢸⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⡏⡆⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⡸⠀⠀⠀⠀│
           │⠀⠀⠀⠀⠀⠀⢀⠇⢸⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⡇⢱⠀⠀⠀⠀⠀⠀⠀⠀⠀⢠⠃⠀⠀⠀⠀│
           │⠀⠀⠀⠀⠀⠀⡞⠀⢸⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⡇⠀⢇⠀⠀⠀⠀⠀⠀⠀⠀⡎⠀⠀⠀⠀⠀│
           │⠀⠀⠀⠀⠀⡸⠀⠀⢸⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⡇⠀⠘⡆⠀⠀⠀⠀⠀⠀⡸⠀⠀⠀⠀⠀⠀│
           │⠀⠀⠀⠀⡰⠁⠀⠀⢸⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⡇⠀⠀⠘⣄⠀⠀⠀⠀⡜⠁⠀⠀⠀⠀⠀⠀│
        -1 │⠀⢀⣀⣜⣀⣀⣀⣀⣸⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣇⣀⣀⣀⣈⣦⣀⣠⣜⣀⣀⣀⣀⣀⠀⠀⠀│
           └────────────────────────────────────────┘
           -2                                       7
                               x

julia> lineplot([sawtoothwave, sin], -π/2, 2π)
           ┌────────────────────────────────────────┐
         1 │⠀⠀⠀⠀⠀⠀⠀⠀⢸⠀⠀⠀⠀⢀⠞⠉⠉⢢⠀⠀⠀⡰⢺⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀│ sawtoothwave(x)
           │⠀⠀⠀⠀⠀⠀⠀⠀⢸⠀⠀⠀⢠⠊⠀⠀⠀⠀⠣⡠⠚⠀⢸⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀│ sin(x)
           │⠀⠀⠀⠀⠀⠀⠀⠀⢸⠀⠀⢠⠇⠀⠀⠀⠀⣠⠎⢱⠀⠀⢸⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀│
           │⠀⠀⠀⠀⠀⠀⠀⠀⢸⠀⠀⡜⠀⠀⠀⢀⠖⠁⠀⠀⢧⠀⢸⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀│
           │⠀⠀⠀⠀⠀⠀⠀⠀⢸⠀⢸⠀⠀⢀⠜⠁⠀⠀⠀⠀⠘⡄⢸⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀│
           │⠀⠀⠀⠀⠀⠀⠀⠀⢸⢀⠇⢀⡔⠉⠀⠀⠀⠀⠀⠀⠀⢱⢸⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀│
           │⠀⠀⠀⠀⠀⠀⠀⠀⢸⡜⡴⠊⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⣾⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀│
   f(x)    │⠤⠤⠤⠤⠤⠤⠤⠤⣼⠯⠤⠤⠤⠤⠤⠤⠤⠤⠤⠤⠤⠤⠼⡤⠤⠤⠤⠤⠤⠤⠤⠤⠤⠤⠤⢤⣤⠤⠤⠤│
           │⠀⠀⠀⠀⠀⠀⣠⠊⣿⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣧⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⡠⢊⠇⠀⠀⠀│
           │⠀⠀⠀⠀⢠⠎⠀⡸⢸⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⡏⡆⠀⠀⠀⠀⠀⠀⠀⡠⠎⠀⡸⠀⠀⠀⠀│
           │⠀⠀⣀⠞⠁⠀⢀⠇⢸⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⡇⢱⠀⠀⠀⠀⠀⣠⠚⠁⠀⢠⠃⠀⠀⠀⠀│
           │⠀⠐⠁⠀⠀⠀⡞⠀⢸⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⡇⠀⢇⠀⠀⢠⠔⠁⠀⠀⠀⡎⠀⠀⠀⠀⠀│
           │⠀⠀⠀⠀⠀⡸⠀⠀⢸⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⡇⠀⠘⣆⠴⠁⠀⠀⠀⠀⡸⠀⠀⠀⠀⠀⠀│
           │⠀⠀⠀⠀⡰⠁⠀⠀⢸⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⡇⢀⡔⠛⣄⠀⠀⠀⠀⡜⠁⠀⠀⠀⠀⠀⠀│
        -1 │⠀⢀⣀⠜⠀⠀⠀⠀⢸⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⡧⠋⠀⠀⠈⢦⣀⣠⠜⠀⠀⠀⠀⠀⠀⠀⠀│
           └────────────────────────────────────────┘
           -2                                       7
                               x

julia> lineplot([trianglewave, sin], -π/2, 2π)
           ┌────────────────────────────────────────┐
         1 │⠀⠀⠀⠀⠀⠀⠀⠀⢸⠀⠀⠀⠀⢀⢞⠝⢏⢢⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀│ trianglewave(x)
           │⠀⠀⠀⠀⠀⠀⠀⠀⢸⠀⠀⠀⢠⠊⡜⠀⠈⢇⠣⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀│ sin(x)
           │⠀⠀⠀⠀⠀⠀⠀⠀⢸⠀⠀⢠⠇⡼⠀⠀⠀⠈⡆⢱⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀│
           │⠀⠀⠀⠀⠀⠀⠀⠀⢸⠀⠀⡜⡸⠀⠀⠀⠀⠀⠈⢆⢧⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀│
           │⠀⠀⠀⠀⠀⠀⠀⠀⢸⠀⢸⡰⠁⠀⠀⠀⠀⠀⠀⠘⣜⡄⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀│
           │⠀⠀⠀⠀⠀⠀⠀⠀⢸⢀⡷⠁⠀⠀⠀⠀⠀⠀⠀⠀⠘⣵⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀│
           │⠀⠀⠀⠀⠀⠀⠀⠀⢸⡼⠃⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠸⡆⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀│
   f(x)    │⠤⠤⠤⠤⠤⠤⠤⠤⢼⠧⠤⠤⠤⠤⠤⠤⠤⠤⠤⠤⠤⠤⠼⡤⠤⠤⠤⠤⠤⠤⠤⠤⠤⠤⠤⠤⣤⠤⠤⠤│
           │⠀⠀⠀⠀⠀⠀⠀⢠⣿⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢳⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢰⠇⠀⠀⠀│
           │⠀⠀⠀⠀⠀⠀⢠⡻⢸⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⡷⡀⠀⠀⠀⠀⠀⠀⠀⠀⢠⡻⠀⠀⠀⠀│
           │⠀⠀⠀⠀⠀⢠⢊⠇⢸⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢱⢣⡀⠀⠀⠀⠀⠀⠀⢠⢣⠃⠀⠀⠀⠀│
           │⠀⠀⠀⠀⢀⠎⡞⠀⢸⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢇⢣⠀⠀⠀⠀⠀⢠⠎⡎⠀⠀⠀⠀⠀│
           │⠀⠀⠀⢀⠎⡸⠀⠀⢸⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠘⡆⢣⠀⠀⠀⢀⠇⡸⠀⠀⠀⠀⠀⠀│
           │⠀⠀⠀⡎⡰⠁⠀⠀⢸⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠘⣄⢣⠀⢀⠎⡜⠁⠀⠀⠀⠀⠀⠀│
        -1 │⠀⢀⣎⠜⠀⠀⠀⠀⢸⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⢮⣦⣮⠜⠀⠀⠀⠀⠀⠀⠀⠀│
           └────────────────────────────────────────┘
           -2                                       7
                               x

```

[travis-img]: https://travis-ci.org/Paalon/Waveforms.jl.svg?branch=master
[travis-url]: https://travis-ci.org/Paalon/Waveforms.jl

[appveyor-img]: https://ci.appveyor.com/project/Paalon/waveforms-jl
[appveyor-url]: https://ci.appveyor.com/project/Paalon/waveforms-jl

[coverage-img]: https://coveralls.io/repos/Paalon/Waveforms.jl/badge.svg?branch=master&service=github
[coverage-url]: https://coveralls.io/github/Paalon/Waveforms.jl?branch=master

[codecov-img]: https://codecov.io/gh/Paalon/Waveforms.jl/branch/master/graph/badge.svg
[codecov-url]: https://codecov.io/gh/Paalon/Waveforms.jl
