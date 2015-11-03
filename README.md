# Image Deflickering for Timelapse Videos

After I made my first few timelapse videos I got really
bothered by the erratic small changes of exposure, which are caused
by various effects:
* Changes of the exposure settings (if not in full manual mode)
* Uncertainties of the aperture
* Shutter jitter

I was looking for an existing solution and only found expensive (O(100€))
software.

So I wrote this little (150 SLOCS) programm.
The brightness of the images are adjusted to fit a rolling mean several consecutive images.


## Installation
I recommend anaconda, it comes with the heavy dependencies of this package:
`numpy` and `scikit-image`

Installation of `deflicker`:

```
$ pip install git+https://github.com/maxnoe/timelapse-deflicker
```

## Usage

`timelapse-deflicker` expects all your pictures in one folder
and named in a scheme, that an alphabetical sorting results in the
correct chronological order.

The adjusted images are saved in the folder `deflickerd` by default.

You can use sigma clipping to get rid of outliers for the calculation 
of the correction factor.
