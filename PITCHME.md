## HoustonWW 2018

### Extending Madagascar tools

---

## sfpgreywfl

#### A timely solution for modelling afficcionados

- Plots wavefields on top of background models

- Useful for identifying illumination issues, tunneling, etc.

- Highly configurable

- Exports to HTML, GIF, MP4

---

![Wavefield](https://s3.eu-west-2.amazonaws.com/cdacosta-londonbucket/wavefield.mp4)

---

#### Common usage

```bash
sfpgreywfl < wavefield.rsf
```

```bash
sfpgreywfl < wavefield.rsf bg=velocity.rsf
```

```bash
sfpgreywfl < wavefield.rsf bg=velocity.rsf \
    wflcmap=seismic title="Wavefield" \
    barlabel="Velocity (m/s)" \
    tmin=0.08 savefile=wavefield.gif
```

...and many other options

---

## afdm

#### Finite-difference Julia example

- Finite-difference examples exist for C, C++, Fortran90, and Python

- These codes reside in: [@ahay/src](https://github.com/ahay/src)/api/$LANG/test/

- With a Julia API we can now contribute an example in Julia

---

#### afdm.jl snippets

```julia
import m8r
ww, nw, dw, ow, lw, uw = m8r.rsf_read("in")
vv, nv, dv, ov, lv, uv = m8r.rsf_read(vel)
rr, nr, dr, or, lr, ur = m8r.rsf_read(ref)
```
