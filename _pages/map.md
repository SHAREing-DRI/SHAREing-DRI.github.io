---
layout: default
permalink: /map/
title: UK City Map — SHAREing Project
---



<div id="map" style="height: 640px; border-radius: 10px; overflow: hidden;"></div>

<!-- Leaflet -->
<link
  rel="stylesheet"
  href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css"
  crossorigin=""
/>
<script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js" crossorigin=""></script>

<style>
html, body {
  margin: 0;
  padding: 0;
}
  #map { height: 600px; margin: 1em 40em; border-radius: 12px; }
  .overlay {
    position: fixed; inset: 0;
    background: rgba(0,0,0,0.45);
    display: none; justify-content: center; align-items: center;
    z-index: 9999;
  }
.overlay {
  position: fixed;
  inset: 0;
  background: rgba(0, 0, 0, 0.45);
  display: none;
  justify-content: center;
  align-items: center;
  z-index: 1000;
}
.overlay.active {
  display: flex;
  animation: fadeIn 0.3s ease forwards;
}
.info-panel {
  background: #fff;
  width: 100%;
  max-width: 800px;
  padding: 60px 30px 35px;
  border-radius: 20px;
  box-shadow: 0 12px 25px rgba(0, 0, 0, 0.25);
  transform: scale(0.9);
  opacity: 0;
  transition: all 0.3s ease;
  position: relative;
}
.overlay.active .info-panel {
  transform: scale(1);
  opacity: 1;
}
.close-btn {
  background: none;
  border: none;
  font-size: 1.6rem;
  cursor: pointer;
  position: absolute;
  top: 15px;
  right: 20px;
  color: #002A41;
}
.member-list {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
  gap: 20px;
  margin-top: 20px;
  list-style: none;
  align-items: center;
  text-align: center;
  padding: 0;
}
.member {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.member img {
  width: 120px;
  height: 120px;
  border-radius: 50%;
  object-fit: cover;
  align-items: center;
  margin-bottom: 8px;
  box-shadow: 0 2px 5px rgba(0,0,0,0.2);
}
.member-name {
  font-weight: 600;
  color: #222;
}
.member-role {
  font-style: italic;
  color: #444;
  font-size: 0.9rem;
}
</style>

<div id="overlay" class="overlay" onclick="closePanel(event)">
  <div id="infoPanel" class="info-panel" onclick="event.stopPropagation()">
    <button class="close-btn" onclick="closePanel()">×</button>
    <h2 id="cityTitle">City</h2>
    <div id="cityContent" class="city-desc">Click a city to learn more.</div>
  </div>
</div>

<script>
const cities = [
  {
    name: 'Durham University',
    lat: 54.7753, lon: -1.5849,
    info: 'Durham University is a collegiate public research university in Durham, England.',
    members: [
      { name: 'Thomas Flynn', role: 'Research Software Engineer<br>', img: '/assets/profilepics/generic.jpg' },
      { name: 'Tobias Weinzierl', role: 'Professor of Computer Science<br>', img: 'https://tobiasweinzierl.webspace.durham.ac.uk/wp-content/uploads/sites/288/2022/02/2019_tobias.jpg' },
      { name: 'Alan Real', role: 'Director of Advanced Research Computing', img:'/assets/profilepics/generic.jpg' },
      { name: 'Eamonn <br> Bell', role: 'Professor of Computer Science', img:'/assets/profilepics/generic.jpg'},
       { name: 'Alastair Basden', role: 'Director of COSMA <br> ', img:'/assets/profilepics/generic.jpg'},
       { name: 'Gokmen <br> Kilic', role: 'Research Software Engineer', img:'/assets/profilepics/Gokmen.jpg' },
      { name: 'Eva Fernandez', role: 'Community Manager <br> ', img: '/assets/profilepics/Fernandez.jpg' }
    ]
  },
    {
    name: 'Cardiff University',
    lat: 51.4816, lon: -3.1791,
    info: 'Cardiff is the capital of Wales.',
    members: [
      { name: 'Jon Lockley', role: 'Director of Advanced Research Computing', img: '/assets/profilepics/generic.jpg' },
      { name: 'Martyn Guest', role: 'Director of Advanced Research Computing', img: '/assets/profilepics/generic.jpg' }
    ]
  },
  {
    name: 'University of Sheffield',
    lat: 53.3811, lon: -1.4701,
    info: 'Sheffield is a city in South Yorkshire.',
    members: [
      { name: 'Davide Costanzo', role: 'Head of Particle Physics', img: '/assets/profilepics/generic.jpg' }
    ]
  },
  {
    name: 'Queen Mary University of London',
    lat: 51.5074, lon: -0.1278,
    info: 'Queen Mary University of London (QMUL) is an established university in London’s vibrant East End.',
    members: [
      { name: 'Biagio Lucini', role: 'Professor of Mathematics and Head of School', img: '/assets/profilepics/Lucini.jpg' },
      { name: 'Jon Hays', role: 'Head of Particle Physics Research Centre', img: '/assets/profilepics/generic.jpg' }
    ]
  },
  {
    name: 'The University of Manchester',
    lat: 53.4808, lon: -2.2426,
    info: 'The University of Manchester is a public research university located in Manchester, UK and its roots trace back to 1824.',
    members: [
      { name: 'Georgios Fourtakas', role: 'Associate Professor, School of Engineering', img:'/assets/profilepics/GFourtakas.jpg' }
    ]
  },
  {
    name: 'Swansea University',
    lat: 51.6214, lon: -3.9436,
    info: 'Swansea University is a research-intensive university in Swansea, Wales, founded by royal charter in 1920 as a constituent college of the University of Wales, and becoming independent in 2007.',
    members: [
      { name: 'Ed Bennett', role: 'Senior Research Software Engineer', img:'/assets/profilepics/Bennett.jpg' }
    ]
  },
  {
    name: 'CoSeC',
    lat: 53.3406, lon: -2.8494,
    info: 'The Computational Science Centre for Research Communities (CoSeC)',
    members: [
      { name: 'Damian Jones', role: 'Programme Manager', img:'/assets/profilepics/DamianJones.jpg' },
      { name: 'Stephen Longshaw', role: 'Director of the Computational Science Centre for Research Communities', img:'/assets/profilepics/Longshaw.jpg' }
    ]
  }
];


const map = L.map('map').setView([54, -2], 6);
L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
  attribution: '© OpenStreetMap contributors'
}).addTo(map);

