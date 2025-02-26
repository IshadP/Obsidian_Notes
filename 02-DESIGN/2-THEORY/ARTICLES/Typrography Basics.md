---
prefer-view: read
cssclasses:
  - list-cards
url: old Obsidian
tags:
  - "#article"
  - typography
---

# Sans-serif and Serif typeface
![[Pasted image 20240805210239.png]]
Serif is the typeface which has the letter stems or extra parts that end the letter. While sans(greek for not)-serif doesn’t have that.

> [!INFO] Research
> Sans-serif is easier to read compared to serif and there for is more accessible

````col
```col-md
# TypeFace
Typeface is the family of fonts which have similar style.It is like set of fonts
```

```col-md
# Font
Font is a specific size of a typeface
```
````

# Font Pairing
- It is the process of choosing different fonts to create constract in a harmonising way.
![[Pasted image 20240805211157.png]]

> [!NOTE] serif is not your enemy
> If you want to combine sans-serif and serif, you can do it. Make sure serif is the larger font(title font) to maintain accessibility

# Font Size

- It is the size of font displayed on screen.
- The size of font __directy conveys your hierarchy__.
- ![[Pasted image 20240805211602.png]]

→ Usually WCAG are followed to determine font size ideal for device
	→ According to them
		 → 9pt = 12px is minimum readibilty limit for web
		 → Ensure that the font is readable at 200% zoom
		 → Keep body text atleast 16px


# Font Weight

- It is overall thickness of line stroke
- Common weights are normal/regular and bold
- Author personally recomands to use atleast 4 weights to convey hierarchy and contrast


# Tracking

Character spacing or tracking is **an optically consistent adjustment to the space between letters to change the visual density of a line or block of text**

For title. keep tracking between 0 - (-5%)
for body keep tracking between 0 - 5%

> [!INFO] Tight it up and loosen it out!
> According to research tight tracking on titles and loose tracking on body text helps for readibility.

**For all caps use more tracking**

# Leading | Line height
It is the vertical space between lines of text

> [!INFO] Ideal for a reason
> Ideal Line height is 1.5x of font size and 1.2x for titles

# Line Measure | Length
It is measure of  character width of a text block.

> [!INFO] Ideal Readable
> 40-75 character in line make it more readable

# BaseLine
It is measure of vertical rythm and alignment.
![[Pasted image 20240805214307.png]]

Grid take the guess work out and make sense of negative space.
It provides guidelines for content.

# X-height
![[Pasted image 20240805214514.png]]

> [!CAUTION] CAUTION
> Avoid using condensed typefaces with short x-heights for your main body UI text and vice versa for title.


# TypeScale

![](https://miro.medium.com/v2/resize:fit:700/0*n53oxEGZJQIzBXKF)

Just like with spacing and sizing, a linear scale won’t work. Smaller jumps between font sizes are useful at the bottom of the scale, but you don’t want to waste time deciding between 46px and 48px for a large headline.

One approach is to calculate your type scale using a ratio, like 4:5 (a “major third”), 2:3 (a “perfect fifth”), or perhaps the “golden ratio”, 1:1.618. This is often called a “modular scale”.

> Using a 16px base and 4:5 ratio, your scale will end up with lots of sizes that don’t land right on the pixel, like 31.25px, 39.063px, 48.828px, etc. Browsers all handle subpixel rounding a little bit differently, so it’s best to avoid fractional sizes if you can avoid it.

There are more practical approach is to simply pick values by hand. You don’t have to worry about subpixel rounding errors this way, and you have total control over which sizes exist instead of outsourcing that job to some mathematical formula.

---

# References
https://bootcamp.uxdesign.cc/all-you-need-about-typography-as-a-ux-ui-designer-2023-part-1-532d3efcf17d
https://bootcamp.uxdesign.cc/all-you-need-about-typography-as-a-ux-ui-designer-2023-part-1-fcf8d5619052

