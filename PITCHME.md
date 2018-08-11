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

## awfd

#### Contributing Julia examples

- Finite-difference examples exist for C, C++, Fortran90, and Python

- With a Julia API we can now contribute an example in Julia

- Testing codes reside in: [@ahay/src](https://github.com/ahay/src)/api/$LANG/test/

<br>
<div class="left">
    <i class="fa fa-user-secret fa-5x" aria-hidden="true"> </i><br>
    <a href="https://gitpitch.com/pro-features" class="pro-link">
    More details here.</a>
</div>
<div class="right">
    <ul>
        <li>Private Repos</li>
        <li>Private URLs</li>
        <li>Password-Protection</li>
        <li>Image Opacity</li>
        <li>SVG Image Support</li>
    </ul>
</div>

---

### Questions?

<br>

@fa[twitter gp-contact](@gitpitch)

@fa[github gp-contact](gitpitch)

@fa[medium gp-contact](@gitpitch)

---?image=assets/image/gitpitch-audience.jpg&opacity=100

@title[Download this Template!]

### <span class="white">Get your presentation started!</span>
### [Download this template @fa[external-link gp-download]](https://gitpitch.com/template/download/white)

