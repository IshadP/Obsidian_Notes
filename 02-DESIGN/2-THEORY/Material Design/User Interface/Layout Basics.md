---
prefer-view: read
cssclasses:
  - cards-col-2
url: https://developer.android.com/design/ui/mobile/guides/layout-and-content/layout-basics
tags:
  - "#article"
  - UI
  - Layout
  - Material-Design
---
# Takeaways
---
- Honor device safe areas, which include cutouts, edge to edge inses and system bars
	- Provide a flexible layout which adjusts when user interacts with keyboard
	- Keep essential interactions in reachable screen area.
	![[Pasted image 20241226122825.png]]
- Use containment to group related content to guide the user through conten and actions
- Provide consistent alignment![[Pasted image 20241226121225.png]]
- Don't stick to a ideal layout(potrait), test different aspect ratios
- Don't overwhelm user with too many actions per view

# Parts of Screen
![[Pasted image 20241226121356.png]]
1. System bar
2. Navigation Area
3. Body

1. System bars display important informatoin about state of device and notifications
2. Navigation region allows users to navigate witin the app. access important actions
3. Body holds the screen content, composed of additional groupings and layout parameters.

To understand the appropriate composition and navigation patterns for your layout, seek to understand how users interact with your content.

# Content composition and structure
---
=> Build a flexible flow and rhythm with a structure and containment methods.

## Base structure: use margins and columns for visual guardrails
To begin creating a solid structure with consistent guardrails, add margins and columns to your layouts.
**standard margin is 16 dp**
-> Mobile screen are often divided in to 4 cols

## Use containment to visually group elements
-> Containment refers to using white space and visible elements together to create a visual grouping. 
-> It represents a enclosed area.
- **Implicit containment** uses whitespace to visually group content and create boundaries #gtkterms 
- **Explicit containment** uses object like divider and card to create boundaries #gtkterms 

## Positioning of content
=> Android can handle elements with element within containers using gravity, spacing and scaling.

- **Gravity** is standard for placing and object within a larger container. #gtkterms 
![[Pasted image 20241226123211.png]]
- **Scaling** is crucial to accomodate dynamic content, device orientation and screen size #gtkterms 
![[Pasted image 20241226123342.png]]![[Pasted image 20241226123356.png]]
- **Alignment** is used to create consistent layouts and positions. #gtkterms 

# Layout & navigation pattern
---
