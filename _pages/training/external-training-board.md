---
layout: splash
permalink: /training/external-training-board
classes: wide
---


<section class="page-intro">
    <h1>External Training Catalogue</h1>

    <p>
        Discover external training opportunities in HPC, AI, research software engineering, programming, performance optimisation, and related topics.
    </p>

    <div class="disclaimer">
        <strong>Disclaimer:</strong> This page is a signposting resource created by the SHAREing project. SHAREing support has been used to curate, organise, and present publicly available training opportunities in a searchable format. The courses listed here are provided by third-party organisations and are not funded, delivered, or maintained by SHAREing unless explicitly stated. Course content, availability, schedules, and registration are the responsibility of the individual providers.
    </div>
</section>



<p class="pathway-intro"> <strong>Create your own learning pathway:</strong> choose the courses you want to complete and build a personalised curriculum. </p>



<!-- ============================================================
     TOOLBAR
============================================================ -->

<div class="map-toolbar">

    <div class="map-search-wrapper">

        <input
            type="search"
            id="map-search"
            class="map-search"
            placeholder="🔍 Search topics or courses..."
            aria-label="Search topics or courses"
        >

    </div>


    <div class="map-controls">

        <button
            type="button"
            id="open-pathway"
            class="pathway-button"
        >
            <span>🧭</span>
            <span>My pathway</span>
            <span
                id="pathway-count"
                class="pathway-count"
            >
                0
            </span>
        </button>


        <button
            type="button"
            id="zoom-in"
            class="map-control-button"
            title="Zoom in"
            aria-label="Zoom in"
        >
            +
        </button>

        <button
            type="button"
            id="zoom-out"
            class="map-control-button"
            title="Zoom out"
            aria-label="Zoom out"
        >
            −
        </button>

        <button
            type="button"
            id="reset-map"
            class="map-control-button"
        >
            ↺ Reset view
        </button>

    </div>

</div>


<!-- ============================================================
     BOARD
============================================================ -->

<div
    id="training-board-wrapper"
    class="training-board-wrapper"
>

    <div
        id="training-board"
        class="training-board"
    ></div>


    <div
        id="board-loading"
        class="board-message"
    >
        Loading training map...
    </div>


    <div
        id="board-empty"
        class="board-message"
        style="display:none;"
    >
        No matching topics or courses found.
    </div>


    <div
        id="zoom-indicator"
        class="zoom-indicator"
    >
        100%
    </div>

</div>


<!-- ============================================================
     INFORMATION PANEL
============================================================ -->

<aside
    id="map-info-panel"
    class="map-info-panel"
    aria-hidden="true"
>

    <button
        type="button"
        id="close-info-panel"
        class="close-info-panel"
        aria-label="Close information panel"
    >
        ×
    </button>

    <div id="map-info-content"></div>

</aside>


<!-- ============================================================
     LEARNING PATHWAY PANEL
============================================================ -->

<div
    id="pathway-backdrop"
    class="pathway-backdrop"
    aria-hidden="true"
></div>

<aside
    id="pathway-panel"
    class="pathway-panel"
    aria-hidden="true"
>

    <button
        type="button"
        id="close-pathway-panel"
        class="close-pathway-panel"
        aria-label="Close learning pathway"
    >
        ×
    </button>


    <div class="pathway-panel-header">

        <div class="info-type">
            Personal learning
        </div>

        <h2>
            My Learning Pathway
        </h2>

        <p>
            Select courses from the training map to create your own
            curriculum. You can reorder or remove courses at any time.
        </p>

    </div>


    <div
        id="pathway-empty"
        class="pathway-empty"
    >

        <div class="pathway-empty-icon">
            🧭
        </div>

        <h3>
            Your pathway is empty
        </h3>

        <p>
            Explore the map and add courses that you would like
            to include in your learning journey.
        </p>

        <button
            type="button"
            id="explore-training"
            class="primary-pathway-button"
        >
            Explore training
        </button>

    </div>


    <div
        id="pathway-content"
        style="display:none;"
    >

        <div class="pathway-summary">

            <strong id="pathway-summary-count">
                0 courses
            </strong>

            <span id="pathway-summary-hint">
                Drag courses to change their order.
            </span>

        </div>


        <div class="pathway-view-toggle" role="tablist" aria-label="Pathway view">

            <button
                type="button"
                id="pathway-view-list-btn"
                class="pathway-view-btn active"
                data-view="list"
                role="tab"
                aria-selected="true"
            >
                📋 List view
            </button>

            <button
                type="button"
                id="pathway-view-map-btn"
                class="pathway-view-btn"
                data-view="map"
                role="tab"
                aria-selected="false"
            >
                🗺️ Map view
            </button>

        </div>


        <p
            id="pathway-map-hint"
            class="pathway-map-hint"
            style="display:none;"
        >
            Drag cards to arrange them, and drag from the dots on a card's edge to connect steps.
        </p>


        <div
            id="pathway-canvas-controls"
            class="pathway-canvas-controls"
            style="display:none;"
        >

    <button
        type="button"
        id="pathway-zoom-out"
        title="Zoom out"
        aria-label="Zoom out"
    >
        −
    </button>

    <span id="pathway-zoom-indicator">
        100%
    </span>

    <button
        type="button"
        id="pathway-zoom-in"
        title="Zoom in"
        aria-label="Zoom in"
    >
        +
    </button>

    <button
        type="button"
        id="pathway-reset-view"
        title="Reset pathway view"
        aria-label="Reset pathway view"
    >
        ↺
    </button>

</div>


        <div
            id="pathway-list"
            class="pathway-list"
        ></div>

<div class="pathway-actions">

    <button
        type="button"
        id="download-pathway"
        class="download-pathway-button"
    >
        ↓ Download my learning pathway
    </button>

    <button
        type="button"
        id="clear-pathway"
        class="clear-pathway-button"
    >
        Clear pathway
    </button>

</div>

    </div>

</aside>


<!-- ============================================================
     LEGEND
============================================================ -->

<div class="map-legend">

    <div class="legend-item">

        <span class="legend-node group-node"></span>

        <span>Training group</span>

    </div>


    <div class="legend-item">

        <span class="legend-node topic-node"></span>

        <span>Topic</span>

    </div>


    <div class="legend-item">

        <span class="legend-node course-node"></span>

        <span>Course</span>

    </div>


    <div class="legend-item">

        <span class="pathway-legend-icon">🧭</span>

        <span>Your learning pathway</span>

    </div>

</div>


<script>

