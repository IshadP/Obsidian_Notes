---
prefer-view: read
cssclasses:
  - list-cards
  - cards-col-2
url: https://developer.android.com/design/ui/mobile/guides/layout-and-content/grids-and-units
tags:
  - "#article"
  - Layout
  - mateial-design
  - UI
  - Grid
---
# Takeaways
---
-> while using baseline grid stick to 4s or 8s
-> Note specs in dp or sp, not pixels
-> **Export rasterised graphics** for all buckets
-> Design with responsive mindset with different size classes, resolution, and aspect ratios

> [!note] Desity Independent Pixel (dp) #gtkterms
> It is a flexible unit to provide uniformity to dimensions. for 160 dpi screen 1dp ~ 1px
> 


> [!note] Scalable pixels #gtkterms 
> Same as dp but for fonts

**Note: Always specific font size in sp units**
![[Pasted image 20241227141833.png]]

# Density Buckets
---
High -density screens have more pixels per inch than low density screens. As a result UI elements look larger on low density screen, thus never declare any meaurement in pixels

Android groups ranges of screen densities into "buckets" and uses them to deliver he optimal set of assets to your device.
The most common are:
1. mdpi
2. hdpi
3. xhdpi
4. xxhdpi
5. xxxhdpi

> [!note] To calculate dp 
> dp = (width in pixels * 160) / screen density

# Grids
---
## Baseline grid
Using grid helps us to maintain consistency across UI.
Android utilises an 8 dp grid.

Smaller elements such as icons, type and some elements within components are best aligned on 4 dp grid.

## Column grid
Columns are used to provide vertical defination to layout by dividing content within the body area. Content is placed in areas of screen tha contain columns. Align with an underlying grid to align content.![[Pasted image 20241227142725.png]]

# Size Classes
---
Window sizes are set of opinionated viewport breakpoint that help you design, develop, and test responsive and adaptive application.

# Aspect Ratios
---
They are proportion fo element's width to its height. Aspect ratios are written as in width:height
