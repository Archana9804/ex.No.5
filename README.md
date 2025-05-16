# MWAD_EX05_image-carousel-in-react
## Date:

## AIM
To create a Image Carousel using React 

## ALGORITHM
### STEP 1 Initial Setup:
Input: A list of images to display in the carousel.

Output: A component displaying the images with navigation controls (e.g., next/previous buttons).

### Step 2 State Management:
Use a state variable (currentIndex) to track the index of the current image displayed.

The carousel starts with the first image, so initialize currentIndex to 0.

### Step 3 Navigation Controls:
Next Image: When the "Next" button is clicked, increment currentIndex.

If currentIndex is at the end of the image list (last image), loop back to the first image using modulo:
currentIndex = (currentIndex + 1) % images.length;

Previous Image: When the "Previous" button is clicked, decrement currentIndex.

If currentIndex is at the beginning (first image), loop back to the last image:
currentIndex = (currentIndex - 1 + images.length) % images.length;

### Step 4 Displaying the Image:
The currentIndex determines which image is displayed.

Using the currentIndex, display the corresponding image from the images list.

### Step 5 Auto-Rotation:
Set an interval to automatically change the image after a set amount of time (e.g., 3 seconds).

Use setInterval to call the nextImage() function at regular intervals.

Clean up the interval when the component unmounts using clearInterval to prevent memory leaks.

## PROGRAM
## App.jsx
```
import React, { useState } from 'react';
import './App.css';

import beach from './beach.jpeg';
import city from './city.jpeg';
import mountain from './mountain.jpeg';

const images = [beach, city, mountain];

function App() {
  const [index, setIndex] = useState(0);

  const showPrev = () => {
    setIndex((prevIndex) => (prevIndex === 0 ? images.length - 1 : prevIndex - 1));
  };

  const showNext = () => {
    setIndex((prevIndex) => (prevIndex === images.length - 1 ? 0 : prevIndex + 1));
  };

  return (
    <div className="carousel-container">
      <h1>My Travel Gallery</h1>
      <img src={images[index]} alt="Place" className="carousel-image" />
      <div className="nav-buttons">
        <button onClick={showPrev}>Previous</button>
        <button onClick={showNext}>Next</button>
      </div>
    </div>
  );
}

export default App;
```
## App.css
```
.carousel-container {
  text-align: center;
  padding: 20px;
}

.carousel-image {
  width: 600px;
  height: 400px;
  object-fit: cover;
  border-radius: 12px;
}

.nav-buttons button {
  margin: 10px;
  padding: 10px 20px;
}
```
## Output
![image](https://github.com/user-attachments/assets/6661be93-0ebb-459b-952a-1fb5536a711e)
![image](https://github.com/user-attachments/assets/d76e1d0e-819b-4144-b67b-a3f36fb8365d)
![image](https://github.com/user-attachments/assets/21eeff65-4434-4832-8f02-90a31ceb29da)


## RESULT
The program for creating Image Carousel using React is executed successfully.
