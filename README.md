# Frontend Mentor - QR code component solution

This is a solution to the [QR code component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/qr-code-component-iux_sIO_H).

## Table of contents

- [Overview](#overview)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
- [Author](#author)

## Overview

This is a project to solve a challenge from Frontend Mentor about QR Code Component. The mission is to make a card that contains a QR Code image with a caption. 

As I start to solve it, I face two challenges: 
(1) To keep the card's content layout stil on different screen, and
(2) To move the card's position in the middle of the screen.

## Design: Desktop Device
![](/screenshots/desktop-device.png)

## Design: Mobile Device
![](/screenshots/mobile-device.png)

### Links

- Solution URL: (https://github.com/cia2003/fm-qrcode-component)
- Live Site URL: (https://cia2003.github.io/fm-qrcode-component/)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox

### What I learned
The most challenging thing to me is to keep the card's content layout stil when I minimize the screen width. Other else is that how to make the card in the middle of the screen. 

First time, I have problem like this:
![](/screenshots/screenshot-1.png)

The card is already on the center, but not in position that I want (that is in the middle of the screen). I use flexbox to centered the card

```css
.content {
    display: flex;
    justify-content: center;
    align-items: center;
    border: 1px solid red;
}
```

So, I used border to see the problem. And it turns out that the div.content only take relatively 65% of the screen. After I do a trial-and-error, I realized that I need to adjust the div.content's height as per full-screen so that the position of the card will change to the middle of the screen.

```css
.content {
  /* other codes */
    height: 100vh;
}
```

How to keep maintain the content still? In my solution, I only adjust the width on differen screen.

For example like this:
```css
.content #qrCode {
  /* other codes */
    width: 20%;
}

@media screen and (max-width: 426px) {
    .content #qrCode {
        width: 75%;
    }
}
```

At the desktop device, the card's width only take 20% of the screen width. As I minimize the screen, I will increase the width's percentage to 75% so it will keep the content stay still.

### Continued development

I think I want to search for adjusting the width of content automatically without repeating the same code on different screen size.

### Useful resources

- [CSS height](https://stackoverflow.com/questions/52941346/css-height-calc100vh-vs-height-100vh) - This helped me to understand how 'vh' works.

## Author

- Frontend Mentor - [@cia2003](https://www.frontendmentor.io/profile/cia2003)