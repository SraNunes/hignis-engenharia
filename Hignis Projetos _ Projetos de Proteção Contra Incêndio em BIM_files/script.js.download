// ---------- Floating Instagram/WhatsApp launcher ----------
const floatMenu = document.getElementById('floatMenu');
const floatToggle = document.getElementById('floatToggle');

if (floatToggle) {
  floatToggle.addEventListener('click', () => {
    floatMenu.classList.toggle('open');
  });
}

document.addEventListener('click', (event) => {
  if (floatMenu && !floatMenu.contains(event.target)) {
    floatMenu.classList.remove('open');
  }
});

// ---------- Mobile menu ----------
const burger = document.getElementById('burger');
const mobileMenu = document.getElementById('mobileMenu');
const mobileClose = document.getElementById('mobileClose');

function toggleMobileMenu(open) {
  if (!mobileMenu) return;
  mobileMenu.classList.toggle('open', open);
  document.body.style.overflow = open ? 'hidden' : '';
}

if (burger) burger.addEventListener('click', () => toggleMobileMenu(true));
if (mobileClose) mobileClose.addEventListener('click', () => toggleMobileMenu(false));
if (mobileMenu) {
  mobileMenu.querySelectorAll('a').forEach(a => {
    a.addEventListener('click', () => toggleMobileMenu(false));
  });
}

// ---------- Reveal on scroll ----------
const revealEls = document.querySelectorAll('[data-reveal]');
if ('IntersectionObserver' in window && revealEls.length) {
  const io = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('is-visible');
        io.unobserve(entry.target);
      }
    });
  }, { threshold: 0.12 });
  revealEls.forEach(el => io.observe(el));
} else {
  revealEls.forEach(el => el.classList.add('is-visible'));
}