document.addEventListener("DOMContentLoaded", function () {

    /* ============================================================
       DATA
       ============================================================ */

const allCourses = {{ site.data["external-training"] | jsonify }};

const today = new Date();
today.setHours(0, 0, 0, 0);

const courses = allCourses.filter(course => {
    const dates = course.dates.trim();

    
    if (
        dates.toLowerCase() === "self-paced" ||
        dates.toLowerCase() === "rolling basis"
    ) {
        return true;
    }

    
    const yearMatch = dates.match(/\b(20\d{2})\b/);
    if (!yearMatch) {
        return true;
    }

    const year = parseInt(yearMatch[1], 10);

    
    const monthMatch = dates.match(
        /\b(January|February|March|April|May|June|July|August|September|October|November|December)\b/i
    );

    if (!monthMatch) {
        return true;
    }

    const monthNames = [
        "January", "February", "March", "April",
        "May", "June", "July", "August",
        "September", "October", "November", "December"
    ];

    const month = monthNames.findIndex(
        m => m.toLowerCase() === monthMatch[1].toLowerCase()
    );

    
    const beforeMonth = dates.substring(0, monthMatch.index);

    
    const dayMatches = beforeMonth.match(/\d+/g);

    if (!dayMatches) {
        return true;
    }

    
    const endDay = parseInt(dayMatches[dayMatches.length - 1], 10);

    const courseEndDate = new Date(year, month, endDay);
    courseEndDate.setHours(0, 0, 0, 0);

    return courseEndDate >= today;
});


const trainingTopics =
    {{ site.data["training-topics"] | jsonify }};

const topicGroups = {};

Object.entries(trainingTopics).forEach(
    ([groupName, topics]) => {

        const parts = groupName.trim().split(/\s+/);
        const icon = parts.pop();
        const name = parts.join(" ");

        topicGroups[name] = {
            icon: icon,
            topics: topics
        };

    }
);


    /* ============================================================
       ELEMENTS
       ============================================================ */

    const boardWrapper =
        document.getElementById("training-board-wrapper");

    const board =
        document.getElementById("training-board");

    const loadingMessage =
        document.getElementById("board-loading");

    const emptyMessage =
        document.getElementById("board-empty");

    const infoPanel =
        document.getElementById("map-info-panel");

    const infoContent =
        document.getElementById("map-info-content");

    const closeInfoButton =
        document.getElementById("close-info-panel");

    const searchInput =
        document.getElementById("map-search");

    const zoomInButton =
        document.getElementById("zoom-in");

    const zoomOutButton =
        document.getElementById("zoom-out");

    const resetButton =
        document.getElementById("reset-map");

    const zoomIndicator =
        document.getElementById("zoom-indicator");

    const pathwayPanel =
        document.getElementById("pathway-panel");

    const pathwayBackdrop =
        document.getElementById("pathway-backdrop");

    const openPathwayButton =
        document.getElementById("open-pathway");

    const closePathwayButton =
        document.getElementById("close-pathway-panel");

    const pathwayCount =
        document.getElementById("pathway-count");

    const pathwayEmpty =
        document.getElementById("pathway-empty");

    const pathwayContent =
        document.getElementById("pathway-content");

    const pathwayList =
        document.getElementById("pathway-list");

        const pathwayZoomInButton =
    document.getElementById("pathway-zoom-in");

const pathwayZoomOutButton =
    document.getElementById("pathway-zoom-out");

const pathwayResetButton =
    document.getElementById("pathway-reset-view");

const pathwayZoomIndicator =
    document.getElementById("pathway-zoom-indicator");

    const pathwaySummaryCount =
        document.getElementById("pathway-summary-count");

    const pathwaySummaryHint =
        document.getElementById("pathway-summary-hint");

    const pathwayViewListBtn =
        document.getElementById("pathway-view-list-btn");

    const pathwayViewMapBtn =
        document.getElementById("pathway-view-map-btn");

    const pathwayCanvasControls =
        document.getElementById("pathway-canvas-controls");

    const pathwayMapHint =
        document.getElementById("pathway-map-hint");

    const clearPathwayButton =
        document.getElementById("clear-pathway");

    const downloadPathwayButton =
        document.getElementById("download-pathway");

    const exploreTrainingButton =
        document.getElementById("explore-training");


    /* ============================================================
       CONFIG
       ============================================================ */

    const config = {

        groupColumns: 3,
        groupGap: 28,

        minZoom: 0.10,
        maxZoom: 2.5,
        zoomStep: 1.2,
        initialZoom: 0.5

    };


    /* ============================================================
       STORAGE
       ============================================================ */

    const pathwayStorageKey =
        "shareing-training-pathway";

    const layoutStorageKey =
        "shareing-training-pathway-layout";

    const viewModeStorageKey =
        "shareing-training-pathway-view";


    let pathwayIds = [];

    let pathwayLayout = {
        positions: {},
        connections: []
    };

    let pathwayViewMode = "list";

    let draggedPathwayId = null;


    try {

        const saved =
            localStorage.getItem(
                pathwayStorageKey
            );

        if (saved) {

            const parsed =
                JSON.parse(saved);

            if (Array.isArray(parsed)) {
                pathwayIds = parsed;
            }

        }

    }
    catch (error) {

        pathwayIds = [];

    }


    try {

        const saved =
            localStorage.getItem(
                layoutStorageKey
            );

        if (saved) {

            const parsed =
                JSON.parse(saved);

            if (parsed) {

                pathwayLayout.positions =
                    parsed.positions || {};

                pathwayLayout.connections =
                    Array.isArray(parsed.connections)
                        ? parsed.connections
                        : [];

            }

        }

    }
    catch (error) {

        pathwayLayout = {
            positions: {},
            connections: []
        };

    }


    try {

        const savedView =
            localStorage.getItem(
                viewModeStorageKey
            );

        if (
            savedView === "list" ||
            savedView === "map"
        ) {
            pathwayViewMode = savedView;
        }

    }
    catch (error) {

        pathwayViewMode = "list";

    }


    function savePathway() {

        localStorage.setItem(
            pathwayStorageKey,
            JSON.stringify(pathwayIds)
        );

        localStorage.setItem(
            layoutStorageKey,
            JSON.stringify(pathwayLayout)
        );

    }


    /* ============================================================
       COURSE DATA
       ============================================================ */

    const coursesByTopic = {};
    const courseLookup = {};
    const knownTopics = new Set();


    Object.values(topicGroups).forEach(
        group => {

            group.topics.forEach(
                topic =>
                    knownTopics.add(topic)
            );

        }
    );


    function slugify(value) {

        return String(value)
            .toLowerCase()
            .trim()
            .replace(/\s+/g, "-")
            .replace(/[^\w-]/g, "");

    }


    function courseIndex(course) {

        return slugify(
            course.url ||
            course.title ||
            "course"
        );

    }


    courses.forEach(
        course => {

            const id =
                courseIndex(course);

            courseLookup[id] =
                course;

            if (!course.tags) {
                return;
            }

            String(course.tags)
                .split(",")
                .map(tag => tag.trim())
                .filter(Boolean)
                .forEach(topic => {

                    if (!coursesByTopic[topic]) {
                        coursesByTopic[topic] = [];
                    }

                    coursesByTopic[topic].push(
                        course
                    );

                });

        }
    );


    pathwayIds =
        pathwayIds.filter(
            id => courseLookup[id]
        );


    pathwayLayout.connections =
        pathwayLayout.connections.filter(
            connection =>
                courseLookup[connection.from] &&
                courseLookup[connection.to]
        );


    savePathway();


    /* ============================================================
       HELPERS
       ============================================================ */

    function escapeHtml(value) {

        if (
            value === null ||
            value === undefined
        ) {
            return "";
        }

        return String(value)
            .replace(/&/g, "&amp;")
            .replace(/</g, "&lt;")
            .replace(/>/g, "&gt;")
            .replace(/"/g, "&quot;")
            .replace(/'/g, "&#039;");

    }


    function formatIcon(format) {

        const icons = {

            "Online (self-service)": "📚",
            "Scheduled (online)": "📅",
            "Scheduled (hybrid)": "📅",
            "Scheduled (in-person)": "📅",
            "Upcoming": "⏳",
            "Other": "🎉"

        };

        return icons[format] || "📚";

    }


    function formatLabel(format) {

        const labels = {

            "Online (self-service)": "On-demand",
            "Scheduled (online)": "Scheduled (Online)",
            "Scheduled (hybrid)": "Scheduled (Hybrid)",
            "Scheduled (in-person)": "Scheduled (In-person)",
            "Upcoming": "Upcoming",
            "Other": "Other"

        };

        return labels[format] || format;

    }


    function getPrimaryTopic(course) {

        if (!course.tags) {
            return "Training";
        }

        return String(course.tags)
            .split(",")
            .map(tag => tag.trim())
            .filter(Boolean)[0] ||
            "Training";

    }


    function isCourseInPathway(course) {

        return pathwayIds.includes(
            courseIndex(course)
        );

    }


    /* ============================================================
       PATHWAY
       ============================================================ */

    function addToPathway(course) {

        const id =
            courseIndex(course);

        if (pathwayIds.includes(id)) {
            return;
        }

        pathwayIds.push(id);

        savePathway();

        updatePathwayUI();
        updateCoursePathwayStates();

    }


    function removeFromPathway(course) {

        const id =
            courseIndex(course);

        pathwayIds =
            pathwayIds.filter(
                item => item !== id
            );

        delete pathwayLayout.positions[id];

        pathwayLayout.connections =
            pathwayLayout.connections.filter(
                connection =>
                    connection.from !== id &&
                    connection.to !== id
            );

        savePathway();

        updatePathwayUI();
        updateCoursePathwayStates();

    }


    function clearPathway() {

        if (!pathwayIds.length) {
            return;
        }

        if (
            !window.confirm(
                "Are you sure you want to clear your learning pathway?"
            )
        ) {
            return;
        }

        pathwayIds = [];

        pathwayLayout = {
            positions: {},
            connections: []
        };

        savePathway();

        updatePathwayUI();
        updateCoursePathwayStates();

    }


    /* ============================================================
       PATHWAY VIEW SWITCHING
       ============================================================ */

    function applyViewModeUI() {

        const isMap =
            pathwayViewMode === "map";

        pathwayViewListBtn.classList.toggle(
            "active",
            !isMap
        );

        pathwayViewListBtn.setAttribute(
            "aria-selected",
            String(!isMap)
        );

        pathwayViewMapBtn.classList.toggle(
            "active",
            isMap
        );

        pathwayViewMapBtn.setAttribute(
            "aria-selected",
            String(isMap)
        );

        pathwayCanvasControls.style.display =
            isMap ? "flex" : "none";

        pathwayMapHint.style.display =
            isMap ? "block" : "none";

        pathwaySummaryHint.textContent =
            isMap
                ? "Drag cards to arrange them, and drag from a card's dots to connect steps."
                : "Drag a card, or use ↑ / ↓, to reorder.";

        if (downloadPathwayButton) {

            downloadPathwayButton.textContent =
                isMap
                    ? "↓ Download pathway map"
                    : "↓ Download my learning pathway";

        }

    }


    function switchPathwayView(view) {

        if (
            view !== "list" &&
            view !== "map"
        ) {
            return;
        }

        if (pathwayViewMode === view) {
            return;
        }

        pathwayViewMode = view;

        try {

            localStorage.setItem(
                viewModeStorageKey,
                view
            );

        }
        catch (error) {}

        applyViewModeUI();

        renderActiveView();

    }


    function renderActiveView() {

        if (pathwayViewMode === "map") {

            renderPathway();

        }
        else {

            renderPathwayListView();

        }

    }


    pathwayViewListBtn.addEventListener(
        "click",
        function () {
            switchPathwayView("list");
        }
    );

    pathwayViewMapBtn.addEventListener(
        "click",
        function () {
            switchPathwayView("map");
        }
    );


    /* ============================================================
       PATHWAY LIST VIEW (default, roadmap-style)
       ============================================================ */

    function renderPathwayListView() {

        if (!pathwayList) {
            return;
        }

        pathwayList.className =
            "pathway-list";

        pathwayList.innerHTML =
            "";

        pathwayIds.forEach(
            (id, index) => {

                const course =
                    courseLookup[id];

                if (!course) {
                    return;
                }

                pathwayList.appendChild(
                    createPathwayListItem(
                        course,
                        id,
                        index
                    )
                );

            }
        );

    }


    function createPathwayListItem(course, id, index) {

        const item =
            document.createElement("div");

        item.className =
            "pathway-item";

        item.draggable =
            true;

        item.dataset.courseId =
            id;

        const topic =
            getPrimaryTopic(course);

        const metaParts = [
            topic,
            course.format
                ? formatLabel(course.format)
                : null
        ].filter(Boolean);

        item.innerHTML = `

            <div class="pathway-number">
                ${index + 1}
            </div>

            <div class="pathway-item-content">

                <div class="pathway-item-title">
                    ${escapeHtml(
                        course.title ||
                        "Untitled course"
                    )}
                </div>

                ${
                    course.organisation
                        ? `
                            <div class="pathway-item-organisation">
                                ${escapeHtml(
                                    course.organisation
                                )}
                            </div>
                        `
                        : ""
                }

                <div class="pathway-item-meta">
                    ${escapeHtml(
                        metaParts.join(" • ")
                    )}
                </div>

                <div
                    class="pathway-item-actions"
                    draggable="false"
                >

                    <button
                        type="button"
                        class="pathway-move-button"
                        data-dir="up"
                        title="Move up"
                        aria-label="Move up"
                        ${index === 0 ? "disabled" : ""}
                    >
                        ↑
                    </button>

                    <button
                        type="button"
                        class="pathway-move-button"
                        data-dir="down"
                        title="Move down"
                        aria-label="Move down"
                        ${index === pathwayIds.length - 1 ? "disabled" : ""}
                    >
                        ↓
                    </button>

                    ${
                        course.url
                            ? `
                                <a
                                    class="pathway-view-button"
                                    href="${escapeHtml(course.url)}"
                                    target="_blank"
                                    rel="noopener noreferrer"
                                >
                                    View →
                                </a>
                            `
                            : ""
                    }

                    <button
                        type="button"
                        class="pathway-remove-button"
                    >
                        Remove
                    </button>

                </div>

            </div>

        `;


        item.querySelectorAll(
            ".pathway-move-button"
        ).forEach(
            button => {

                button.addEventListener(
                    "click",
                    function () {

                        movePathwayItem(
                            id,
                            this.dataset.dir
                        );

                    }
                );

            }
        );


        item.querySelector(
            ".pathway-remove-button"
        ).addEventListener(
            "click",
            function () {

                removeFromPathway(
                    course
                );

            }
        );


        item.addEventListener(
            "dragstart",
            function (event) {

                draggedPathwayId = id;

                item.classList.add(
                    "dragging"
                );

                try {

                    event.dataTransfer.effectAllowed =
                        "move";

                    event.dataTransfer.setData(
                        "text/plain",
                        id
                    );

                }
                catch (error) {}

            }
        );


        item.addEventListener(
            "dragend",
            function () {

                draggedPathwayId = null;

                item.classList.remove(
                    "dragging"
                );

                pathwayList
                    .querySelectorAll(
                        ".pathway-item"
                    )
                    .forEach(
                        element =>
                            element.classList.remove(
                                "drag-over"
                            )
                    );

            }
        );


        item.addEventListener(
            "dragover",
            function (event) {

                if (
                    !draggedPathwayId ||
                    draggedPathwayId === id
                ) {
                    return;
                }

                event.preventDefault();

                item.classList.add(
                    "drag-over"
                );

            }
        );


        item.addEventListener(
            "dragleave",
            function () {

                item.classList.remove(
                    "drag-over"
                );

            }
        );


        item.addEventListener(
            "drop",
            function (event) {

                event.preventDefault();

                item.classList.remove(
                    "drag-over"
                );

                if (
                    !draggedPathwayId ||
                    draggedPathwayId === id
                ) {
                    return;
                }

                const rect =
                    item.getBoundingClientRect();

                const insertBefore =
                    (event.clientY - rect.top) <
                    rect.height / 2;

                reorderPathway(
                    draggedPathwayId,
                    id,
                    insertBefore
                );

                draggedPathwayId = null;

            }
        );


        return item;

    }


    function movePathwayItem(id, direction) {

        const index =
            pathwayIds.indexOf(id);

        if (index === -1) {
            return;
        }

        const targetIndex =
            direction === "up"
                ? index - 1
                : index + 1;

        if (
            targetIndex < 0 ||
            targetIndex >= pathwayIds.length
        ) {
            return;
        }

        const temp =
            pathwayIds[index];

        pathwayIds[index] =
            pathwayIds[targetIndex];

        pathwayIds[targetIndex] =
            temp;

        savePathway();

        renderPathwayListView();

    }


    function reorderPathway(draggedId, targetId, insertBefore) {

        const fromIndex =
            pathwayIds.indexOf(draggedId);

        if (fromIndex === -1) {
            return;
        }

        pathwayIds.splice(
            fromIndex,
            1
        );

        let targetIndex =
            pathwayIds.indexOf(targetId);

        if (targetIndex === -1) {
            targetIndex =
                pathwayIds.length;
        }

        if (!insertBefore) {
            targetIndex += 1;
        }

        pathwayIds.splice(
            targetIndex,
            0,
            draggedId
        );

        savePathway();

        renderPathwayListView();

    }


    /* ============================================================
       PATHWAY CANVAS (optional map view)
       ============================================================ */

        let pathwayCanvas = null;
        let pathwayViewport = null;
        let pathwayWorld = null;
        let pathwayNodes = null;
        let pathwaySvg = null;

        let pathwayZoom = 1;
        let pathwayPanX = 0;
        let pathwayPanY = 0;

        const pathwayMinZoom = 0.35;
        const pathwayMaxZoom = 2.5;
        const pathwayZoomStep = 1.2;

        let pathwayPanning = false;

        let pathwayPanStartX = 0;
        let pathwayPanStartY = 0;

        let pathwayPanOriginX = 0;
        let pathwayPanOriginY = 0;

            function createPathwayCanvas() {

            pathwayList.innerHTML = "";

            pathwayList.className =
                "pathway-interactive-canvas";


            /* --------------------------------------------------------
            VIEWPORT
            -------------------------------------------------------- */

            pathwayViewport =
                document.createElement("div");

            pathwayViewport.className =
                "pathway-viewport";


            /* --------------------------------------------------------
            WORLD
            Everything inside this gets zoomed and panned.
            -------------------------------------------------------- */

            pathwayWorld =
                document.createElement("div");

            pathwayWorld.className =
                "pathway-world";


            /* --------------------------------------------------------
            SVG
            -------------------------------------------------------- */

            pathwaySvg =
                document.createElementNS(
                    "http://www.w3.org/2000/svg",
                    "svg"
                );

            pathwaySvg.classList.add(
                "pathway-svg"
            );


            /* --------------------------------------------------------
            NODES
            -------------------------------------------------------- */

            pathwayNodes =
                document.createElement("div");

            pathwayNodes.className =
                "pathway-nodes";


            pathwayWorld.appendChild(
                pathwaySvg
            );

            pathwayWorld.appendChild(
                pathwayNodes
            );

            pathwayViewport.appendChild(
                pathwayWorld
            );

            pathwayList.appendChild(
                pathwayViewport
            );


            pathwayCanvas =
                pathwayList;


            /* --------------------------------------------------------
            PAN CANVAS
            -------------------------------------------------------- */

            pathwayViewport.addEventListener(
                "pointerdown",
                startPathwayPan
            );

            pathwayViewport.addEventListener(
                "pointermove",
                movePathwayPan
            );

            pathwayViewport.addEventListener(
                "pointerup",
                stopPathwayPan
            );

            pathwayViewport.addEventListener(
                "pointercancel",
                stopPathwayPan
            );


            /* --------------------------------------------------------
            WHEEL ZOOM
            -------------------------------------------------------- */

            pathwayViewport.addEventListener(
                "wheel",
                handlePathwayWheel,
                {
                    passive: false
                }
            );


            updatePathwayTransform();

        }


        /* ============================================================
   PATHWAY VIEW TRANSFORM
============================================================ */

function updatePathwayTransform() {

    if (!pathwayWorld) {
        return;
    }


    pathwayWorld.style.transform =
        `translate(
            ${pathwayPanX}px,
            ${pathwayPanY}px
        )
        scale(${pathwayZoom})`;


    if (pathwayZoomIndicator) {

        pathwayZoomIndicator.textContent =
            `${Math.round(
                pathwayZoom * 100
            )}%`;

    }

}


/* ============================================================
   PATHWAY PAN
============================================================ */

function startPathwayPan(event) {

    /*
     * Do not pan when interacting with a course,
     * connection handle or button.
     */

    if (
        event.target.closest(
            ".pathway-node, button, a, .pathway-line-hit"
        )
    ) {
        return;
    }


    event.preventDefault();


    pathwayPanning = true;

    pathwayPanStartX =
        event.clientX;

    pathwayPanStartY =
        event.clientY;

    pathwayPanOriginX =
        pathwayPanX;

    pathwayPanOriginY =
        pathwayPanY;


    pathwayViewport.classList.add(
        "is-panning"
    );


    pathwayViewport.setPointerCapture(
        event.pointerId
    );

}


function movePathwayPan(event) {

    if (!pathwayPanning) {
        return;
    }


    pathwayPanX =
        pathwayPanOriginX +
        event.clientX -
        pathwayPanStartX;


    pathwayPanY =
        pathwayPanOriginY +
        event.clientY -
        pathwayPanStartY;


    updatePathwayTransform();

}


function stopPathwayPan(event) {

    if (!pathwayPanning) {
        return;
    }


    pathwayPanning = false;


    pathwayViewport.classList.remove(
        "is-panning"
    );


    if (
        event.pointerId !== undefined
    ) {

        try {

            pathwayViewport.releasePointerCapture(
                event.pointerId
            );

        }
        catch (error) {}

    }

}


/* ============================================================
   PATHWAY ZOOM
============================================================ */

function zoomPathway(factor) {

    const oldZoom =
        pathwayZoom;


    pathwayZoom =
        Math.max(
            pathwayMinZoom,
            Math.min(
                pathwayMaxZoom,
                pathwayZoom * factor
            )
        );


    if (
        pathwayZoom === oldZoom
    ) {
        return;
    }


    updatePathwayTransform();

}


/* ============================================================
   ZOOM AROUND MOUSE POSITION
============================================================ */

function zoomPathwayAtPoint(
    factor,
    clientX,
    clientY
) {

    if (!pathwayViewport) {
        return;
    }


    const rect =
        pathwayViewport.getBoundingClientRect();


    const mouseX =
        clientX -
        rect.left;


    const mouseY =
        clientY -
        rect.top;


    const oldZoom =
        pathwayZoom;


    const newZoom =
        Math.max(
            pathwayMinZoom,
            Math.min(
                pathwayMaxZoom,
                oldZoom * factor
            )
        );


    if (
        newZoom === oldZoom
    ) {
        return;
    }


    /*
     * Keep the point underneath the cursor
     * in the same place while zooming.
     */

    pathwayPanX =
        mouseX -
        (
            mouseX -
            pathwayPanX
        ) *
        (
            newZoom /
            oldZoom
        );


    pathwayPanY =
        mouseY -
        (
            mouseY -
            pathwayPanY
        ) *
        (
            newZoom /
            oldZoom
        );


    pathwayZoom =
        newZoom;


    updatePathwayTransform();

}


/* ============================================================
   MOUSE WHEEL
============================================================ */

function handlePathwayWheel(event) {

    event.preventDefault();


    const factor =
        event.deltaY < 0
            ? pathwayZoomStep
            : 1 / pathwayZoomStep;


    zoomPathwayAtPoint(
        factor,
        event.clientX,
        event.clientY
    );

}


/* ============================================================
   RESET PATHWAY VIEW
============================================================ */

function resetPathwayView() {

    pathwayZoom = 1;

    pathwayPanX = 0;

    pathwayPanY = 0;

    updatePathwayTransform();

}


    /* ============================================================
       NODE POSITION
       ============================================================ */

    function defaultPosition(index) {

        const width =
            pathwayCanvas.clientWidth || 900;

        const nodeWidth = 230;
        const nodeHeight = 145;
        const gapX = 45;
        const gapY = 45;

        const columns =
            Math.max(
                1,
                Math.floor(
                    width /
                    (nodeWidth + gapX)
                )
            );


        return {

            x:
                25 +
                (index % columns) *
                (nodeWidth + gapX),

            y:
                25 +
                Math.floor(index / columns) *
                (nodeHeight + gapY)

        };

    }


    function getPosition(id, index) {

        if (
            pathwayLayout.positions[id]
        ) {
            return pathwayLayout.positions[id];
        }

        const position =
            defaultPosition(index);

        pathwayLayout.positions[id] =
            position;

        return position;

    }


    /* ============================================================
       RENDER PATHWAY
       ============================================================ */

    function renderPathway() {

        if (!pathwayList) {
            return;
        }


        createPathwayCanvas();


        if (!pathwayIds.length) {
            return;
        }


        pathwayIds.forEach(
            (id, index) => {

                const course =
                    courseLookup[id];

                if (!course) {
                    return;
                }

                createNode(
                    course,
                    index
                );

            }
        );


        requestAnimationFrame(
            drawConnections
        );

    }


    /* ============================================================
       CREATE NODE
       ============================================================ */

    function createNode(course, index) {

        const id =
            courseIndex(course);

        const node =
            document.createElement("div");

        node.className =
            "pathway-node";

        node.dataset.courseId =
            id;


        const position =
            getPosition(
                id,
                index
            );


        node.style.left =
            position.x + "px";

        node.style.top =
            position.y + "px";


        const topic =
            getPrimaryTopic(course);


        node.innerHTML = `

            <button
                type="button"
                class="pathway-node-remove"
                title="Remove"
            >
                ×
            </button>


            <div
                class="pathway-handle top"
                data-side="top"
            ></div>

            <div
                class="pathway-handle right"
                data-side="right"
            ></div>

            <div
                class="pathway-handle bottom"
                data-side="bottom"
            ></div>

            <div
                class="pathway-handle left"
                data-side="left"
            ></div>


            <div class="pathway-node-title">

                ${
                    course.url
                        ? `
                            <a
                                href="${escapeHtml(course.url)}"
                                target="_blank"
                                rel="noopener noreferrer"
                            >
                                ${escapeHtml(
                                    course.title ||
                                    "Untitled course"
                                )}
                            </a>
                        `
                        :
                        escapeHtml(
                            course.title ||
                            "Untitled course"
                        )
                }

            </div>


            ${
                course.organisation
                    ? `
                        <div class="pathway-node-org">
                            ${escapeHtml(
                                course.organisation
                            )}
                        </div>
                    `
                    : ""
            }


            <div class="pathway-node-meta">

                ${
                    topic
                        ? escapeHtml(topic)
                        : ""
                }

                ${
                    course.format
                        ? `
                            <br>
                            ${escapeHtml(
                                formatLabel(
                                    course.format
                                )
                            )}
                        `
                        : ""
                }

            </div>

        `;


        pathwayNodes.appendChild(
            node
        );


        /* --------------------------------------------------------
           REMOVE
           -------------------------------------------------------- */

        node.querySelector(
            ".pathway-node-remove"
        ).addEventListener(
            "click",
            function (event) {

                event.stopPropagation();

                removeFromPathway(
                    course
                );

            }
        );


        /* --------------------------------------------------------
           CONNECTION HANDLES
           -------------------------------------------------------- */

        node.querySelectorAll(
            ".pathway-handle"
        ).forEach(
            handle => {

                handle.addEventListener(
                    "pointerdown",
                    function (event) {

                        event.preventDefault();

                        event.stopPropagation();

                        startConnection(
                            event,
                            node,
                            handle
                        );

                    }
                );

            }
        );


        /* --------------------------------------------------------
           NODE DRAGGING
           -------------------------------------------------------- */

        node.addEventListener(
            "pointerdown",
            function (event) {

                if (
                    event.target.closest(
                        ".pathway-handle"
                    )
                ) {
                    return;
                }

                if (
                    event.target.closest(
                        ".pathway-node-remove"
                    )
                ) {
                    return;
                }

                startNodeDrag(
                    event,
                    node
                );

            }
        );

    }


    /* ============================================================
       MOVE NODE
       ============================================================ */

    function startNodeDrag(event, node) {

    event.preventDefault();

    event.stopPropagation();


    const id =
        node.dataset.courseId;


    const viewportRect =
        pathwayViewport.getBoundingClientRect();


    const position =
        pathwayLayout.positions[id] ||
        {
            x: 0,
            y: 0
        };


    /*
     * Convert the mouse position from screen
     * coordinates into pathway-world coordinates.
     */

    const mouseWorldX =
        (
            event.clientX -
            viewportRect.left -
            pathwayPanX
        ) /
        pathwayZoom;


    const mouseWorldY =
        (
            event.clientY -
            viewportRect.top -
            pathwayPanY
        ) /
        pathwayZoom;


    const offsetX =
        mouseWorldX -
        position.x;


    const offsetY =
        mouseWorldY -
        position.y;


    node.classList.add(
        "dragging"
    );


    function move(moveEvent) {

        const currentWorldX =
            (
                moveEvent.clientX -
                viewportRect.left -
                pathwayPanX
            ) /
            pathwayZoom;


        const currentWorldY =
            (
                moveEvent.clientY -
                viewportRect.top -
                pathwayPanY
            ) /
            pathwayZoom;


        const x =
            Math.max(
                0,
                currentWorldX -
                offsetX
            );


        const y =
            Math.max(
                0,
                currentWorldY -
                offsetY
            );


        node.style.left =
            x + "px";

        node.style.top =
            y + "px";


        pathwayLayout.positions[id] = {

            x: x,
            y: y

        };


        drawConnections();

    }


    function stop() {

        node.classList.remove(
            "dragging"
        );


        document.removeEventListener(
            "pointermove",
            move
        );


        document.removeEventListener(
            "pointerup",
            stop
        );


        savePathway();

    }


    document.addEventListener(
        "pointermove",
        move
    );


    document.addEventListener(
        "pointerup",
        stop,
        {
            once: true
        }
    );

}


    /* ============================================================
       CONNECTIONS
       ============================================================ */

    let connection = null;


    function startConnection(
    event,
    sourceNode,
    sourceHandle
) {

    const start =
        handlePoint(
            sourceHandle
        );


    const temp =
        document.createElementNS(
            "http://www.w3.org/2000/svg",
            "path"
        );


    temp.classList.add(
        "pathway-temp-line"
    );


    pathwaySvg.appendChild(
        temp
    );


    connection = {

        source:
            sourceNode.dataset.courseId,

        start:
            start,

        temp:
            temp

    };


    document.addEventListener(
        "pointermove",
        moveConnection
    );


    document.addEventListener(
        "pointerup",
        finishConnection,
        {
            once: true
        }
    );


    moveConnection(event);

}


   function moveConnection(event) {

    if (!connection) {
        return;
    }


    const rect =
        pathwayViewport.getBoundingClientRect();


    /*
     * Convert screen coordinates
     * into pathway-world coordinates.
     */

    const x =
        (
            event.clientX -
            rect.left -
            pathwayPanX
        ) /
        pathwayZoom;


    const y =
        (
            event.clientY -
            rect.top -
            pathwayPanY
        ) /
        pathwayZoom;


    connection.temp.setAttribute(
        "d",
        bezier(
            connection.start.x,
            connection.start.y,
            x,
            y
        )
    );

}


    function finishConnection(event) {

        document.removeEventListener(
            "pointermove",
            moveConnection
        );


        if (!connection) {
            return;
        }


        const target =
            document
                .elementFromPoint(
                    event.clientX,
                    event.clientY
                )
                ?.closest(
                    ".pathway-node"
                );


        if (
            target &&
            target.dataset.courseId &&
            target.dataset.courseId !==
                connection.source
        ) {

            const targetId =
                target.dataset.courseId;


            const exists =
                pathwayLayout.connections.some(
                    item =>
                        item.from ===
                            connection.source &&
                        item.to ===
                            targetId
                );


            if (!exists) {

                pathwayLayout.connections.push({

                    from:
                        connection.source,

                    to:
                        targetId

                });

            }

        }


        connection.temp.remove();

        connection = null;

        savePathway();

        drawConnections();

    }


    /* ============================================================
       DRAW CONNECTIONS
       ============================================================ */

function handlePoint(handle) {

    const node =
        handle.closest(".pathway-node");

    if (!node) {
        return {
            x: 0,
            y: 0
        };
    }

    const nodeX =
        parseFloat(node.style.left) || 0;

    const nodeY =
        parseFloat(node.style.top) || 0;

    const nodeWidth =
        node.offsetWidth;

    const nodeHeight =
        node.offsetHeight;

    const side =
        handle.dataset.side;

    switch (side) {

        case "top":
            return {
                x: nodeX + nodeWidth / 2,
                y: nodeY
            };

        case "right":
            return {
                x: nodeX + nodeWidth,
                y: nodeY + nodeHeight / 2
            };

        case "bottom":
            return {
                x: nodeX + nodeWidth / 2,
                y: nodeY + nodeHeight
            };

        case "left":
            return {
                x: nodeX,
                y: nodeY + nodeHeight / 2
            };

        default:
            return {
                x: nodeX + nodeWidth / 2,
                y: nodeY + nodeHeight / 2
            };

    }

}


function getConnectionPoints(
    source,
    target
) {

    const sourceX =
        parseFloat(source.style.left) || 0;

    const sourceY =
        parseFloat(source.style.top) || 0;

    const targetX =
        parseFloat(target.style.left) || 0;

    const targetY =
        parseFloat(target.style.top) || 0;


    const sourceWidth =
        source.offsetWidth;

    const sourceHeight =
        source.offsetHeight;

    const targetWidth =
        target.offsetWidth;

    const targetHeight =
        target.offsetHeight;


    const sx =
        sourceX +
        sourceWidth / 2;

    const sy =
        sourceY +
        sourceHeight / 2;

    const tx =
        targetX +
        targetWidth / 2;

    const ty =
        targetY +
        targetHeight / 2;


    const dx =
        tx - sx;

    const dy =
        ty - sy;


    let sourceSide;
    let targetSide;


    if (
        Math.abs(dx) >
        Math.abs(dy)
    ) {

        if (dx > 0) {

            sourceSide = "right";
            targetSide = "left";

        }
        else {

            sourceSide = "left";
            targetSide = "right";

        }

    }
    else {

        if (dy > 0) {

            sourceSide = "bottom";
            targetSide = "top";

        }
        else {

            sourceSide = "top";
            targetSide = "bottom";

        }

    }


    return {

        start:
            handlePoint(
                source.querySelector(
                    `.pathway-handle.${sourceSide}`
                )
            ),

        end:
            handlePoint(
                target.querySelector(
                    `.pathway-handle.${targetSide}`
                )
            )

    };

}


    function bezier(
        x1,
        y1,
        x2,
        y2
    ) {

        const distance =
            Math.max(
                50,
                Math.abs(x2 - x1) * 0.5
            );


        const direction =
            x2 >= x1 ? 1 : -1;


        return `
            M ${x1} ${y1}
            C
            ${x1 + distance * direction} ${y1},
            ${x2 - distance * direction} ${y2},
            ${x2} ${y2}
        `;

    }


    function drawConnections() {

    if (!pathwaySvg) {
        return;
    }

    pathwaySvg.innerHTML = "";

    pathwayLayout.connections =
        pathwayLayout.connections.filter(
            connection =>
                pathwayIds.includes(connection.from) &&
                pathwayIds.includes(connection.to)
        );

    pathwayLayout.connections.forEach(
        (connection, index) => {

            const source =
                pathwayNodes.querySelector(
                    `[data-course-id="${CSS.escape(connection.from)}"]`
                );

            const target =
                pathwayNodes.querySelector(
                    `[data-course-id="${CSS.escape(connection.to)}"]`
                );

            if (!source || !target) {
                return;
            }

            const points =
                getConnectionPoints(
                    source,
                    target
                );

            const pathData =
                bezier(
                    points.start.x,
                    points.start.y,
                    points.end.x,
                    points.end.y
                );


            /* ========================================================
               CLICKABLE HIT AREA
               ======================================================== */

           const hitArea =
    document.createElementNS(
        "http://www.w3.org/2000/svg",
        "path"
    );

hitArea.classList.add(
    "pathway-line-hit"
);

hitArea.setAttribute(
    "d",
    pathData
);

hitArea.setAttribute(
    "fill",
    "none"
);

hitArea.setAttribute(
    "stroke",
    "transparent"
);

hitArea.setAttribute(
    "stroke-width",
    "24"
);

hitArea.setAttribute(
    "pointer-events",
    "all"
);

hitArea.addEventListener(
    "click",
    function (event) {

        event.preventDefault();
        event.stopPropagation();

        pathwayLayout.connections =
            pathwayLayout.connections.filter(
                (_, connectionIndex) =>
                    connectionIndex !== index
            );

        savePathway();
        drawConnections();
    }
);


            /* ========================================================
               VISIBLE LINE
               ======================================================== */

            const line =
                document.createElementNS(
                    "http://www.w3.org/2000/svg",
                    "path"
                );

            line.classList.add(
                "pathway-line"
            );

            line.setAttribute(
                "d",
                pathData
            );

            line.setAttribute(
                "fill",
                "none"
            );

            /*
             * The visible line must NEVER capture clicks.
             */
            line.setAttribute(
                "pointer-events",
                "none"
            );


            /*
             * IMPORTANT:
             * Put the clickable hit area underneath the visible
             * line in the SVG, but because the visible line has
             * pointer-events:none, the hit area remains clickable.
             */
            pathwaySvg.appendChild(
                hitArea
            );

            pathwaySvg.appendChild(
                line
            );
        }
    );
}


    /* ============================================================
       PATHWAY UI
       ============================================================ */

    function updatePathwayUI() {

        const count =
            pathwayIds.length;


        pathwayCount.textContent =
            count;


        pathwaySummaryCount.textContent =
            `${count} ${
                count === 1
                    ? "course"
                    : "courses"
            }`;


        if (!count) {

            pathwayEmpty.style.display =
                "block";

            pathwayContent.style.display =
                "none";

        }
        else {

            pathwayEmpty.style.display =
                "none";

            pathwayContent.style.display =
                "block";

            applyViewModeUI();

            renderActiveView();

        }

    }


    function updateCoursePathwayStates() {

        board
            .querySelectorAll(
                ".training-course-card"
            )
            .forEach(
                card => {

                    card.classList.toggle(
                        "in-pathway",
                        pathwayIds.includes(
                            card.dataset.courseId
                        )
                    );

                }
            );

    }


    /* ============================================================
       INFORMATION PANEL
       ============================================================ */

    function closeInfoPanel() {

        infoPanel.classList.remove(
            "open"
        );

        infoPanel.setAttribute(
            "aria-hidden",
            "true"
        );

    }


    function openInfoPanel(html) {

        closePathwayPanel();

        infoContent.innerHTML =
            html;

        infoPanel.classList.add(
            "open"
        );

        infoPanel.setAttribute(
            "aria-hidden",
            "false"
        );


        infoContent
            .querySelectorAll(
                ".small-pathway-button"
            )
            .forEach(
                button => {

                    button.addEventListener(
                        "click",
                        function () {

                            const course =
                                courseLookup[
                                    this.dataset.courseId
                                ];

                            if (!course) {
                                return;
                            }


                            if (
                                isCourseInPathway(
                                    course
                                )
                            ) {

                                removeFromPathway(
                                    course
                                );

                                this.classList.remove(
                                    "added"
                                );

                                this.textContent =
                                    "+ Add";

                            }
                            else {

                                addToPathway(
                                    course
                                );

                                this.classList.add(
                                    "added"
                                );

                                this.textContent =
                                    "✓ In pathway";

                            }

                        }
                    );

                }
            );

    }


    function showCourseInfo(
        course,
        topicName
    ) {

        const added =
            isCourseInPathway(
                course
            );


        openInfoPanel(`

            <div class="info-type">
                Training course
            </div>

            <h2>
                ${escapeHtml(
                    course.title ||
                    "Untitled course"
                )}
            </h2>

            ${
                course.organisation
                    ? `
                        <div class="map-course-organisation">
                            ${escapeHtml(
                                course.organisation
                            )}
                        </div>
                    `
                    : ""
            }

            ${
                course.format
                    ? `
                        <div class="info-meta">
                            ${formatIcon(course.format)}
                            ${escapeHtml(
                                formatLabel(
                                    course.format
                                )
                            )}
                        </div>
                    `
                    : ""
            }

            ${
                course.dates &&
                course.format !==
                    "Online (self-service)"
                    ? `
                        <div class="info-meta">
                            📅
                            ${escapeHtml(
                                course.dates
                            )}
                        </div>
                    `
                    : ""
            }

            <div class="info-section">

                <h3>Topic</h3>

                <span class="course-topic-tag">
                    ${escapeHtml(topicName)}
                </span>

            </div>

            <div class="course-pathway-action">

                <button
                    type="button"
                    id="course-pathway-button"
                    class="
                        pathway-course-button
                        ${added ? "added" : ""}
                    "
                >
                    ${
                        added
                            ? "✓ Added to my pathway"
                            : "+ Add to my pathway"
                    }
                </button>

            </div>

            ${
                course.url
                    ? `
                        <a
                            href="${escapeHtml(course.url)}"
                            target="_blank"
                            rel="noopener"
                            class="primary-course-button"
                        >
                            View course →
                        </a>
                    `
                    : ""
            }

        `);


        const button =
            document.getElementById(
                "course-pathway-button"
            );


        if (button) {

            button.addEventListener(
                "click",
                function () {

                    if (
                        isCourseInPathway(
                            course
                        )
                    ) {

                        removeFromPathway(
                            course
                        );

                        this.classList.remove(
                            "added"
                        );

                        this.textContent =
                            "+ Add to my pathway";

                    }
                    else {

                        addToPathway(
                            course
                        );

                        this.classList.add(
                            "added"
                        );

                        this.textContent =
                            "✓ Added to my pathway";

                    }

                }
            );

        }

    }


    /* ============================================================
       TOPIC INFO
       ============================================================ */

    function showTopicInfo(
        topicName,
        topicCourses,
        groupName
    ) {

        openInfoPanel(`

            <div class="info-type">
                Training topic
            </div>

            <h2>
                ${escapeHtml(topicName)}
            </h2>

            <div class="info-breadcrumb">
                ${escapeHtml(groupName)}
            </div>

            <div class="info-stat">

                <strong>
                    ${topicCourses.length}
                </strong>

                <span>
                    ${
                        topicCourses.length === 1
                            ? "course"
                            : "courses"
                    }
                </span>

            </div>

            <div class="info-section">

                <h3>
                    Available training
                </h3>

                <div class="course-list">

                    ${
                        topicCourses
                            .map(
                                course =>
                                    createInfoCourseCard(
                                        course
                                    )
                            )
                            .join("")
                    }

                </div>

            </div>

        `);

    }


    function createInfoCourseCard(course) {

        const added =
            isCourseInPathway(
                course
            );


        return `

            <article class="map-course-card">

                ${
                    course.organisation
                        ? `
                            <div class="map-course-organisation">
                                ${escapeHtml(
                                    course.organisation
                                )}
                            </div>
                        `
                        : ""
                }

                <h4>
                    ${escapeHtml(
                        course.title ||
                        "Untitled course"
                    )}
                </h4>

                ${
                    course.format
                        ? `
                            <div class="map-course-meta">
                                ${formatIcon(
                                    course.format
                                )}
                                ${escapeHtml(
                                    formatLabel(
                                        course.format
                                    )
                                )}
                            </div>
                        `
                        : ""
                }

                <div class="info-card-actions">

                    ${
                        course.url
                            ? `
                                <a
                                    href="${escapeHtml(
                                        course.url
                                    )}"
                                    target="_blank"
                                    rel="noopener"
                                    class="map-course-link"
                                >
                                    View course →
                                </a>
                            `
                            : ""
                    }

                    <button
                        type="button"
                        class="small-pathway-button ${
                            added ? "added" : ""
                        }"
                        data-course-id="${escapeHtml(
                            courseIndex(course)
                        )}"
                    >
                        ${
                            added
                                ? "✓ In pathway"
                                : "+ Add"
                        }
                    </button>

                </div>

            </article>

        `;

    }


    /* ============================================================
       OPEN / CLOSE PATHWAY
       ============================================================ */

    function openPathwayPanel() {

        closeInfoPanel();

        pathwayPanel.classList.add(
            "open"
        );

        pathwayPanel.setAttribute(
            "aria-hidden",
            "false"
        );

        pathwayBackdrop.classList.add(
            "open"
        );

        pathwayBackdrop.setAttribute(
            "aria-hidden",
            "false"
        );

        document.body.classList.add(
            "pathway-scroll-lock"
        );

        updatePathwayUI();

    }


    function closePathwayPanel() {

        pathwayPanel.classList.remove(
            "open"
        );

        pathwayPanel.setAttribute(
            "aria-hidden",
            "true"
        );

        pathwayBackdrop.classList.remove(
            "open"
        );

        pathwayBackdrop.setAttribute(
            "aria-hidden",
            "true"
        );

        document.body.classList.remove(
            "pathway-scroll-lock"
        );

    }


    pathwayBackdrop.addEventListener(
        "click",
        closePathwayPanel
    );


    openPathwayButton.addEventListener(
        "click",
        openPathwayPanel
    );

    pathwayZoomInButton.addEventListener(
    "click",
    function () {

        zoomPathway(
            pathwayZoomStep
        );

    }
);


pathwayZoomOutButton.addEventListener(
    "click",
    function () {

        zoomPathway(
            1 / pathwayZoomStep
        );

    }
);


pathwayResetButton.addEventListener(
    "click",
    function () {

        resetPathwayView();

    }
);


    closePathwayButton.addEventListener(
        "click",
        closePathwayPanel
    );


    clearPathwayButton.addEventListener(
        "click",
        clearPathway
    );


    exploreTrainingButton.addEventListener(
        "click",
        closePathwayPanel
    );


    /* ============================================================
       BUILD MAIN TRAINING BOARD
       ============================================================ */

    const groups = [];


    Object.entries(topicGroups).forEach(
        ([groupName, groupData]) => {

            const topics =
                groupData.topics
                    .filter(
                        topic =>
                            coursesByTopic[topic] &&
                            coursesByTopic[topic].length
                    )
                    .map(
                        topic => ({
                            name: topic,
                            courses:
                                coursesByTopic[topic]
                        })
                    );


            if (topics.length) {

                groups.push({

                    name: groupName,
                    icon: groupData.icon,
                    topics: topics,

                    courseCount:
                        topics.reduce(
                            (total, topic) =>
                                total +
                                topic.courses.length,
                            0
                        )

                });

            }

        }
    );


    loadingMessage.style.display =
        "none";


    /* ============================================================
       CREATE BOARD
       ============================================================ */

    groups.forEach(
        group => {

            const groupCard =
                document.createElement(
                    "section"
                );

            groupCard.className =
                "training-group-card";

            groupCard.dataset.group =
                group.name;

            groupCard.id =
                `group-${slugify(
                    group.name
                )}`;


            groupCard.innerHTML = `

                <div class="training-group-header">

                    <div class="group-title-row">

                        <div class="group-icon">
                            ${group.icon}
                        </div>

                        <div>

                            <h2>
                                ${escapeHtml(
                                    group.name
                                )}
                            </h2>

                            <div class="group-summary">
                                ${group.topics.length}
                                ${
                                    group.topics.length === 1
                                        ? "topic"
                                        : "topics"
                                }

                                <span class="summary-dot">
                                    •
                                </span>

                                ${group.courseCount}
                                ${
                                    group.courseCount === 1
                                        ? "course"
                                        : "courses"
                                }

                            </div>

                        </div>

                    </div>

                </div>

            `;


            const topicGrid =
                document.createElement(
                    "div"
                );

            topicGrid.className =
                "topic-grid";


            group.topics.forEach(
                topic => {

                    const topicCard =
                        document.createElement(
                            "article"
                        );

                    topicCard.className =
                        "training-topic-card";


                    topicCard.id =
                        `topic-${slugify(
                            group.name
                        )}-${slugify(
                            topic.name
                        )}`;


                    const header =
                        document.createElement(
                            "div"
                        );

                    header.className =
                        "topic-card-header";


                    header.innerHTML = `

                        <div class="topic-title">

                            <span class="topic-marker"></span>

                            <h3>
                                ${escapeHtml(
                                    topic.name
                                )}
                            </h3>

                        </div>

                        <span class="topic-count">
                            ${topic.courses.length}
                        </span>

                    `;


                    topicCard.appendChild(
                        header
                    );


                    const courseList =
                        document.createElement(
                            "div"
                        );

                    courseList.className =
                        "topic-course-list";


                    topic.courses.forEach(
                        course => {

                            const card =
                                document.createElement(
                                    "button"
                                );

                            card.type =
                                "button";

                            card.className =
                                "training-course-card";

                            card.dataset.courseId =
                                courseIndex(course);


                            card.innerHTML = `

                                <span class="course-card-title-row">

                                    <span class="course-card-title">
                                        ${escapeHtml(
                                            course.title ||
                                            "Untitled course"
                                        )}
                                    </span>

                                    <span class="course-pathway-status">
                                        ✓
                                    </span>

                                </span>

                                ${
                                    course.organisation
                                        ? `
                                            <span class="course-card-organisation">
                                                ${escapeHtml(
                                                    course.organisation
                                                )}
                                            </span>
                                        `
                                        : ""
                                }

                                <span class="course-card-meta">

                                    ${
                                        course.format
                                            ? `
                                                <span>
                                                    ${formatIcon(
                                                        course.format
                                                    )}
                                                    ${escapeHtml(
                                                        formatLabel(
                                                            course.format
                                                        )
                                                    )}
                                                </span>
                                            `
                                            : ""
                                    }

                                    ${
                                        course.dates &&
                                        course.format !==
                                            "Online (self-service)"
                                            ? `
                                                <span>
                                                    📅
                                                    ${escapeHtml(
                                                        course.dates
                                                    )}
                                                </span>
                                            `
                                            : ""
                                    }

                                </span>

                            `;


                            if (
                                isCourseInPathway(
                                    course
                                )
                            ) {
                                card.classList.add(
                                    "in-pathway"
                                );
                            }


                            card.addEventListener(
                                "click",
                                function () {

                                    showCourseInfo(
                                        course,
                                        topic.name
                                    );

                                }
                            );


                            courseList.appendChild(
                                card
                            );

                        }
                    );


                    topicCard.appendChild(
                        courseList
                    );


                    header.addEventListener(
                        "click",
                        function () {

                            showTopicInfo(
                                topic.name,
                                topic.courses,
                                group.name
                            );

                        }
                    );


                    topicGrid.appendChild(
                        topicCard
                    );

                }
            );


            groupCard.appendChild(
                topicGrid
            );

            board.appendChild(
                groupCard
            );

        }
    );


    /* ============================================================
       BOARD ZOOM / PAN
       ============================================================ */

    let zoom =
        config.initialZoom;

    let panX = 0;
    let panY = 0;

    let boardDragging = false;

    let dragStartX = 0;
    let dragStartY = 0;

    let startPanX = 0;
    let startPanY = 0;


    function updateBoardTransform() {

        board.style.transform =
            `translate(
                ${panX}px,
                ${panY}px
            )
            scale(${zoom})`;


        zoomIndicator.textContent =
            `${Math.round(
                zoom * 100
            )}%`;

    }


    boardWrapper.addEventListener(
        "pointerdown",
        function (event) {

            if (
                event.target.closest(
                    "button, a, input"
                )
            ) {
                return;
            }


            boardDragging = true;

            dragStartX =
                event.clientX;

            dragStartY =
                event.clientY;

            startPanX =
                panX;

            startPanY =
                panY;

            boardWrapper.classList.add(
                "is-panning"
            );

        }
    );


    boardWrapper.addEventListener(
        "pointermove",
        function (event) {

            if (!boardDragging) {
                return;
            }

            panX =
                startPanX +
                event.clientX -
                dragStartX;

            panY =
                startPanY +
                event.clientY -
                dragStartY;

            updateBoardTransform();

        }
    );


    boardWrapper.addEventListener(
        "pointerup",
        function () {

            boardDragging = false;

            boardWrapper.classList.remove(
                "is-panning"
            );

        }
    );


    boardWrapper.addEventListener(
        "pointercancel",
        function () {

            boardDragging = false;

            boardWrapper.classList.remove(
                "is-panning"
            );

        }
    );


    function zoomAroundCentre(
        factor
    ) {

        zoom =
            Math.max(
                config.minZoom,
                Math.min(
                    config.maxZoom,
                    zoom * factor
                )
            );

        updateBoardTransform();

    }


    zoomInButton.addEventListener(
        "click",
        function () {
            zoomAroundCentre(
                config.zoomStep
            );
        }
    );


    zoomOutButton.addEventListener(
        "click",
        function () {
            zoomAroundCentre(
                1 / config.zoomStep
            );
        }
    );


    resetButton.addEventListener(
        "click",
        function () {

            searchInput.value = "";

            zoom =
                config.initialZoom;

            panX = 0;
            panY = 0;

            updateBoardTransform();

            closeInfoPanel();

        }
    );


    /* ============================================================
       SEARCH
       ============================================================ */

    searchInput.addEventListener(
        "input",
        function () {

            const query =
                this.value
                    .trim()
                    .toLowerCase();


            board
                .querySelectorAll(
                    ".search-match"
                )
                .forEach(
                    element =>
                        element.classList.remove(
                            "search-match"
                        )
                );


            if (!query) {
                return;
            }


            groups.forEach(
                group => {

                    const groupMatch =
                        group.name
                            .toLowerCase()
                            .includes(
                                query
                            );


                    const matchingTopics =
                        group.topics.filter(
                            topic => {

                                return (
                                    topic.name
                                        .toLowerCase()
                                        .includes(
                                            query
                                        ) ||

                                    topic.courses.some(
                                        course =>
                                            (
                                                course.title ||
                                                ""
                                            )
                                            .toLowerCase()
                                            .includes(
                                                query
                                            )
                                    )
                                );

                            }
                        );


                    if (
                        groupMatch ||
                        matchingTopics.length
                    ) {

                        const element =
                            document.getElementById(
                                `group-${slugify(
                                    group.name
                                )}`
                            );

                        if (element) {

                            element.classList.add(
                                "search-match"
                            );

                        }

                    }


                    matchingTopics.forEach(
                        topic => {

                            const element =
                                document.getElementById(
                                    `topic-${slugify(
                                        group.name
                                    )}-${slugify(
                                        topic.name
                                    )}`
                                );

                            if (element) {

                                element.classList.add(
                                    "search-match"
                                );

                            }

                        }
                    );

                }
            );

        }
    );


    /* ============================================================
       INFO PANEL
       ============================================================ */

    closeInfoButton.addEventListener(
        "click",
        closeInfoPanel
    );


    /* ============================================================
       KEYBOARD
       ============================================================ */

    document.addEventListener(
        "keydown",
        function (event) {

            if (
                event.key === "Escape"
            ) {

                closeInfoPanel();
                closePathwayPanel();

            }

        }
    );


    /* ============================================================
       DOWNLOAD
       ============================================================ */

    if (downloadPathwayButton) {

        downloadPathwayButton.addEventListener(
            "click",
            downloadPathway
        );

    }


    function downloadPathway() {

        if (!pathwayIds.length) {

            alert(
                "Your learning pathway is empty."
            );

            return;

        }


        let html = null;

        let filename =
            "my-shareing-learning-pathway.html";


        if (pathwayViewMode === "map") {

            html =
                buildMapDownloadHtml();

            filename =
                "my-shareing-learning-pathway-map.html";

        }


        /*
         * Fall back to the list export if the map export
         * could not be built (e.g. the canvas was not
         * rendered for some reason).
         */

        if (!html) {

            html =
                buildListDownloadHtml();

            filename =
                "my-shareing-learning-pathway.html";

        }


        triggerHtmlDownload(
            html,
            filename
        );

    }


    function triggerHtmlDownload(html, filename) {

        const blob =
            new Blob(
                [html],
                {
                    type:
                        "text/html;charset=utf-8"
                }
            );


        const url =
            URL.createObjectURL(
                blob
            );


        const link =
            document.createElement(
                "a"
            );


        link.href =
            url;

        link.download =
            filename;


        document.body.appendChild(
            link
        );

        link.click();

        link.remove();

        URL.revokeObjectURL(
            url
        );

    }


    /* ------------------------------------------------------------
       LIST EXPORT
       ------------------------------------------------------------ */

    function buildListDownloadHtml() {

        const rows =
            pathwayIds
                .map(
                    id =>
                        courseLookup[id]
                )
                .filter(Boolean)
                .map(
                    (course, index) => `

                        <article class="course">

                            <div class="number">
                                ${index + 1}
                            </div>

                            <div>

                                <h2>
                                    ${
                                        course.url
                                            ? `
                                                <a href="${escapeHtml(
                                                    course.url
                                                )}">
                                                    ${escapeHtml(
                                                        course.title ||
                                                        "Untitled course"
                                                    )}
                                                </a>
                                              `
                                            :
                                            escapeHtml(
                                                course.title ||
                                                "Untitled course"
                                            )
                                    }
                                </h2>

                                ${
                                    course.organisation
                                        ? `
                                            <p>
                                                ${escapeHtml(
                                                    course.organisation
                                                )}
                                            </p>
                                          `
                                        : ""
                                }

                                <small>
                                    ${escapeHtml(
                                        getPrimaryTopic(
                                            course
                                        )
                                    )}
                                </small>

                            </div>

                        </article>

                    `
                )
                .join("");


        return `

            <!DOCTYPE html>

            <html lang="en">

            <head>

                <meta charset="UTF-8">

                <title>
                    My SHAREing Learning Pathway
                </title>

                <style>

                    body {
                        font-family:
                            Arial,
                            sans-serif;

                        max-width: 900px;

                        margin: 40px auto;

                        padding: 20px;

                        color: #334155;
                    }

                    h1 {
                        color: #002a41;
                    }

                    .course {
                        display: flex;

                        gap: 20px;

                        margin-bottom: 15px;

                        padding: 20px;

                        border:
                            1px solid #e2e8f0;

                        border-radius: 10px;
                    }

                    .number {
                        font-weight: bold;

                        color: #940594;
                    }

                    h2 {
                        margin: 0 0 5px;

                        font-size: 1.1rem;
                    }

                    a {
                        color: #002a41;

                        text-decoration: none;
                    }

                    p {
                        color: #940594;

                        font-size: .8rem;
                    }

                    small {
                        color: #64748b;
                    }

                </style>

            </head>

            <body>

                <h1>
                    My Learning Pathway
                </h1>

                ${rows}

            </body>

            </html>

        `;

    }


    /* ------------------------------------------------------------
       MAP EXPORT
       Snapshots the cards at their current dragged positions and
       the connector lines exactly as drawn on screen, by reading
       the live map DOM (same geometry helpers the on-screen map
       already uses: handlePoint / getConnectionPoints / bezier).
       ------------------------------------------------------------ */

    function buildMapDownloadHtml() {

        if (!pathwayNodes) {
            return null;
        }

        const nodeElements =
            Array.from(
                pathwayNodes.querySelectorAll(
                    ".pathway-node"
                )
            );

        if (!nodeElements.length) {
            return null;
        }


        let minX = Infinity;
        let minY = Infinity;
        let maxX = -Infinity;
        let maxY = -Infinity;

        const nodeData =
            nodeElements.map(
                element => {

                    const x =
                        parseFloat(element.style.left) || 0;

                    const y =
                        parseFloat(element.style.top) || 0;

                    const w =
                        element.offsetWidth;

                    const h =
                        element.offsetHeight;

                    minX = Math.min(minX, x);
                    minY = Math.min(minY, y);
                    maxX = Math.max(maxX, x + w);
                    maxY = Math.max(maxY, y + h);

                    return {
                        id: element.dataset.courseId,
                        x: x,
                        y: y,
                        w: w,
                        h: h
                    };

                }
            );


        const padding = 40;

        const offsetX =
            padding - minX;

        const offsetY =
            padding - minY;

        const canvasWidth =
            (maxX - minX) + padding * 2;

        const canvasHeight =
            (maxY - minY) + padding * 2;


        const validConnections =
            pathwayLayout.connections.filter(
                connection =>
                    pathwayIds.includes(connection.from) &&
                    pathwayIds.includes(connection.to)
            );

        const pathsSvg =
            validConnections
                .map(
                    connection => {

                        const source =
                            pathwayNodes.querySelector(
                                `[data-course-id="${CSS.escape(connection.from)}"]`
                            );

                        const target =
                            pathwayNodes.querySelector(
                                `[data-course-id="${CSS.escape(connection.to)}"]`
                            );

                        if (!source || !target) {
                            return "";
                        }

                        const points =
                            getConnectionPoints(
                                source,
                                target
                            );

                        const d =
                            bezier(
                                points.start.x + offsetX,
                                points.start.y + offsetY,
                                points.end.x + offsetX,
                                points.end.y + offsetY
                            );

                        return `<path d="${d}" fill="none" stroke="#940594" stroke-width="2.5" opacity="0.75" />`;

                    }
                )
                .join("");


        const cardsHtml =
            nodeData
                .map(
                    data => {

                        const course =
                            courseLookup[data.id];

                        if (!course) {
                            return "";
                        }

                        const topic =
                            getPrimaryTopic(course);

                        const metaParts = [
                            topic,
                            course.format
                                ? formatLabel(course.format)
                                : null
                        ].filter(Boolean);

                        return `

                            <div
                                class="map-card"
                                style="left:${data.x + offsetX}px; top:${data.y + offsetY}px; width:${data.w}px;"
                            >

                                <div class="map-card-title">
                                    ${
                                        course.url
                                            ? `
                                                <a href="${escapeHtml(course.url)}">
                                                    ${escapeHtml(
                                                        course.title ||
                                                        "Untitled course"
                                                    )}
                                                </a>
                                              `
                                            :
                                            escapeHtml(
                                                course.title ||
                                                "Untitled course"
                                            )
                                    }
                                </div>

                                ${
                                    course.organisation
                                        ? `
                                            <div class="map-card-org">
                                                ${escapeHtml(
                                                    course.organisation
                                                )}
                                            </div>
                                          `
                                        : ""
                                }

                                <div class="map-card-meta">
                                    ${escapeHtml(
                                        metaParts.join(" • ")
                                    )}
                                </div>

                            </div>

                        `;

                    }
                )
                .join("");


        return `

            <!DOCTYPE html>

            <html lang="en">

            <head>

                <meta charset="UTF-8">

                <title>
                    My SHAREing Learning Pathway – Map
                </title>

                <style>

                    body {
                        font-family:
                            Arial,
                            sans-serif;

                        margin: 40px;

                        color: #334155;

                        background: #f8fafc;
                    }

                    h1 {
                        color: #002a41;
                    }

                    .map-wrap {
                        position: relative;

                        width: ${canvasWidth}px;
                        height: ${canvasHeight}px;

                        margin-top: 20px;

                        overflow: auto;
                    }

                    .map-wrap svg {
                        position: absolute;

                        left: 0;
                        top: 0;

                        overflow: visible;

                        pointer-events: none;
                    }

                    .map-card {
                        position: absolute;

                        box-sizing: border-box;

                        padding: 14px 16px;

                        border:
                            1px solid #d8dee6;

                        border-radius: 12px;

                        background: #ffffff;

                        box-shadow:
                            0 4px 12px rgba(15, 23, 42, .08);
                    }

                    .map-card-title {
                        font-weight: 700;

                        font-size: .85rem;

                        color: #002a41;

                        line-height: 1.35;
                    }

                    .map-card-title a {
                        color: inherit;

                        text-decoration: none;
                    }

                    .map-card-title a:hover {
                        text-decoration: underline;
                    }

                    .map-card-org {
                        margin-top: 6px;

                        font-size: .65rem;

                        font-weight: 700;

                        text-transform: uppercase;

                        color: #940594;
                    }

                    .map-card-meta {
                        margin-top: 6px;

                        font-size: .68rem;

                        color: #64748b;
                    }

                </style>

            </head>

            <body>

                <h1>
                    My Learning Pathway – Map
                </h1>

                <div class="map-wrap">

                    <svg
                        width="${canvasWidth}"
                        height="${canvasHeight}"
                    >
                        ${pathsSvg}
                    </svg>

                    ${cardsHtml}

                </div>

            </body>

            </html>

        `;

    }


    /* ============================================================
       INITIALISE
       ============================================================ */

    updatePathwayUI();

    updateBoardTransform();

});


