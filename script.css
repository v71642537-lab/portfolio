const canvas = document.getElementById("frameCanvas");
const context = canvas.getContext("2d");

const frameCount = 240; // Total frames

canvas.width = 1920;   // Set to your frame resolution
canvas.height = 1080;  // Set to your frame resolution

function currentFrame(index) {
  const paddedIndex = String(index).padStart(3, '0');
  return `frames/ezgif-frame-${paddedIndex}.jpg`;
}

const images = [];
let imagesLoaded = 0;

for (let i = 1; i <= frameCount; i++) {
  const img = new Image();
  img.src = currentFrame(i);
  img.onload = () => {
    imagesLoaded++;
    if (imagesLoaded === 1) {
      context.drawImage(img, 0, 0);
    }
  };
  images.push(img);
}

function updateImage(index) {
  if (images[index - 1]) {
    context.clearRect(0, 0, canvas.width, canvas.height);
    context.drawImage(images[index - 1], 0, 0);
  }
}

window.addEventListener("scroll", () => {
  const scrollTop = window.scrollY;
  const maxScroll = document.body.scrollHeight - window.innerHeight;
  const scrollFraction = scrollTop / maxScroll;
  const frameIndex = Math.min(
    frameCount,
    Math.ceil(scrollFraction * frameCount)
  );

  requestAnimationFrame(() => updateImage(frameIndex));
});
