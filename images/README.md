# Add Your Photos Here

To display real photos from your Facebook page:

1. Go to https://www.facebook.com/RMGServices301/photos
2. Download your favorite before/after or job photos
3. Save them here as `photo1.jpg`, `photo2.jpg`, `photo3.jpg`
4. In `styles.css`, update the `.gallery-item-1`, `.gallery-item-2`, `.gallery-item-3` classes:

```css
.gallery-item-1 {
  background-image: url('images/photo1.jpg');
}
.gallery-item-2 {
  background-image: url('images/photo2.jpg');
}
.gallery-item-3 {
  background-image: url('images/photo3.jpg');
}
```

Don't forget to add `background-size: cover` and `background-position: center` if not already there!
