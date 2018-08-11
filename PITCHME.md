<!-- .slide: class="center" -->

## HoustonWW 2018

### Extending Madagascar tools

<br>
Carlos Alberto da Costa Filho

August 11, 2018

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

## sfpgreywfl

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

## afdm.jl

#### Finite-difference Julia example

- Finite-difference examples exist for C, C++, Fortran90, and Python

- These codes reside in: [@ahay/src](https://github.com/ahay/src)/api/$LANG/test/

- With a Julia API we can now contribute an example in Julia

---

## afdm.jl
#### Code snippets

```julia
import m8r

# Get file names
vel = m8r.getstring("vel")
ref = m8r.getstring("ref")

# Load wavelet, velocity and sources
ww, nw, dw, ow, lw, uw = m8r.rsf_read("in")
vv, nv, dv, ov, lv, uv = m8r.rsf_read(vel)
rr, nr, dr, or, lr, ur = m8r.rsf_read(ref)
```

---
## afdm.jl
#### Code snippets

```julia
ud[3:end-2, 3:end-2] = c0 .* uo[3:end-2, 3:end-2].*(idx.+idz) .+
c1.*(uo[3:end-2, 2:end-3] .+ uo[3:end-2, 4:end-1]).*idx .+
c2.*(uo[3:end-2, 1:end-4] .+ uo[3:end-2, 5:end  ]).*idx .+
c1.*(uo[2:end-3, 3:end-2] .+ uo[4:end-1, 3:end-2]).*idz .+
c2.*(uo[1:end-4, 3:end-2] .+ uo[5:end,   3:end-2]).*idz

# inject wavelet, scale by velocity, update
ud = ud .- ww[it] .* rr
ud = ud .* vv .* vv
up = 2.*uo .- um .+ ud .* dt2
um, uo = uo, up

m8r.floatwrite(vec(uo), nz*nx, Fo)
```
---
![afdm.jl wavefield](https://s3.eu-west-2.amazonaws.com/cdacosta-londonbucket/wavefield_afdm.mp4)

---

## Next steps

<br>

- Julia v1.0 has come out, API must be updated!

<br>

- Would be nice if `sfpgreywfl` could also plot sources/receivers


---
<!-- .slide: class="center" -->
## Thank you for your attention!

Follow me at GitHub: [@cako](https://github.com/cako/)

<br>
<br>
<div style="font-size: 0.5em">
Find this presentation at: [https://github.com/cako/seg-working-workshop-2018](https://github.com/cako/seg-working-workshop-2018)
</div>
<div style="font-size: 0.5em">
View this presentation at: [https://gitpitch.com/cako/seg-working-workshop-2018](https://gitpitch.com/cako/seg-working-workshop-2018)
</div>
