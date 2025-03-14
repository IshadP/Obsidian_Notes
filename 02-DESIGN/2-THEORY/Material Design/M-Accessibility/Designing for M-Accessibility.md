---
prefer-view: read
cssclasses:
  - list-cards
  - cards-col-2
url: https://m3.material.io/foundations/designing/overview
tags:
  - "#article"
  - accessibility
  - ux
  - "#Material-Design"
---
Material framework uses WCAG guidelines for base and best practices

For more accessibility use native standart platform elements.

## Color contrast
Color can help communicate mmod, tone and info. Using right color contrast can help user understand and interact with right elements.

__Color contrast ratio is the distinguishing between foreground and background elements__

It ranges from 1:1 to 21:1, higher the better.

Foe,
__Large Text__ = 3 : 1
__Small text__ = 4.5 : 1

Example:

![[Pasted image 20241026132209.png]]![[Pasted image 20241026132213.png]]

---

![[Pasted image 20241026132239.png]]![[Pasted image 20241026132243.png]]

## Hierarchy

When navigation is easy user understand your app. To emphasize on information that is important, use proper hierarchy and color.

### Navigation
It should have clear task flow with minimal steps, easy to locate controls and clear labeling.
More features:
1. Clear visible elements
2. Sufficient constrast and size
3. Clear hierarchy
4. Key information

### Level of importance
- Place important action at the top
- Place related items near to each other / next to each other

### Visual Hierarchy
Understand how screen reader work. To design accessible apps designer need to work closely with developers to understand not only CSS but HTML hierarchy as well.

## Web landmarks and headings

Assistive Technologies rely on clear communication, a clear structure in order to function. These are heading amd landmarks.
By classifying page in to a strucutured info, we can convey complex information with ease, while enabling assistive technologies to function actively.

### identifying landmarks 
Landmarks are large block of content that establish structure
According to W3C ARIA(Accessible Rich Internet Application) Guidelines these landmarks are:
1. __Navigation__
2. __Search__
3. __Main__
4. __Banner__
5. __Complementary__
6. __ContentInfo__
7. __Region__: important content blocks
8. __Form__

### add accessibility labels
__Add clear and specific labels__ to an  landmark role. This helps user differentiate information.

_Do not repeat landmark role within a label._

### add heading
Assistive tech often rely on web heading to navigate webpage.
1. Identify heading based on content hierarchy
2. Make sure no level of heading is skipped. 
	1. h1->h2->h3 :SiTicktick: 
	2. h1->h3 :LiCross:
3. Map your content to heading 

## Target Size
Target is anything that user needs to interact with.

### Touch & pointer target sizes
touch pointers are part of screen that interact to user input.
Most platform recommend about 48x48dp touch target

_Note: iOS recommends about 44 x 44dp_

![[Pasted image 20241026152823.png]]

- Icons: 24dp
- Star icon: 40dp
- Touch target on both: 48dp

### Pointer targets
These are touch targets but implemented by motion tracking device such as stylus and mouse.

### Padding
_Minimum padding_: 8dp

## Flow

People should be able to navigate your app without the use of mouse of touch screen. Simplify your flows by:
1. Strategic ordering of tabs
2. Reducing overall page complexity

### Use defaults

Avoid doing more work by using predefined tab ordering, unless your user journey needs it specifically. This is due to fact that keyboard navigation may be defined for this already.

### Determine user flows

#### 1. group product use cases
 -> group product uses cases into primary and secondary use case
#### 2. Define intial focus and component level focus
-> define initial focus when user loads and component focus when user interacts with a complex element

#### 3. Define any atypical key traversal through page and components
-> Define the use of _tab, arrow keys, Enter_ for a atypical traversal or complex elements

### Respect pre-existing keyboard shortcuts

---
