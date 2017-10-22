# OpenCV

## Data Model

## Image transformation

### About point
Points are tuples of size 2: `(x, y)`

### About image
Images are NumPy array 
 - `[size, size, channels]` if channel >1
 - `[size, size]` else

### Get subimage, image region
```python
# Image are just numpy array
roi = gray[y1:y2, x1:x2]
```

### Adding Border
```python
bordersize=10
mean=255
border=cv2.copyMakeBorder(im, top=bordersize, bottom=bordersize,
 left=bordersize, right=bordersize, 
 borderType=cv2.BORDER_CONSTANT, value=[mean,mean,mean] )
```

## Pixel transformation

### Dilate pixels
```python
dilated = cv2.dilate(img, np.ones((11, 11)))
```

## Drawing

### Circle (also Point!)
```python
# Set thickness to negative in order to fill the circle
cv2.circle(img, center, radius, color, thickness=1, lineType=8, shift=0)
```

### Rectangle
```python
cv2.rectangle(img_rect, best_rect[0], best_rect[3], col, thickness=5)
```
