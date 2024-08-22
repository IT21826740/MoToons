

# MoToons 3D Image Slider Banner

This project demonstrates how to create a 3D image slider effect using CSS. The banner section is part of the MoToons website, a kids' cartoon channel primarily focused on fairy tales. The 3D image slider gives a dynamic and interactive experience by rotating images in a circular carousel.

## Demo



https://github.com/user-attachments/assets/235f23a1-163b-494f-885c-4709b6558a75



## Overview

This project is designed to create a visually appealing 3D image slider effect using only HTML and CSS. The slider rotates a set of images in a 3D circular pattern, giving the impression of depth and perspective. This effect is perfect for enhancing the user experience on websites, especially in banner sections.

## Technologies Used

- **HTML5**: For structuring the webpage.
- **CSS3**: For styling the webpage and creating the 3D effects.
- **Web Fonts**: For custom typography.

## Installation

1. Clone the repository to your local machine:

   ```bash
   git clone https://github.com/IT21826740/MoToons.git
   ```

2. Navigate to the project directory:

   ```bash
   cd MoToons
   ```

3. Open the `index.html` file in your preferred web browser to see the 3D image slider in action.

## Usage

The code provided is specifically for creating a 3D image slider within a banner section. You can use this in your own projects by copying the HTML and CSS files into your project structure.

- The main HTML structure is in the `index.html` file.
- The CSS for the 3D slider effect is in the `style.css` file.

## How It Works

### 1. **HTML Structure**

The HTML structure consists of a `banner` div, which contains a `slider` div. The slider holds individual `item` divs, each containing an image. The `content` div contains the title and other elements that are overlaid on the banner.

```html
<div class="banner">
    <div class="slider" style="--quantity: 10">
        <!-- Individual items containing images -->
        <div class="item" style="--position: 1"><img src="images/fairy1.jpg" alt=""></div>
        <!-- More items here -->
    </div>
    <div class="content">
        <h1 data-content="MoToons">MoToons</h1>
        <div class="model"></div>
    </div>
</div>
```

### 2. **CSS 3D Effect**

The 3D effect is achieved by utilizing the following CSS properties:

- **`transform-style: preserve-3d;`**: This allows child elements to be transformed in 3D space.
- **`perspective`**: This gives the illusion of depth.
- **`rotateY`**: This rotates the images around the Y-axis to create a circular pattern.

```css
.banner .slider {
    position: absolute;
    width: 200px;
    height: 250px;
    top: 10%;
    left: calc(50% - 100px);
    transform-style: preserve-3d;
    transform: perspective(1000px);
    animation: autoRun 40s linear infinite;
}
```

Each image is positioned on the carousel using a combination of `rotateY` and `translateZ`.

```css
.banner .slider .item {
    position: absolute;
    inset: 0 0 0 0;
    transform: rotateY(calc((var(--position) - 1) * (360 / var(--quantity)) * 1deg))
               translateZ(550px);
}
```

### 3. **Animation**

The images rotate continuously around the Y-axis using the `@keyframes` animation:

```css
@keyframes autoRun {
    from {
        transform: perspective(1000px) rotateX(-10deg) rotateY(0deg);
    }
    to {
        transform: perspective(1000px) rotateX(-10deg) rotateY(360deg);
    }
}
```

## Customization

You can customize the following aspects of the slider:

- **Number of Images**: Adjust the `--quantity` custom property in the `slider` div to match the number of images.
- **Speed of Rotation**: Modify the `animation` duration in the `slider` div to control the rotation speed.
- **Size and Position**: Adjust the `width`, `height`, `translateZ`, and `rotateY` values to change the size and position of the carousel.

