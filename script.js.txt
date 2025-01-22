// Smooth Scrolling for navigation (if menu is added later)
document.querySelectorAll('a[href^="#"]').forEach(anchor => {
  anchor.addEventListener('click', function (e) {
    e.preventDefault();

    document.querySelector(this.getAttribute('href')).scrollIntoView({
      behavior: 'smooth'
    });
  });
});

// Highlight key sections on scroll
const sections = document.querySelectorAll('section');
window.addEventListener('scroll', () => {
  const scrollPosition = window.scrollY + window.innerHeight / 2;

  sections.forEach(section => {
    if (
      section.offsetTop <= scrollPosition &&
      section.offsetTop + section.offsetHeight > scrollPosition
    ) {
      section.style.backgroundColor = '#e9f8ff';
    } else {
      section.style.backgroundColor = 'white';
    }
  });
});