const normalStyle = { radius: 8, color: '#002A41', fillColor: '#002A41', weight: 1, fillOpacity: 0.85 };
const hoverStyle = { radius: 14, color: '#B906B9', fillColor: '#B906B9', weight: 2, fillOpacity: 1 };

const overlay = document.getElementById('overlay');
const cityTitle = document.getElementById('cityTitle');
const cityContent = document.getElementById('cityContent');

function openPanel(city) {
  cityTitle.textContent = city.name;
  cityContent.innerHTML = `
    <p>${city.info}</p>
    <h3>Team Members</h3>
    <ul class="member-list">
      ${city.members.map(m => `
        <li class="member">
          <img src="${m.img}" alt="${m.name}">
          <div class="member-name">${m.name}</div>
          <div class="member-role"><em>${m.role}</em></div>
        </li>
      `).join('')}
    </ul>
  `;
  overlay.classList.add('active');
}

function closePanel(event) {
  if (event && event.target !== overlay && !event.target.classList.contains('close-btn'))
    return;
  overlay.classList.remove('active');
}

cities.forEach(city => {
  const marker = L.circleMarker([city.lat, city.lon], normalStyle).addTo(map);
  marker.bindTooltip(city.name, { direction: 'top', offset: [0, -8] });
  marker.on('mouseover', () => marker.setStyle(hoverStyle));
  marker.on('mouseout', () => marker.setStyle(normalStyle));
  marker.on('click', () => openPanel(city));
});
</script>

