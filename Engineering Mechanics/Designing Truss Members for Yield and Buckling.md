# Designing Truss Members for Yield and Buckling
Created: 18/08/2022 at 16:32
Tags:
Related: [[Simple Trusses, The Method of Joints, Zero-Force Members]]

### How Safe? and Yield
We say the allowable stress is 60% the yield stress of the material. For steel we use 250MPa as its yield stress so our allowable stress is **150MPa**.

$$\frac{F}{\sigma_{all}} \leq A$$

### Buckling
Members subjected to compressive forces may bend and deflect laterally and fail due to buckling. #todo/excalidraw
$$P_{cr} = \frac{\pi^2EI}{L^2}$$

I - the second moment of area.

#### Second Moment of Area
#todo/excalidraw
$$I_{x} = \sum y^2bsy = \int^{h/2}_{-h/2}y^2bdy$$

### Summary
Analyse the truss by finding all the internal forces.

Determine the cross sectional (A) required for the mmeber under the largest forces.

Determine the second moment of area for the most critical member under compresion.

```ad-info
This critical member could be the one with the largest compression force, or one with a lower compression force but larger.
```

Choose a section from the table #todo that satisfies both A and I.
