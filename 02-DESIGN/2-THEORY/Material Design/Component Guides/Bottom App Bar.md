---
prefer-view: read
cssclasses:
  - list-cards
  - cards-col-2
url: 
tags:
  - "#article"
  - Material-Design
  - components
  - product-design
---
# Guidelines
## Usage
-> They provide upto 4 actions buttons and a [[FAB]]
-> should only be used on mobile devices
-> shouldn't be used for screen with one or less actions or headings
-> For any destructive action in bottom bar, a snack bar should accompany the action
-> **Bottom bars are not navigation bars**

# Anatomy

![Diagram of bottom app bar indicating the 4 parts of its anatomy](https://firebasestorage.googleapis.com/v0/b/design-spec/o/projects%2Fgoogle-material-3%2Fimages%2Flw1ue6ek-9.png?alt=media&token=4815c919-195e-4db7-8eb0-48f9202b47cf)

1. **Container**: contains all elements
2. **FAB**: It is displayed within bottom bars
3. **Icon Button**: It can hold upto 4 icon buttons
4. **Icon button for overflow menu**

# Placement
## With top bar
=> top bar can provide navigation and actions can be organised in bottom bar

## With snack bar
=> To avoid obstructions, snackbar should animate in its place vertically.

# Responsive Layout

=> It is optimised for compact and medium windows, **not** recommended for larger windows
=> Always use the minimum height of bottom bar

## Alignment

=> FAB should be aligned to trailing edge
=> Secondary actions should be aligned to leading edge

# Behaviour

## Scrolling
=> Scrolling downwards hides bottom bar
=> Scrolling upwards reveals bottom bar