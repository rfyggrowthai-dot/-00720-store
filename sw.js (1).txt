
const CACHE_NAME = 'wasit-v110-1';
const urlsToCache = ['/-00720-store/','/-00720-store/index.html','/-00720-store/manifest.json'];
self.addEventListener('install', e => { e.waitUntil(caches.open(CACHE_NAME).then(c=>c.addAll(urlsToCache))) });
self.addEventListener('fetch', e => { e.respondWith(caches.match(e.request).then(r=> r || fetch(e.request))) });
