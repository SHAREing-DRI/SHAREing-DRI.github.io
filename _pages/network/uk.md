---
layout: single
permalink: /uk/
---


<div class="uk-map-container">

    <img
        src='/assets/images/map.png'
        alt="Map of UK universities"
        class="uk-map">

    <!-- Durham -->
    <button class="marker"
            style="top:44.25%; left:69.5%;"
            data-uni="durham">
    </button>

    <!-- Belfast -->
    <button class="marker"
            style="top:46%; left:39.5%;"
            data-uni="belfast">
    </button>

    <!-- Leeds -->
    <button class="marker"
            style="top:53.85%; left:69.65%;"
            data-uni="leeds">
    </button>

    <!-- Sheffield -->
    <button class="marker"
            style="top:60%; left:69.7%;"
            data-uni="sheffield">
    </button>

    <!-- Manchester -->
    <button class="marker"
            style="top:58%; left:65%;"
            data-uni="manchester">
    </button>

    <!-- Birmingham -->
    <button class="marker"
            style="top:68.5%; left:67.5%;"
            data-uni="birmingham">
    </button>

    <!-- Cardiff -->
    <button class="marker"
            style="top:78.55%; left:58.8%;"
            data-uni="cardiff">
    </button>

    <!-- Oxford -->
    <button class="marker"
            style="top:75.5%; left:73.5%;"
            data-uni="oxford">
    </button>

    <!-- UCL -->
    <button class="marker"
            style="top:75%; left:83%;"
            data-uni="ucl">
    </button>

    <!-- Imperial -->
    <button class="marker"
            style="top:78%; left:80%;"
            data-uni="imperial">
    </button>

    <!-- Queen Mary -->
    <button class="marker"
            style="top:80%; left:83%;"
            data-uni="qmul">
    </button>

</div>

<!-- ===================================================== -->

<div id="uni-modal" class="uni-modal">

<div class="uni-modal-card">

    <button id="close-modal" class="close-button">×</button>

    <div class="uni-header">

        <img id="uni-logo"
             class="uni-logo"
             src=""
             alt="University logo">

        <div>

            <h2 id="uni-name"></h2>

            <p id="uni-location" class="uni-location"></p>

        </div>

    </div>

    <div class="programme-banner">

        <h3 id="programme-name"></h3>

        <span id="programme-type"></span>

    </div>

    <p id="uni-description" class="uni-description"></p>

    <div class="info-grid">

        <div class="info-card">
            <span class="label">Duration</span>
            <span id="programme-duration"></span>
        </div>

        <div class="info-card">
            <span class="label">Study mode</span>
            <span id="programme-mode"></span>
        </div>

        <div class="info-card">
            <span class="label">Start</span>
            <span id="programme-start"></span>
        </div>

        <div class="info-card">
            <span class="label">Russell Group</span>
            <span id="uni-russell"></span>
        </div>

    </div>

    <div class="button-row">

        <a id="programme-link"
           class="primary-button"
           target="_blank">
           View Master's
        </a>

        <a id="uni-link"
           class="secondary-button"
           target="_blank">
           University website
        </a>

    </div>

</div>

</div>




<style>

.uni-header{

display:flex;
align-items:center;
gap:1.2rem;
margin-bottom:1.5rem;

}

.uni-logo{

width:80px;
height:80px;
object-fit:contain;

padding:.5rem;

background:white;

border-radius:12px;

box-shadow:0 4px 12px rgba(0,0,0,.08);

}

.uni-location{

margin:0;

color:#666;

font-size:.95rem;

}