window.addEventListener(
    "scroll",
    function () {

        if (window.scrollY > 10) {

            document.body.classList.add(
                "scrolled"
            );

        }
        else {

            document.body.classList.remove(
                "scrolled"
            );

        }

    }
);

</script>


<!-- ============================================================
     STYLES
============================================================ -->

<style>

/* =========================================================
   PAGE INTRO
========================================================= */

.page-intro {
    margin: 0.8rem 0;
    padding: 0.8rem;
    background: #f8fafc;
    border-left: 5px solid #421456;
    border-radius: 12px;
    box-shadow: 0 2px 8px rgba(0,0,0,.05);
}

.page-intro h1 {
    margin: 0 0 .5rem;
    color: #0f2a3a;
    font-size: 0.8rem;
}

.page-intro p {
    margin: .1rem 0;
    color: #475569;
    font-size: .6rem;
}

.page-intro .disclaimer {
    margin-top: 0.2rem;
    font-size: .6rem;
    color: #334155;
}

/* ==============================================================
   MAP CANVAS
============================================================== */

.training-board-wrapper {

    position: relative;

    width: 100%;

    height: 78vh;

    min-height: 650px;

    max-height: 1000px;

    overflow: hidden;

    border: 1px solid #e2e8f0;

    border-radius: 14px;

    background-color: #f8fafc;

    background-image:
        radial-gradient(
            #cbd5e1 0.8px,
            transparent 0.8px
        );

    background-size: 24px 24px;

    cursor: grab;

    user-select: none;

    -webkit-user-select: none;

    touch-action: none;

}


