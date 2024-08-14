Created: 21/09/2023 at 08:31

Getting an image from the sensor to the CPU is the smallest part. The *software* is the key to make a system like this useful.

### Applications for Embedded Systems
- digital camera
- surveillance camera
- robotics

### Software Needed
- motion detection (easy)
- color detection (little more complex)
- shape detection (difficult)

#### Motion Detection
Subtracting gray scale values for all pixel-pairs from two subsequent images.
![[Image Processing-1695256606019.jpeg]]

Better to use *absolute difference* of values rather than just difference.
I.e.
- compute average over all pixels
- if average above threshold, motion detected
![[Image Processing-1695256707418.jpeg]]

##### Implementation
```c
void difference(BYTE im1[], BYTE im2[], BYTE diff[]){
  for (int i = 0; i < VGA_PIXELS; i++){
    diff[i] = abs(im1[i] - im2[i]);
  }
}

int average(BYTE img[]){
  int sum = 0;
  for (int i = 0; i < VGA_PIXELS; i++){
    sum += img[i];
  }
  return sum / VGA_PIXELS;
}

int motion(BYTE im1[], BYTE ims2[], int threshold){
  VGAgray diff;
  difference(im1, im2, diff);
  return (average(diff) > threshold);
}
```
#### Object Tracking


#### Colour Models
##### RGB
Color spaces, red, green, blue
![[Image Processing-1695257720193.jpeg]]

Not independent on the independent lighting.

##### HSI
Hue, saturation, intensity
![[Image Processing-1695257813429.jpeg]]

Ideally we want the hue value from RGB as that is independent of the lighting.

##### HIS Conversion
![[Image Processing-1695257931783.jpeg]]

##### Simplified HSI Conversion
![[Image Processing-1695258047182.jpeg]]

#### Colour Detection
Uniquely coloured objects are easier to detect by using colour than shape.

##### Steps
1. From RGS to Hue (of HSI)
2. From Hue to boolean (does pixel HSI match desired HIS range)?
3. From match-image to position coordinates
![[Image Processing-1695258262140.jpeg]]

##### Implementation
```c
void matching(BYTE hue[], BYTE match[], int desired, int thres){
  for (int i = 0; i < CAMHEIGHT*CAMWIDTH; i++){
    diff = abs(hue[i] - desired);
    match[i] = (diff < thres || 252-diff < thres) && (hue[i] != NO_HUE);
}

void histrogram(BYTE match[][], BYTE hist[]){
  for (int x = 0; x < CAMWIDTH; x++) {
    hist[x] = 0;
    for (int y = 0; y < CAMHEIGHT; y++) {
      int pos = y*CAMWIDTH + x;
      hist[x] += match[pos];
    }
  }
}

int maxpos(BYTE hist[]) {
  int best_post = 0;
  for (int i = 0; i < CAMWIDTH; i++) {
    if (hist[i] > hist[best_pos]) {
      best_pos = i;
    }
  }
  return best_pos;
}

int ColDetect(BYTE img[], inte desired, int thres) {
  // find object of desired hue and threshold
  VGAgray hue, sat, inten, match; // signel bytes for H,S,I
  int hist[640]; // max line size for VGA

  IPCol2HSI(img, hue, sat, inten); // hue conversion
  matching(hue, match, desired, thres); // boolean conversion
  histogram(match, hist); // generate histogram
  return maxpos(hist); // find max position
}
```
### Image Data Types in RoBIOS7
![[Image Processing-1695256497934.jpeg]]