.programme-banner{

background:linear-gradient(135deg,#005bbb,#0075e8);

color:white;

padding:1rem 1.2rem;

border-radius:12px;

margin-bottom:1.5rem;

}

.programme-banner h3{

margin:0 0 .3rem 0;

color:white;

}

.programme-banner span{

opacity:.9;

font-size:.9rem;

}

.info-grid{

display:grid;

grid-template-columns:repeat(2,1fr);

gap:12px;

margin-bottom:2rem;

}

.info-card{

background:#f7f8fa;

padding:1rem;

border-radius:10px;

border:1px solid #e8e8e8;

}

.info-card .label{

display:block;

font-size:.8rem;

font-weight:700;

text-transform:uppercase;

color:#777;

margin-bottom:.35rem;

}


.button-row{

display:flex;

gap:1rem;

flex-wrap:wrap;

}

.primary-button{

background:#005bbb;

color:white !important;

padding:12px 22px;

border-radius:10px;

text-decoration:none;

font-weight:700;

}

.secondary-button{

background:white;

border:2px solid #005bbb;

color:#005bbb !important;

padding:12px 22px;

border-radius:10px;

text-decoration:none;

font-weight:700;

}

.primary-button:hover{

background:#004799;

}

.secondary-button:hover{

background:#f5f9ff;

}

.uni-modal-card{

animation:popup .3s ease;

}


/* ==========================================================
   UK Universities Interactive Map
   Designed for Minimal Mistakes
   ========================================================== */

.uk-map-container{
    position:relative;
    width:100%;
    max-width:1000px;
    margin:2rem auto;
}

.uk-map{
    width:100%;
    display:block;
    border-radius:16px;
    box-shadow:0 12px 30px rgba(0,0,0,.15);
}

/* ==========================================================
   MARKERS
   ========================================================== */

.marker{

    position:absolute;

    width:18px;
    height:18px;

    border:none;
    border-radius:50%;

    background:#d62828;

    cursor:pointer;

    transform:translate(-50%,-50%);

    transition:
        transform .2s ease,
        box-shadow .2s ease,
        background .2s ease;

    z-index:20;

}

/* glowing ring */

.marker::before{

    content:"";

    position:absolute;

    inset:-7px;

    border-radius:50%;

    border:2px solid rgba(214,40,40,.45);

    animation:pulse 2.4s infinite;

}

.marker:hover{

    transform:translate(-50%,-50%) scale(1.35);

    background:#005bbb;

    box-shadow:0 0 20px rgba(0,91,187,.55);

}

.marker:focus{

    outline:none;

    transform:translate(-50%,-50%) scale(1.35);

}

/* ==========================================================
   PULSE
   ========================================================== */

@keyframes pulse{

    0%{

        transform:scale(.9);
        opacity:.8;

    }

    70%{

        transform:scale(1.8);
        opacity:0;

    }

    100%{

        transform:scale(1.8);
        opacity:0;

    }

}

/* ==========================================================
   MODAL
   ========================================================== */

.uni-modal{

    position: fixed !important;
    top:0;
    left:0;
    width:100vw;
    height:100vh;

    display:none;

    justify-content:center;
    align-items:center;

    background:rgba(0,0,0,.55);

    z-index:999999;

}

.uni-modal.show{
    display:flex;
}

.uni-modal-card{
    position:relative;

    width:min(550px,95vw);

    background:white;

    border-radius:18px;

    padding:2rem;

    box-shadow:0 20px 60px rgba(0,0,0,.35);
}

@keyframes popup{

    from{

        transform:translateY(20px);
        opacity:0;

    }

    to{

        transform:translateY(0);
        opacity:1;

    }

}

/* ==========================================================
   CLOSE BUTTON
   ========================================================== */

.close-button{

    position:absolute;

    top:15px;

    right:15px;

    width:40px;

    height:40px;

    border:none;

    border-radius:50%;

    background:#eeeeee;

    cursor:pointer;

    font-size:24px;

    transition:.2s;

}

.close-button:hover{

    background:#d62828;

    color:white;

}

/* ==========================================================
   UNIVERSITY NAME
   ========================================================== */

#uni-name{

    margin-top:0;

    margin-bottom:1rem;

    font-size:2rem;

    color:#005bbb;

}

/* ==========================================================
   TABLE
   ========================================================== */

.uni-table{

    width:100%;

    border-collapse:collapse;

    margin-bottom:1.5rem;

}

.uni-table td{

    padding:10px 6px;

    border-bottom:1px solid #ececec;

}

.uni-table td:first-child{

    font-weight:700;

    width:150px;

}