.training-board-wrapper.is-panning {

    cursor: grabbing;

}


.training-board,
.training-board * {

    user-select: none;

    -webkit-user-select: none;

}


.training-board img,
.training-board svg {

    -webkit-user-drag: none;

}


.training-board {

    cursor: grab;
    backface-visibility: hidden;

}


.training-board-wrapper.is-panning .training-board {

    cursor: grabbing;

}


/* ==============================================================
   PAGE INTRO
============================================================== */

.training-map-intro {

    max-width: 950px;

    margin-bottom: 1.5rem;

}


.pathway-intro {

    margin-top: 1rem;

    padding: 0.9rem 1rem;

    border-left: 4px solid #940594;

    border-radius: 6px;

    background: #faf5fa;

    color: #475569;

    font-size: 0.6rem !important;

}


/* ==============================================================
   TOOLBAR
============================================================== */

.map-toolbar {

    display: flex;

    align-items: center;

    justify-content: space-between;

    gap: 1rem;

    margin: 1rem 0;

    flex-wrap: wrap;

}


.map-search-wrapper {

    flex: 1;

    min-width: 240px;

}


.map-search {

    width: 100%;

    box-sizing: border-box;

    padding: 0.75rem 1rem;

    border: 1px solid #cbd5e1;

    border-radius: 8px;

    background: #ffffff;

    font-size: 0.95rem;

}


