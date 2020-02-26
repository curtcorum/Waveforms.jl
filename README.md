# Waveforms

[![Build Status](https://travis-ci.org/Paalon/Waveforms.jl.svg?branch=master)](https://travis-ci.org/Paalon/Waveforms.jl)

[![Coverage Status](https://coveralls.io/repos/Paalon/Waveforms.jl/badge.svg?branch=master&service=github)](https://coveralls.io/github/Paalon/Waveforms.jl?branch=master)

[![codecov.io](http://codecov.io/github/Paalon/Waveforms.jl/coverage.svg?branch=master)](http://codecov.io/github/Paalon/Waveforms.jl?branch=master)

Waveform functions library. Following functions are supported:

- Square wave
- Sawtooth wave
- Triangle wave

| Waveform | 2π-periodic    | 1-periodic      |
| -------- | -------------- | --------------- |
| Square   | `squarewave`   | `squarewave1`   |
| Sawtooth | `sawtoothwave` | `sawtoothwave1` |
| Triangle | `trianglewave` | `trianglewave1` |

## Installation

```julia
(v1.0) pkg> add https://github.com/Paalon/Waveforms.jl
```

## Usage

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