/* ==========================================================
   DESCRIPTION
   ========================================================== */

#uni-description{

    margin-bottom:2rem;

    line-height:1.7;

}

/* ==========================================================
   BUTTON
   ========================================================== */

.website-button{

    display:inline-block;

    padding:12px 22px;

    border-radius:10px;

    background:#005bbb;

    color:white !important;

    text-decoration:none;

    font-weight:700;

    transition:.2s;

}

.website-button:hover{

    background:#003f82;

    transform:translateY(-2px);

}

/* ==========================================================
   MOBILE
   ========================================================== */

@media (max-width:700px){

    .modal{

        padding:1rem;

    }

    .modal-card{

        padding:1.5rem;

    }

    #uni-name{

        font-size:1.6rem;

    }

    .marker{

        width:16px;
        height:16px;

    }

}

/* ==========================================================
   DARK MODE
   (works with Minimal Mistakes)
   ========================================================== */

html[data-theme="dark"] .modal-card{

    background:#242424;

    color:white;

}

html[data-theme="dark"] .uni-table td{

    border-color:#444;

}

html[data-theme="dark"] .close-button{

    background:#444;

    color:white;

}

html[data-theme="dark"] .website-button{

    background:#4d9dff;

}

html[data-theme="dark"] #uni-name{

    color:#8fc4ff;

}



</style>



<script>
/*
==============================================================
UK Universities Interactive Map
==============================================================
*/

const universities = {

durham:{

    name:"Durham University",

    logo:"/assets/images/universities/durham-logo.png",

    location:"Durham, England",

    website:"https://www.durham.ac.uk/",

    programmeName:"MSc Scientific Computing and Data Analysis",

    programmeType:"Full-time • On campus",

    duration:"1 year",

    mode:"Full-time",

    start:"September",

    programmeLink:"https://www.durham.ac.uk/",

    russell:"Yes",

    description:
    "Develop advanced computational, programming and data analysis skills through a research-led Master's programme with strong links to high-performance computing and research software engineering."

},

    sheffield: {

        name: "The University of Sheffield",

        location: "Sheffield, England",

        founded: "1905",

        students: "30,000+",

        russell: "Yes",

        website: "https://www.sheffield.ac.uk/",

        description:
            "The University of Sheffield is a Russell Group university recognised internationally for engineering, computer science, medicine and materials research."

    },

    cardiff: {

        name: "Cardiff University",

        location: "Cardiff, Wales",

        founded: "1883",

        students: "34,000+",

        russell: "Yes",

        website: "https://www.cardiff.ac.uk/",

        description:
            "Cardiff University is Wales' only Russell Group university and has an international reputation for research excellence and innovation."

    },

    belfast: {

        name: "Queen's University Belfast",

        location: "Belfast, Northern Ireland",

        founded: "1845",

        students: "25,000+",

        russell: "Yes",

        website: "https://www.qub.ac.uk/",

        description:
            "Queen's University Belfast is one of the UK's oldest universities and is internationally recognised for research, medicine, engineering and computer science."

    },

    ucl: {

        name: "University College London (UCL)",

        location: "London, England",

        founded: "1826",

        students: "50,000+",

        russell: "Yes",

        website: "https://www.ucl.ac.uk/",

        description:
            "UCL is one of the world's leading multidisciplinary universities with internationally recognised teaching and research across almost every academic field."

    },

    imperial: {

        name: "Imperial College London",

        location: "London, England",

        founded: "1907",

        students: "23,000+",

        russell: "Yes",

        website: "https://www.imperial.ac.uk/",

        description:
            "Imperial specialises in science, engineering, medicine and business, and consistently ranks among the world's best universities."

    },

    qmul: {

        name: "Queen Mary University of London",

        location: "London, England",

        founded: "1887",

        students: "32,000+",

        russell: "Yes",

        website: "https://www.qmul.ac.uk/",

        description:
            "Queen Mary University of London is a leading research university with strengths in medicine, law, engineering and the humanities."

    },

    leeds: {

        name: "University of Leeds",

        location: "Leeds, England",

        founded: "1904",

        students: "39,000+",

        russell: "Yes",

        website: "https://www.leeds.ac.uk/",

        description:
            "The University of Leeds is one of the UK's largest universities and is recognised internationally for research and teaching excellence."

    },

    manchester: {

        name: "The University of Manchester",

        location: "Manchester, England",

        founded: "2004 (Origins 1824)",

        students: "46,000+",

        russell: "Yes",

        website: "https://www.manchester.ac.uk/",

        description:
            "The University of Manchester is home to world-leading research across engineering, AI, health sciences and the physical sciences."

    },

    oxford: {

        name: "University of Oxford",

        location: "Oxford, England",

        founded: "1096",

        students: "26,000+",

        russell: "Yes",

        website: "https://www.ox.ac.uk/",

        description:
            "The University of Oxford is the oldest university in the English-speaking world and consistently ranks among the world's leading institutions."

    },

    birmingham: {

        name: "University of Birmingham",

        location: "Birmingham, England",

        founded: "1900",

        students: "38,000+",

        russell: "Yes",

        website: "https://www.birmingham.ac.uk/",

        description:
            "The University of Birmingham is a founding member of the Russell Group with internationally recognised research in engineering, medicine, computer science and the social sciences."

    }

};