.map-search:focus {

    outline: none;

    border-color: #940594;

    box-shadow:
        0 0 0 3px
        rgba(
            148,
            5,
            148,
            0.12
        );

}


.map-controls {

    display: flex;

    align-items: center;

    gap: 0.5rem;

    flex-wrap: wrap;

}


.map-control-button {

    border: 1px solid #cbd5e1;

    background: #ffffff;

    color: #334155;

    padding: 0.65rem 0.85rem;

    border-radius: 7px;

    cursor: pointer;

    font-size: 0.9rem;

    transition:
        background 0.15s ease,
        border-color 0.15s ease,
        transform 0.15s ease;

}


.map-control-button:hover {

    background: #f8fafc;

    border-color: #940594;

}


.map-control-button:active {

    transform: translateY(1px);

}


/* ==============================================================
   PATHWAY BUTTON
============================================================== */

.pathway-button {

    display: inline-flex;

    align-items: center;

    gap: 0.45rem;

    border: 1px solid #940594;

    background: #940594;

    color: #ffffff;

    padding: 0.65rem 0.9rem;

    border-radius: 7px;

    cursor: pointer;

    font-size: 0.9rem;

    font-weight: 700;

    transition:
        background 0.15s ease,
        transform 0.15s ease;

}


.pathway-button:hover {

    background: #740574;

}


