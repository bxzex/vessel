# Vessel

A ceramics studio product page where the pot is real geometry — turned on a
lathe in WebGL and configured live.

Live: https://bxzex.github.io/vessel/

## The pot is not a photograph

A profile is only ever a line. Spin that line around an axis and you have a pot,
which is exactly what happens here: the silhouette you pick is a radius
function, sampled up the height of the piece and swept through a full turn into
about 44,000 triangles, rebuilt from scratch every time you move a control.

The normal at each vertex comes from the **slope of the profile**, not from the
position, which is what makes light break over the shoulder properly instead of
sliding around a tube. The fragment shader carries a key light, a fill, a
hemisphere ambient so the underside picks up bounce, a Blinn specular whose
exponent is set by the finish, a Fresnel rim, and a gradient that pools the
glaze thicker at the foot than at the lip.

The camera fits itself to the geometry: it works out how far back it has to be
for both the height and the width of the current silhouette to fit the window,
so no shape is ever cropped whatever the window is doing.

## What is configurable

Four silhouettes, five glazes, three finishes, height from 18 to 42 cm and the
fullness of the belly. Price, dimensions and the specification table all follow.
If WebGL is unavailable the viewer says so plainly and the rest of the page
carries on working.

## Verification

Each silhouette is checked to produce genuinely different geometry rather than
a relabelled one: Bell runs from a 1.155 foot to a 0.36 lip, Column is nearly
straight at 0.34 to 0.39, Bottle narrows to a 0.198 neck over a 0.918 belly.
Glazes are checked in pixels — Tenmoku renders at a mean brightness of 96
against Ash at 159 — and pricing is checked across height, glaze and finish.

## Notes

One HTML file. No libraries, no images, no build step. Vessel is invented; the
address and email are deliberately not real.

Built by [bxzex](https://bxzex.com).