const logoElement=document.getElementById("uni-logo");

const programmeName=document.getElementById("programme-name");

const programmeType=document.getElementById("programme-type");

const programmeDuration=document.getElementById("programme-duration");

const programmeMode=document.getElementById("programme-mode");

const programmeStart=document.getElementById("programme-start");

const programmeLink=document.getElementById("programme-link");




/* ====================================================== */
const modal = document.getElementById("uni-modal");

const closeButton = document.getElementById("close-modal");

const nameElement = document.getElementById("uni-name");

const locationElement = document.getElementById("uni-location");

const russellElement = document.getElementById("uni-russell");

const descriptionElement = document.getElementById("uni-description");

const websiteElement = document.getElementById("uni-link");


/* ====================================================== */


const modal = document.getElementById("uni-modal");

const closeButton = document.getElementById("close-modal");

const nameElement = document.getElementById("uni-name");

const locationElement = document.getElementById("uni-location");

const descriptionElement = document.getElementById("uni-description");

const russellElement = document.getElementById("uni-russell");

const websiteElement = document.getElementById("uni-link");

const logoElement = document.getElementById("uni-logo");

const programmeName = document.getElementById("programme-name");

const programmeType = document.getElementById("programme-type");

const programmeDuration = document.getElementById("programme-duration");

const programmeMode = document.getElementById("programme-mode");

const programmeStart = document.getElementById("programme-start");

const programmeLink = document.getElementById("programme-link");


function openUniversity(id){

    const uni = universities[id];

    if(!uni) return;

    logoElement.src = uni.logo;

    logoElement.alt = uni.name + " logo";

    nameElement.textContent = uni.name;

    locationElement.textContent = uni.location;

    programmeName.textContent = uni.programmeName;

    programmeType.textContent = uni.programmeType;

    programmeDuration.textContent = uni.duration;

    programmeMode.textContent = uni.mode;

    programmeStart.textContent = uni.start;

    russellElement.textContent = uni.russell;

    descriptionElement.textContent = uni.description;

    programmeLink.href = uni.programmeLink;

    websiteElement.href = uni.website;

    modal.classList.add("show");

}
/* ====================================================== */

function closeModal(){

    modal.classList.remove("show");

}

/* ====================================================== */

document.querySelectorAll(".marker").forEach(marker=>{

    marker.addEventListener("click",()=>{

        openUniversity(marker.dataset.uni);

    });

});

/* ====================================================== */

closeButton.addEventListener("click",closeModal);

/* ====================================================== */

modal.addEventListener("click",(event)=>{

    if(event.target===modal){

        closeModal();

    }

});

/* ====================================================== */

document.addEventListener("keydown",(event)=>{

    if(event.key==="Escape"){

        closeModal();

    }

});

    </script>