.pathway-count {

    display: inline-flex;

    align-items: center;

    justify-content: center;

    min-width: 20px;

    height: 20px;

    padding: 0 0.25rem;

    box-sizing: border-box;

    border-radius: 999px;

    background: #ffffff;

    color: #940594;

    font-size: 0.7rem;

}


/* ==============================================================
   BOARD
============================================================== */

.training-board {

    position: absolute;

    left: 0;

    top: 0;

    display: grid;

    grid-template-columns:
        repeat(
            3,
            minmax(
                390px,
                1fr
            )
        );

    gap: 28px;

    width: max-content;

    min-width: 1280px;

    padding: 50px;

    box-sizing: border-box;

    transform-origin: 0 0;

   

}


/* ==============================================================
   GROUP CARDS
============================================================== */

.training-group-card {

    position: relative;

    box-sizing: border-box;

    width: 100%;

    min-width: 390px;

    height: auto;

    align-self: start;

    padding: 1.2rem;

    border:
        1px solid
        #d8b8d8;

    border-radius: 16px;

    background:
        rgba(
            255,
            255,
            255,
            0.97
        );

    box-shadow:
        0 5px 18px
        rgba(
            15,
            23,
            42,
            0.07
        );

    transition:
        border-color 0.2s ease,
        box-shadow 0.2s ease;

}


.training-group-card.search-match {

    border-color: #940594;

    box-shadow:
        0 0 0 4px
        rgba(
            148,
            5,
            148,
            0.13
        ),
        0 8px 25px
        rgba(
            148,
            5,
            148,
            0.12
        );

}


/* ==============================================================
   GROUP HEADER
============================================================== */

.training-group-header {

    margin-bottom: 1rem;

    padding-bottom: 1rem;

    border-bottom:
        1px solid
        #f1e5f1;

}


.group-title-row {

    display: flex;

    align-items: center;

    gap: 0.8rem;

}


.group-icon {

    flex:
        0 0
        46px;

    width: 46px;

    height: 46px;

    display: flex;

    align-items: center;

    justify-content: center;

    border-radius: 12px;

    background:
        linear-gradient(
            135deg,
            #940594,
            #740574
        );

    color: #ffffff;

    font-size: 1.4rem;

    box-shadow:
        0 4px 10px
        rgba(
            148,
            5,
            148,
            0.18
        );

}


.training-group-header h2 {

    margin: 0;

    color: #002a41;

    font-size: 1.25rem;

    line-height: 1.2;

}


.group-summary {

    display: flex;

    align-items: center;

    gap: 0.35rem;

    margin-top: 0.3rem;

    color: #64748b;

    font-size: 0.75rem;

}


.summary-dot {

    color: #c084c0;

}


/* ==============================================================
   TOPIC GRID
============================================================== */

.topic-grid {

    display: grid;

    gap: 16px;

    align-items: start;

}


.topic-grid.one-topic {

    grid-template-columns:
        minmax(
            0,
            1fr
        );

}


.topic-grid.two-topics {

    grid-template-columns:
        repeat(
            2,
            minmax(
                0,
                1fr
            )
        );

}


.topic-grid.many-topics {

    grid-template-columns:
        repeat(
            2,
            minmax(
                0,
                1fr
            )
        );

}


/* ==============================================================
   TOPIC CARD
============================================================== */

.training-topic-card {

    position: relative;

    min-width: 0;

    box-sizing: border-box;

    padding: 0.85rem;

    border:
        1px solid
        #e2e8f0;

    border-radius: 11px;

    background: #ffffff;

    box-shadow:
        0 2px 7px
        rgba(
            15,
            23,
            42,
            0.04
        );

}


.training-topic-card.search-match {

    border-color: #940594;

    box-shadow:
        0 0 0 3px
        rgba(
            148,
            5,
            148,
            0.13
        );

}


/* ==============================================================
   TOPIC HEADER
============================================================== */

.topic-card-header {

    display: flex;

    align-items: flex-start;

    justify-content: space-between;

    gap: 0.5rem;

    margin-bottom: 0.7rem;

    cursor: pointer;

}


.topic-title {

    display: flex;

    align-items: center;

    gap: 0.5rem;

    min-width: 0;

}


.topic-marker {

    flex:
        0 0
        9px;

    width: 9px;

    height: 9px;

    border-radius: 50%;

    background: #940594;

    box-shadow:
        0 0 0 3px
        rgba(
            148,
            5,
            148,
            0.1
        );

}


.topic-card-header h3 {

    margin: 0;

    color: #334155;

    font-size: 0.92rem;

    line-height: 1.25;

}


.topic-count {

    flex:
        0 0
        auto;

    padding:
        0.2rem
        0.45rem;

    border-radius: 999px;

    background: #f3e8f3;

    color: #740574;

    font-size: 0.65rem;

    font-weight: 700;

    white-space: nowrap;

}


/* ==============================================================
   COURSE LIST
============================================================== */

.topic-course-list {

    display: flex;

    flex-direction: column;

    gap: 6px;

}


/* ==============================================================
   COURSE CARD
============================================================== */

.training-course-card {

    display: flex;

    flex-direction: column;

    width: 100%;

    min-width: 0;

    box-sizing: border-box;

    padding: 0.65rem 0.7rem;

    border:
        1px solid
        #edf0f3;

    border-radius: 7px;

    background: #f8fafc;

    text-align: left;

    cursor: pointer;

    transition:
        border-color 0.15s ease,
        background 0.15s ease,
        transform 0.15s ease;

}


.training-course-card:hover {

    border-color: #c084c0;

    background: #ffffff;

    transform:
        translateY(-1px);

}


.training-course-card.in-pathway {

    border-color: #940594;

    background: #faf5fa;

}


.course-card-title-row {

    display: flex;

    align-items: flex-start;

    justify-content: space-between;

    gap: 0.4rem;

}


.course-card-title {

    color: #334155;

    font-size: 0.75rem;

    font-weight: 600;

    line-height: 1.3;

}


.course-pathway-status {

    display: none;

    flex:
        0 0
        auto;

    width: 18px;

    height: 18px;

    align-items: center;

    justify-content: center;

    border-radius: 50%;

    background: #940594;

    color: #ffffff;

    font-size: 0.65rem;

    font-weight: 700;

}


.training-course-card.in-pathway
.course-pathway-status {

    display: inline-flex;

}


.course-card-organisation {

    margin-top: 0.25rem;

    color: #940594;

    font-size: 0.62rem;

    font-weight: 700;

    line-height: 1.25;

    text-transform: uppercase;

    letter-spacing: 0.025em;

}


.course-card-meta {

    display: flex;

    flex-wrap: wrap;

    gap: 0.4rem;

    margin-top: 0.35rem;

    color: #64748b;

    font-size: 0.62rem;

    line-height: 1.3;

}


/* ==============================================================
   BOARD MESSAGE
============================================================== */

.board-message {

    position: absolute;

    inset: 0;

    display: flex;

    align-items: center;

    justify-content: center;

    color: #64748b;

    pointer-events: none;

}


/* ==============================================================
   ZOOM INDICATOR
============================================================== */

.zoom-indicator {

    position: absolute;

    right: 14px;

    bottom: 14px;

    z-index: 20;

    padding:
        0.35rem
        0.55rem;

    border:
        1px solid
        #e2e8f0;

    border-radius: 6px;

    background:
        rgba(
            255,
            255,
            255,
            0.92
        );

    color: #64748b;

    font-size: 0.7rem;

    pointer-events: none;

    box-shadow:
        0 2px 6px
        rgba(
            15,
            23,
            42,
            0.05
        );

}


/* ==============================================================
   LEGEND
============================================================== */

.map-legend {

    display: flex;

    justify-content: center;

    align-items: center;

    gap: 1.5rem;

    margin: 1rem 0 2rem;

    flex-wrap: wrap;

}


.legend-item {

    display: flex;

    align-items: center;

    gap: 0.4rem;

    color: #64748b;

    font-size: 0.8rem;

}


.legend-node {

    width: 12px;

    height: 12px;

    display: inline-block;

    border-radius: 50%;

}


.legend-node.group-node {

    background: #940594;

}


.legend-node.topic-node {

    background: #ffffff;

    border:
        2px solid
        #940594;

    box-sizing: border-box;

}


.legend-node.course-node {

    background: #e2e8f0;

    border:
        1px solid
        #94a3b8;

}


.pathway-legend-icon {

    font-size: 0.95rem;

}


/* ==============================================================
   INFORMATION PANEL
============================================================== */

.map-info-panel {
    position: fixed;
    z-index: 99999;

    top: 3rem;
    right: 0;

    height: calc(100vh - 2rem);

    box-sizing: border-box;

    padding: 2rem;

    overflow-y: auto;

    background: #ffffff;

    border-left: 1px solid #e2e8f0;

    box-shadow:
        -8px 0 30px
        rgba(15, 23, 42, 0.12);

    transform: translateX(105%);
    transition: transform 0.3s ease;
}

body.scrolled .map-info-panel {
    top: 0;
    height: 100vh;
}

.map-info-panel.open {

    transform:
        translateX(0);

}


.close-info-panel {

     position: absolute;
    z-index: 100000;
    top: 1rem;
    right: 1rem;


    width: 34px;

    height: 34px;

    border: 0;

    border-radius: 50%;

    background: #f1f5f9;

    color: #475569;

    font-size: 1.5rem;

    line-height: 1;

    cursor: pointer;

}


.close-info-panel:hover {

    background: #e2e8f0;

}


#map-info-content {

    padding-top: 1rem;

}


.info-type {

    margin-bottom: 0.5rem;

    color: #940594;

    font-size: 0.75rem;

    font-weight: 700;

    text-transform: uppercase;

    letter-spacing: 0.06em;

}


#map-info-content h2 {

    margin-top: 0;

    margin-bottom: 0.6rem;

    padding-right: 1.5rem;

    color: #002a41;

    line-height: 1.25;

}


#map-info-content h3 {

    margin-top: 1.5rem;

    margin-bottom: 0.75rem;

    color: #334155;

    font-size: 1rem;

}


.info-breadcrumb {

    color: #64748b;

    font-size: 0.8rem;

}


/* ==============================================================
   INFO STATS
============================================================== */

.info-stat {

    display: flex;

    align-items: baseline;

    gap: 0.5rem;

    margin: 1rem 0;

    padding: 0.9rem 1rem;

    border-radius: 8px;

    background: #f8fafc;

}


.info-stat strong {

    color: #940594;

    font-size: 1.5rem;

}


.info-stat span {

    color: #64748b;

    font-size: 0.85rem;

}


/* ==============================================================
   INFO COURSE CARDS
============================================================== */

.course-list {

    display: flex;

    flex-direction: column;

    gap: 0.8rem;

}


.map-course-card {

    padding: 1rem;

    border:
        1px solid
        #e2e8f0;

    border-radius: 8px;

    background: #ffffff;

}


.map-course-card:hover {

    border-color: #c084c0;

}


.map-course-organisation {

    margin-bottom: 0.3rem;

    color: #940594;

    font-size: 0.7rem;

    font-weight: 700;

    text-transform: uppercase;

    letter-spacing: 0.04em;

}


.map-course-card h4 {

    margin:
        0 0 0.7rem;

    color: #334155;

    font-size: 0.95rem;

    line-height: 1.35;

}


.map-course-meta {

    margin-top: 0.35rem;

    color: #64748b;

    font-size: 0.78rem;

}


.info-card-actions {

    display: flex;

    align-items: center;

    justify-content: space-between;

    gap: 0.75rem;

    margin-top: 0.75rem;

}


.map-course-link {

    color: #940594;

    font-size: 0.8rem;

    font-weight: 700;

    text-decoration: none;

}


.map-course-link:hover {

    text-decoration: underline;

}


.small-pathway-button {

    flex:
        0 0
        auto;

    padding:
        0.4rem
        0.6rem;

    border:
        1px solid
        #940594;

    border-radius: 6px;

    background: #ffffff;

    color: #940594;

    font-size: 0.7rem;

    font-weight: 700;

    cursor: pointer;

}


.small-pathway-button:hover {

    background: #faf5fa;

}


.small-pathway-button.added {

    background: #940594;

    color: #ffffff;

}


/* ==============================================================
   COURSE INFO
============================================================== */

.info-meta {

    margin: 0.5rem 0;

    color: #64748b;

    font-size: 0.85rem;

}


.course-topic-tag {

    display: inline-block;

    padding:
        0.35rem
        0.65rem;

    border-radius: 999px;

    background: #f3e8f3;

    color: #740574;

    font-size: 0.75rem;

}


.course-pathway-action {

    margin-top: 1.5rem;

}



.pathway-course-button {

    width: 100%;

    padding:
        0.8rem
        1rem;

    border:
        1px solid
        #940594;

    border-radius: 7px;

    background: #ffffff;

    color: #940594;

    font-size: 0.85rem;

    font-weight: 700;

    cursor: pointer;

    transition:
        background 0.15s ease,
        color 0.15s ease;

}


.pathway-course-button:hover {

    background: #faf5fa;

}


.pathway-course-button.added {

    background: #940594;

    color: #ffffff;

}


.primary-course-button {

    display: inline-block;

    margin-top: 0.8rem;

    padding:
        0.7rem
        1rem;

    border-radius: 7px;

    background: #940594;

    color: #ffffff;

    font-size: 0.85rem;

    font-weight: 700;

    text-decoration: none;

}


.primary-course-button:hover {

    background: #740574;

}


/* ==============================================================
   SCROLL LOCK (while the pathway panel is open)
============================================================== */

body.pathway-scroll-lock {

    overflow: hidden;

}


/* ==============================================================
   PATHWAY BACKDROP
   Sits above the site's own header/nav (whatever z-index the
   theme uses) so the panel never mixes visually with it, and
   dims + blocks the rest of the page while the panel is open.
============================================================== */

.pathway-backdrop {

    position: fixed;

    inset: 0;

    z-index: 999998;

    background:
        rgba(15, 23, 42, 0.55);

    opacity: 0;
    visibility: hidden;

    transition:
        opacity 0.2s ease,
        visibility 0.2s ease;

}


.pathway-backdrop.open {

    opacity: 1;
    visibility: visible;

}


/* ==============================================================
   LEARNING PATHWAY PANEL
============================================================== */
.pathway-panel {
    position: fixed;
    z-index: 999999;

    /*
     * inset + margin:auto centers the panel inside a box
     * that is always 1rem smaller than the viewport on every
     * side, so the panel can never be pushed off-screen or
     * clipped, regardless of window height or page scroll.
     */
    inset: 1rem;
    margin: auto;

    width: min(1000px, 90vw);
    height: min(750px, calc(100vh - 2rem));
    max-height: calc(100vh - 2rem);

    box-sizing: border-box;
    padding: 2rem;

    overflow-y: auto;

    background: #ffffff;

    border: 1px solid #e2e8f0;
    border-radius: 20px;

    box-shadow:
        0 20px 60px rgba(15, 23, 42, 0.25);

    transform:
        scale(0.95);

    opacity: 0;
    visibility: hidden;

    transition:
        opacity 0.2s ease,
        transform 0.2s ease,
        visibility 0.2s ease;
}

.pathway-panel.open {
    transform:
        scale(1);

    opacity: 1;
    visibility: visible;
}



.close-pathway-panel {

       position: absolute;
    z-index: 100001;

    top: 1rem;

    right: 1rem;

    width: 34px;

    height: 34px;

    border: 0;

    border-radius: 50%;

    background: #f1f5f9;

    color: #475569;

    font-size: 1.5rem;

    line-height: 1;

    cursor: pointer;

}


.close-pathway-panel:hover {

    background: #e2e8f0;

}


.pathway-panel-header {

    padding-right: 2rem;

}


.pathway-panel-header h2 {

    margin:
        0 0 0.7rem;

    color: #002a41;

    line-height: 1.25;

}


.pathway-panel-header p {

    margin: 0;

    color: #64748b;

    font-size: 0.85rem;

    line-height: 1.5;

}


/* ==============================================================
   PATHWAY EMPTY STATE
============================================================== */

.pathway-empty {

    margin-top: 2rem;

    padding: 2rem 1.2rem;

    border:
        1px dashed
        #cbd5e1;

    border-radius: 12px;

    background: #f8fafc;

    text-align: center;

}


.pathway-empty-icon {

    margin-bottom: 0.7rem;

    font-size: 2rem;

}


.pathway-empty h3 {

    margin:
        0 0 0.5rem;

    color: #334155;

    font-size: 1rem;

}


.pathway-empty p {

    margin:
        0 0 1.2rem;

    color: #64748b;

    font-size: 0.8rem;

    line-height: 1.5;

}


.primary-pathway-button {

    padding:
        0.65rem
        0.9rem;

    border: 0;

    border-radius: 7px;

    background: #940594;

    color: #ffffff;

    font-size: 0.8rem;

    font-weight: 700;

    cursor: pointer;

}


.primary-pathway-button:hover {

    background: #740574;

}


/* ==============================================================
   PATHWAY SUMMARY
============================================================== */

.pathway-summary {

    display: flex;

    flex-direction: column;

    gap: 0.2rem;

    margin:
        1.5rem 0
        0.8rem;

    padding:
        0.8rem
        0.9rem;

    border-radius: 8px;

    background: #faf5fa;

}


.pathway-summary strong {

    color: #940594;

    font-size: 0.9rem;

}


.pathway-summary span {

    color: #64748b;

    font-size: 0.7rem;

}


/* ==============================================================
   PATHWAY VIEW TOGGLE
============================================================== */

.pathway-view-toggle {

    display: flex;

    gap: 0.4rem;

    margin-bottom: 0.8rem;

}


.pathway-view-btn {

    flex: 1;

    padding: 0.55rem 0.7rem;

    border: 1px solid #e2e8f0;

    border-radius: 7px;

    background: #ffffff;

    color: #64748b;

    font-size: 0.78rem;

    font-weight: 700;

    cursor: pointer;

    transition:
        border-color 0.15s ease,
        background 0.15s ease,
        color 0.15s ease;

}


.pathway-view-btn:hover {

    border-color: #c084c0;

    color: #940594;

}


.pathway-view-btn.active {

    border-color: #940594;

    background: #940594;

    color: #ffffff;

}


.pathway-map-hint {

    margin: 0 0 0.8rem;
    padding: 0.6rem 0.8rem;
    border-radius: 7px;
    background: #faf5fa;
    color: #740574;
    font-size: 0.6rem !important;
    line-height: 1.4;

}


.pathway-map-hint p {

    font-size: 0.6rem !important;
 
}



/* ==============================================================
   PATHWAY LIST
============================================================== */

.pathway-list {

    display: flex;

    flex-direction: column;

    gap: 0.65rem;

}


.pathway-item {

    display: flex;

    gap: 0.7rem;

    padding: 0.75rem;

    border:
        1px solid
        #e2e8f0;

    border-radius: 9px;

    background: #ffffff;

    cursor: grab;

    transition:
        border-color 0.15s ease,
        box-shadow 0.15s ease,
        opacity 0.15s ease;

}


.pathway-item:hover {

    border-color: #c084c0;

}


.pathway-item.dragging {

    opacity: 0.45;

}


.pathway-item.drag-over {

    border-color: #940594;

    box-shadow:
        0 0 0 3px
        rgba(
            148,
            5,
            148,
            0.1
        );

}


.pathway-number {

    flex:
        0 0
        28px;

    width: 28px;

    height: 28px;

    display: flex;

    align-items: center;

    justify-content: center;

    border-radius: 50%;

    background: #f3e8f3;

    color: #940594;

    font-size: 0.72rem;

    font-weight: 700;

}


.pathway-item-content {

    flex: 1;

    min-width: 0;

}


.pathway-item-title {

    color: #334155;

    font-size: 0.82rem;

    font-weight: 700;

    line-height: 1.35;

}


.pathway-item-organisation {

    margin-top: 0.25rem;

    color: #940594;

    font-size: 0.62rem;

    font-weight: 700;

    text-transform: uppercase;

}


.pathway-item-meta {

    margin-top: 0.3rem;

    color: #64748b;

    font-size: 0.65rem;

}


.pathway-item-actions {

    display: flex;

    align-items: center;

    gap: 0.3rem;

    margin-top: 0.6rem;

    flex-wrap: wrap;

}


.pathway-move-button,
.pathway-view-button,
.pathway-remove-button {

    padding:
        0.3rem
        0.5rem;

    border:
        1px solid
        #e2e8f0;

    border-radius: 5px;

    background: #ffffff;

    color: #475569;

    font-size: 0.65rem;

    cursor: pointer;

}


.pathway-move-button:hover,
.pathway-view-button:hover {

    border-color: #940594;

    color: #940594;

}


.pathway-move-button:disabled {

    opacity: 0.3;

    cursor: default;

}


.pathway-remove-button {

    margin-left: auto;

    color: #b91c1c;

}


.pathway-remove-button:hover {

    border-color: #fecaca;

    background: #fef2f2;

}


.pathway-actions {

    margin-top: 1.2rem;

    padding-top: 1rem;

    border-top:
        1px solid
        #e2e8f0;

}


.clear-pathway-button {

    width: 100%;

    padding: 0.65rem;

    border:
        1px solid
        #cbd5e1;

    border-radius: 7px;

    background: #ffffff;

    color: #64748b;

    font-size: 0.75rem;

    cursor: pointer;

}


.clear-pathway-button:hover {

    border-color: #ef4444;

    color: #b91c1c;

    background: #fef2f2;

}

.download-pathway-button {

    width: 100%;

    margin-bottom: 0.6rem;

    padding: 0.7rem 0.8rem;

    border: 1px solid #940594;

    border-radius: 7px;

    background: #940594;

    color: #ffffff;

    font-size: 0.75rem;

    font-weight: 700;

    cursor: pointer;

    transition:
        background 0.15s ease,
        transform 0.15s ease;

}


.download-pathway-button:hover {

    background: #740574;

}


.download-pathway-button:active {

    transform: translateY(1px);

}


/* ==============================================================
   MOBILE
============================================================== */

@media (max-width: 1200px) {

    .training-board {

        grid-template-columns:
            repeat(
                2,
                minmax(
                    390px,
                    1fr
                )
            );

    }

}


@media (max-width: 850px) {

    .training-board {

        grid-template-columns:
            minmax(
                360px,
                1fr
            );

        min-width: 360px;

        padding: 30px;

    }


    .training-group-card {

        min-width: 360px;

    }


    .topic-grid.two-topics,
    .topic-grid.many-topics {

        grid-template-columns:
            minmax(
                0,
                1fr
            );

    }

}


@media (max-width: 700px) {

    .map-toolbar {

        align-items: stretch;

    }


    .map-controls {

        width: 100%;

        justify-content: flex-end;

    }


    .training-board-wrapper {

        height: 70vh;

        min-height: 550px;

    }


    .training-board {

        padding: 20px;

    }


    .training-group-card {

        min-width: 320px;

    }


    .map-info-panel,
    .pathway-panel {

        width: 100%;

        padding: 1.5rem;

    }


    .pathway-button {

        flex: 1;

        justify-content: center;

    }

}

/* ============================================================
   INTERACTIVE LEARNING PATHWAY
   ============================================================ */

.pathway-interactive-canvas {
    position: relative !important;

    width: 100%;

    height: 560px;

    overflow: hidden;

    margin-top: 1rem;

    border:
        1px solid #e2e8f0;

    border-radius: 12px;

    background-color: #f8fafc;

    background-image:
        radial-gradient(
            #cbd5e1 0.8px,
            transparent 0.8px
        );

    background-size: 22px 22px;

    display: block !important;

    cursor: default;
}




.pathway-nodes {
    position: absolute;
    inset: 0;
    z-index: 2;
    pointer-events: none;
}


/* ============================================================
   NODE
   ============================================================ */

.pathway-node {
    position: absolute;

    width: 230px;

    min-height: 125px;

    box-sizing: border-box;

    padding: 16px;

    border:
        1px solid #d8dee6;

    border-radius: 12px;

    background: #ffffff;

    box-shadow:
        0 4px 12px
        rgba(15, 23, 42, .08);

        cursor: grab;
    user-select: none;
    touch-action: none;
    pointer-events: auto;

    transition:
        box-shadow .15s ease,
        border-color .15s ease;
}


.pathway-node:hover {
    border-color: #940594;

    box-shadow:
        0 7px 18px
        rgba(15, 23, 42, .13);
}


.pathway-node.dragging {
    cursor: grabbing;

    z-index: 100;

    box-shadow:
        0 12px 25px
        rgba(15, 23, 42, .18);
}


/* ============================================================
   NODE CONTENT
   ============================================================ */

.pathway-node-title {
    margin-right: 25px;

    color: #002a41;

    font-size: .85rem;

    font-weight: 700;

    line-height: 1.35;
}


.pathway-node-title a {
    color: inherit;

    text-decoration: none;
}


.pathway-node-title a:hover {
    color: #940594;

    text-decoration: underline;
}


.pathway-node-org {
    margin-top: 7px;

    color: #940594;

    font-size: .65rem;

    font-weight: 700;

    text-transform: uppercase;
}


.pathway-node-meta {
    margin-top: 8px;

    color: #64748b;

    font-size: .68rem;

    line-height: 1.5;
}


/* ============================================================
   REMOVE BUTTON
   ============================================================ */

.pathway-node-remove {
    position: absolute;

    top: 7px;
    right: 7px;

    width: 24px;
    height: 24px;

    padding: 0;

    border: 0;

    border-radius: 50%;

    background: #f1f5f9;

    color: #64748b;

    font-size: 16px;

    cursor: pointer;
}


.pathway-node-remove:hover {
    background: #fee2e2;

    color: #b91c1c;
}


/* ============================================================
   CONNECTION HANDLES
   ============================================================ */

.pathway-handle {
    position: absolute;

    width: 11px;
    height: 11px;

    box-sizing: border-box;

    border:
        2px solid #940594;

    border-radius: 50%;

    background: #ffffff;

    cursor: crosshair;

    z-index: 10;
}


.pathway-handle:hover {
    background: #940594;

    transform: scale(1.3);
}


.pathway-handle.top {
    top: -6px;
    left: 50%;

    transform:
        translateX(-50%);
}


.pathway-handle.right {
    top: 50%;
    right: -6px;

    transform:
        translateY(-50%);
}


.pathway-handle.bottom {
    bottom: -6px;
    left: 50%;

    transform:
        translateX(-50%);
}


.pathway-handle.left {
    top: 50%;
    left: -6px;

    transform:
        translateY(-50%);
}


/* ============================================================
   CONNECTIONS
   ============================================================ */





.pathway-line-hit:hover + .pathway-line {
    stroke-width: 4;

    opacity: 1;
}


.pathway-line-hit {
    fill: none;
    stroke: transparent;
    stroke-width: 24px;
    pointer-events: stroke;
    cursor: pointer;
}

.pathway-temp-line {
    fill: none;

    stroke: #940594;

    stroke-width: 2;

    stroke-dasharray: 6 5;

    opacity: .55;

    pointer-events: none;
}

.pathway-line:hover {
    stroke-width: 4;

    opacity: 1;
}


.pathway-temp-line {
    fill: none;

    stroke: #940594;

    stroke-width: 2;

    stroke-dasharray: 6 5;

    opacity: .55;

    pointer-events: none;
}


/* ============================================================
   PATHWAY CANVAS
============================================================ */

.pathway-interactive-canvas {

    position: relative !important;

    width: 100%;

    height: 560px;

    overflow: hidden;

    margin-top: 1rem;

    border:
        1px solid #e2e8f0;

    border-radius: 12px;

    background-color: #f8fafc;

    background-image:
        radial-gradient(
            #cbd5e1 0.8px,
            transparent 0.8px
        );

    background-size: 22px 22px;

    display: block !important;

}


/* ============================================================
   VIEWPORT
============================================================ */

.pathway-viewport {

    position: absolute;

    inset: 0;

    overflow: hidden;

    cursor: grab;

    touch-action: none;

    user-select: none;

    -webkit-user-select: none;

}


.pathway-viewport.is-panning {

    cursor: grabbing;

}


/* ============================================================
   WORLD
============================================================ */

.pathway-world {

    position: absolute;

    left: 0;

    top: 0;

    width: 3000px;

    height: 2000px;

    transform-origin: 0 0;

    will-change: transform;

}


/* ============================================================
   SVG
============================================================ */




/* ============================================================
   NODES
============================================================ */

.pathway-nodes {

    position: absolute;

    left: 0;

    top: 0;

    width: 3000px;

    height: 2000px;

    z-index: 2;

}


/* ============================================================
   PATHWAY CANVAS CONTROLS
============================================================ */

.pathway-canvas-controls {

    display: flex;

    align-items: center;

    gap: 0.3rem;

    margin-bottom: 0.7rem;

}


.pathway-canvas-controls button {

    width: 32px;

    height: 32px;

    padding: 0;

    border:
        1px solid #cbd5e1;

    border-radius: 6px;

    background: #ffffff;

    color: #475569;

    font-size: 1rem;

    cursor: pointer;

}


.pathway-canvas-controls button:hover {

    border-color: #940594;

    color: #940594;

    background: #faf5fa;

}


#pathway-zoom-indicator {

    min-width: 48px;

    text-align: center;

    color: #64748b;

    font-size: 0.7rem;

    font-weight: 600;

}

.pathway-world {
    position: relative;
}

.pathway-svg {
    position: absolute;
    inset: 0;
    width: 100%;
    height: 100%;
    overflow: visible;

    /*
     * SVG itself can receive pointer events.
     * Individual visible lines disable them below.
     */
    pointer-events: auto;

    z-index: 1;
}

.pathway-line {
    fill: none;
    stroke: #940594;
    stroke-width: 2.5;
    opacity: .7;
    pointer-events: none;
}

.pathway-line-hit {
    fill: none;
    stroke: transparent;
    stroke-width: 24px;

    pointer-events: stroke;

    cursor: pointer;
}


.pathway-nodes {
    position: absolute;
    inset: 0;
}



</style>