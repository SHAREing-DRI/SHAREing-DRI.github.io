---
layout: splash
permalink: /training/external-training-map
classes: wide
---

<section class="page-intro training-map-intro">

    <h1>Training Map</h1>

    <p>
        Explore the training available through SHAREing by topic.
        Drag the nodes to move them around, zoom in and out, and click
        on a topic to discover related courses.
    </p>

</section>


<!-- ============================================================
     MAP CONTROLS
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
            id="zoom-in"
            class="map-control-button"
            title="Zoom in"
        >
            +
        </button>

        <button
            type="button"
            id="zoom-out"
            class="map-control-button"
            title="Zoom out"
        >
            −
        </button>

        <button
            type="button"
            id="reset-map"
            class="map-control-button"
        >
            ↺ Reset map
        </button>

    </div>

</div>


<!-- ============================================================
     MAP
============================================================ -->

<div class="training-map-wrapper">

    <svg
        id="training-map"
        role="img"
        aria-label="Interactive SHAREing training map"
    ></svg>

    <div
        id="map-loading"
        class="map-message"
    >
        Loading training map...
    </div>

    <div
        id="map-empty"
        class="map-message"
        style="display: none;"
    >
        No matching topics or courses found.
    </div>

</div>


<!-- ============================================================
     COURSE / TOPIC INFORMATION PANEL
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
     LEGEND
============================================================ -->

<div class="map-legend">

    <div class="legend-item">
        <span class="legend-node group-node"></span>
        <span>Group</span>
    </div>

    <div class="legend-item">
        <span class="legend-node topic-node"></span>
        <span>Topic</span>
    </div>

    <div class="legend-item">
        <span class="legend-node course-node"></span>
        <span>Course</span>
    </div>

</div>


<!-- ============================================================
     D3.JS
============================================================ -->

<script src="https://d3js.org/d3.v7.min.js"></script>


<script>

document.addEventListener("DOMContentLoaded", function () {

    // ============================================================
    // DATA
    // ============================================================

    const courses = {{ site.data["external-training"] | jsonify }};


    // ============================================================
    // TOPIC GROUPS
    //
    // Keep this structure aligned with the topic groups used
    // on the main training catalogue page.
    // ============================================================

    const topicGroups = {

        "Languages": {
            icon: "💬",
            topics: [
                "Fortran",
                "C++",
                "Julia",
                "Python"
            ]
        },

        "Parallelism": {
            icon: "🔀",
            topics: [
                "MPI",
                "OpenMP",
                "Parallel Programming",
                "Parallel Computing"
            ]
        },

        "GPU": {
            icon: "🎮",
            topics: [
                "GPU",
                "CUDA",
                "HIP",
                "OpenACC"
            ]
        },

        "Performance": {
            icon: "📈",
            topics: [
                "Performance",
                "Performance Analysis",
                "Benchmarking",
                "Optimisation",
                "Profiling"
            ]
        },

        "Other": {
            icon: "📦",
            topics: [
                "Containers",
                "I/O",
                "Tools",
                "Software Engineering",
                "Research Software Engineering"
            ]
        },

        "Community": {
            icon: "🌍",
            topics: [
                "Seminar",
                "Community",
                "Career Development",
                "Professional Skills"
            ]
        }

    };


    // ============================================================
    // CONFIGURATION
    // ============================================================

    const config = {

        width: 1600,

        height: 900,

        // How far courses sit from their topic
        courseDistance: 115,

        // How far topics sit from their group
        topicDistance: 190,

        // Minimum zoom
        minZoom: 0.35,

        // Maximum zoom
        maxZoom: 3.5

    };


    // ============================================================
    // ELEMENTS
    // ============================================================

    const svg = d3.select("#training-map");

    const mapWrapper =
        document.querySelector(".training-map-wrapper");

    const loadingMessage =
        document.getElementById("map-loading");

    const emptyMessage =
        document.getElementById("map-empty");

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


    // ============================================================
    // RESPONSIVE SVG SIZE
    // ============================================================

    function getMapSize() {

        const width =
            mapWrapper.clientWidth || config.width;

        const height =
            Math.max(
                650,
                Math.min(
                    900,
                    window.innerHeight * 0.75
                )
            );

        return {
            width,
            height
        };

    }


    let mapSize = getMapSize();

    svg
        .attr("width", mapSize.width)
        .attr("height", mapSize.height)
        .attr("viewBox", `0 0 ${mapSize.width} ${mapSize.height}`);


    // ============================================================
    // PREPARE TOPIC DATA
    // ============================================================

    const knownTopics = new Set();

    Object.values(topicGroups).forEach(group => {

        group.topics.forEach(topic => {
            knownTopics.add(topic);
        });

    });


    // ============================================================
    // FIND TOPICS IN CSV
    // ============================================================

    const coursesByTopic = {};


    courses.forEach(course => {

        if (!course.tags) {
            return;
        }

        const topics = course.tags
            .split(",")
            .map(tag => tag.trim())
            .filter(Boolean);


        topics.forEach(topic => {

            if (!coursesByTopic[topic]) {
                coursesByTopic[topic] = [];
            }

            coursesByTopic[topic].push(course);

        });

    });


    // ============================================================
    // ADD UNGROUPED TOPICS TO "OTHER"
    // ============================================================

    Object.keys(coursesByTopic).forEach(topic => {

        if (!knownTopics.has(topic)) {

            if (!topicGroups["Other"].topics.includes(topic)) {

                topicGroups["Other"].topics.push(topic);

            }

        }

    });


    // ============================================================
    // BUILD GRAPH NODES
    // ============================================================

    const nodes = [];

    const links = [];

    const nodeMap = new Map();


    // ------------------------------------------------------------
    // ROOT NODE
    // ------------------------------------------------------------




    // ============================================================
    // GROUP NODES
    // ============================================================

    Object.entries(topicGroups).forEach(
        ([groupName, groupData]) => {

            const groupId =
                `group-${slugify(groupName)}`;


            const availableTopics =
                groupData.topics.filter(
                    topic => coursesByTopic[topic]
                );


            // Don't show empty groups
            if (!availableTopics.length) {
                return;
            }


            const groupNode = {

                id: groupId,

                type: "group",

                label: groupName,

                icon: groupData.icon,

                size: 24,

                topicCount: availableTopics.length

            };


            nodes.push(groupNode);

            nodeMap.set(groupId, groupNode);





            // ====================================================
            // TOPICS
            // ====================================================

            availableTopics.forEach(topic => {

                const topicId =
                    `topic-${slugify(topic)}`;


                const topicNode = {

                    id: topicId,

                    type: "topic",

                    label: topic,

                    size: Math.min(
                        12 +
                        coursesByTopic[topic].length * 1.5,
                        22
                    ),

                    courseCount:
                        coursesByTopic[topic].length,

                    group:
                        groupName

                };


                nodes.push(topicNode);

                nodeMap.set(topicId, topicNode);


                links.push({

                    source: groupId,

                    target: topicId,

                    type: "group-topic"

                });


                // =================================================
                // COURSES
                //
                // Courses are included in the graph, but kept
                // visually smaller.
                // =================================================

                coursesByTopic[topic].forEach(
                    (course, index) => {

                        /*
                         * A course may appear under multiple topics.
                         *
                         * We create one course node per course and
                         * connect it to each relevant topic.
                         */

                        const courseId =
                            `course-${courseIndex(course)}`;


                        let courseNode =
                            nodeMap.get(courseId);


                        if (!courseNode) {

                            courseNode = {

                                id: courseId,

                                type: "course",

                                label:
                                    course.title ||
                                    "Untitled course",

                                organisation:
                                    course.organisation ||
                                    "",

                                format:
                                    course.format ||
                                    "",

                                dates:
                                    course.dates ||
                                    "",

                                location:
                                    course.location ||
                                    "",

                                url:
                                    course.url ||
                                    "#",

                                size: 7,

                                topics: []

                            };


                            nodes.push(courseNode);

                            nodeMap.set(
                                courseId,
                                courseNode
                            );

                        }


                        if (
                            !courseNode.topics.includes(topic)
                        ) {

                            courseNode.topics.push(topic);

                        }


                        /*
                         * Prevent duplicate links.
                         */

                        const linkExists =
                            links.some(link =>

                                link.source === topicId &&
                                link.target === courseId

                            );


                        if (!linkExists) {

                            links.push({

                                source: topicId,

                                target: courseId,

                                type: "topic-course"

                            });

                        }

                    }

                );

            });

        }
    );


    // ============================================================
    // HANDLE EMPTY DATA
    // ============================================================

    if (!nodes.length) {

        loadingMessage.style.display = "none";

        emptyMessage.style.display = "block";

        return;

    }


    loadingMessage.style.display = "none";


    // ============================================================
    // ZOOM
    // ============================================================

    const mapGroup =
        svg.append("g")
            .attr("class", "map-group");


    const zoom =
        d3.zoom()
            .scaleExtent([
                config.minZoom,
                config.maxZoom
            ])
            .on("zoom", event => {

                mapGroup.attr(
                    "transform",
                    event.transform
                );

            });


    svg.call(zoom);


    // ============================================================
    // LINKS
    // ============================================================

    const linkGroup =
        mapGroup
            .append("g")
            .attr("class", "links");


    const linkElements =
        linkGroup
            .selectAll("line")
            .data(links)
            .enter()
            .append("line")
            .attr("class", d => {

                if (d.type === "root-group") {
                    return "map-link root-group-link";
                }

                if (d.type === "group-topic") {
                    return "map-link group-topic-link";
                }

                return "map-link topic-course-link";

            });


    // ============================================================
    // NODES
    // ============================================================

    const nodeGroup =
        mapGroup
            .append("g")
            .attr("class", "nodes");


    const nodeElements =
        nodeGroup
            .selectAll("g")
            .data(nodes)
            .enter()
            .append("g")
            .attr("class", d =>
                `map-node ${d.type}-node`
            )
            .style("cursor", "pointer")
            .call(
                d3.drag()
                    .on("start", dragStarted)
                    .on("drag", dragged)
                    .on("end", dragEnded)
            );


    // ============================================================
    // NODE CIRCLES
    // ============================================================

    nodeElements
        .append("circle")
        .attr("r", d => d.size)
        .attr("class", "node-circle");


    // ============================================================
    // GROUP ICONS
    // ============================================================

    nodeElements
        .filter(d =>
            d.type === "group"
        )
        .append("text")
        .attr("class", "group-icon")
        .attr("text-anchor", "middle")
        .attr("dy", "0.35em")
        .text(d => d.icon);


    // ============================================================
    // NODE LABELS
    // ============================================================

    nodeElements
        .append("text")
        .attr("class", "node-label")
        .attr("dy", d => {

            if (d.type === "root") {
                return d.size + 22;
            }

            return d.size + 17;

        })
        .attr("text-anchor", "middle")
        .text(d => d.label);


    // ============================================================
    // TOPIC COURSE COUNTS
    // ============================================================

    nodeElements
        .filter(d =>
            d.type === "topic"
        )
        .append("text")
        .attr("class", "node-count")
        .attr("text-anchor", "middle")
        .attr("dy", "0.35em")
        .text(d => d.courseCount);


    // ============================================================
    // FORCE SIMULATION
    // ============================================================

    const simulation =
        d3.forceSimulation(nodes)

            .force(
                "link",
                d3.forceLink(links)
                    .id(d => d.id)
                    .distance(d => {

                        if (
                            d.type === "root-group"
                        ) {
                            return 180;
                        }

                        if (
                            d.type === "group-topic"
                        ) {
                            return config.topicDistance;
                        }

                        return config.courseDistance;

                    })
                    .strength(d => {

                        if (
                            d.type === "root-group"
                        ) {
                            return 1;
                        }

                        if (
                            d.type === "group-topic"
                        ) {
                            return 0.8;
                        }

                        return 0.35;

                    })
            )

            .force(
                "charge",
                d3.forceManyBody()
                    .strength(d => {

                        if (d.type === "root") {
                            return -1000;
                        }

                        if (d.type === "group") {
                            return -650;
                        }

                        if (d.type === "topic") {
                            return -300;
                        }

                        return -80;

                    })
            )

            .force(
                "collision",
                d3.forceCollide()
                    .radius(d => {

                        if (d.type === "course") {
                            return 22;
                        }

                        return d.size + 18;

                    })
                    .strength(1)
            )

            .force(
                "x",
                d3.forceX(
                    mapSize.width / 2
                ).strength(0.04)
            )

            .force(
                "y",
                d3.forceY(
                    mapSize.height / 2
                ).strength(0.04)
            )

            .on("tick", ticked);


    // ============================================================
    // INITIAL POSITIONS
    // ============================================================

    nodes.forEach(node => {

        node.x =
            mapSize.width / 2 +
            (Math.random() - 0.5) * 500;

        node.y =
            mapSize.height / 2 +
            (Math.random() - 0.5) * 400;

    });


    simulation.alpha(1).restart();


    // ============================================================
    // TICK
    // ============================================================

    function ticked() {

        linkElements

            .attr(
                "x1",
                d => d.source.x
            )

            .attr(
                "y1",
                d => d.source.y
            )

            .attr(
                "x2",
                d => d.target.x
            )

            .attr(
                "y2",
                d => d.target.y
            );


        nodeElements.attr(
            "transform",
            d => `translate(${d.x},${d.y})`
        );

    }


    // ============================================================
    // NODE CLICK
    // ============================================================

    nodeElements.on(
        "click",
        function (event, node) {

            event.stopPropagation();

            showNodeInfo(node);

            highlightNode(node);

        }
    );


    // ============================================================
    // BACKGROUND CLICK
    // ============================================================

    svg.on(
        "click",
        function () {

            clearHighlight();

            closeInfoPanel();

        }
    );


    // ============================================================
    // SHOW NODE INFORMATION
    // ============================================================

    function showNodeInfo(node) {

        let html = "";


        // --------------------------------------------------------
        // ROOT
        // --------------------------------------------------------

        if (node.type === "root") {

            html = `

                <div class="info-type">
                    Training map
                </div>

                <h2>
                    SHAREing Training
                </h2>

                <p>
                    Explore training opportunities across
                    different HPC, programming, performance,
                    GPU and research software topics.
                </p>

                <div class="info-stat">
                    <strong>${courses.length}</strong>
                    <span>courses</span>
                </div>

            `;

        }


        // --------------------------------------------------------
        // GROUP
        // --------------------------------------------------------

        else if (node.type === "group") {

            const topics =
                topicGroups[node.label].topics
                    .filter(topic =>
                        coursesByTopic[topic]
                    );


            html = `

                <div class="info-type">
                    Training group
                </div>

                <h2>
                    ${node.icon} ${node.label}
                </h2>

                <div class="info-stat">
                    <strong>${topics.length}</strong>
                    <span>topics</span>
                </div>

                <div class="info-section">

                    <h3>Topics</h3>

                    <ul class="info-topic-list">

                        ${topics.map(topic => `

                            <li>
                                ${topic}
                                <span>
                                    ${coursesByTopic[topic].length}
                                </span>
                            </li>

                        `).join("")}

                    </ul>

                </div>

            `;

        }


        // --------------------------------------------------------
        // TOPIC
        // --------------------------------------------------------

        else if (node.type === "topic") {

            const topicCourses =
                coursesByTopic[node.label] || [];


            html = `

                <div class="info-type">
                    Training topic
                </div>

                <h2>
                    ${node.label}
                </h2>

                <div class="info-stat">
                    <strong>${topicCourses.length}</strong>
                    <span>
                        ${topicCourses.length === 1
                            ? "course"
                            : "courses"}
                    </span>
                </div>

                <div class="info-section">

                    <h3>Available training</h3>

                    <div class="course-list">

                        ${topicCourses.map(course => `

                            <article class="map-course-card">

                                <div class="map-course-organisation">
                                    ${course.organisation || ""}
                                </div>

                                <h4>
                                    ${course.title || ""}
                                </h4>

                                ${
                                    course.format
                                        ? `
                                            <div class="map-course-meta">
                                                ${formatIcon(course.format)}
                                                ${formatLabel(course.format)}
                                            </div>
                                          `
                                        : ""
                                }

                                ${
                                    course.dates
                                        ? `
                                            <div class="map-course-meta">
                                                📅 ${course.dates}
                                            </div>
                                          `
                                        : ""
                                }

                                ${
                                    course.url
                                        ? `
                                            <a
                                                href="${course.url}"
                                                target="_blank"
                                                rel="noopener"
                                                class="map-course-link"
                                            >
                                                View course →
                                            </a>
                                          `
                                        : ""
                                }

                            </article>

                        `).join("")}

                    </div>

                </div>

            `;

        }


        // --------------------------------------------------------
        // COURSE
        // --------------------------------------------------------

        else if (node.type === "course") {

            html = `

                <div class="info-type">
                    Training course
                </div>

                <h2>
                    ${node.label}
                </h2>

                ${
                    node.organisation
                        ? `
                            <div class="map-course-organisation">
                                ${node.organisation}
                            </div>
                          `
                        : ""
                }

                ${
                    node.format
                        ? `
                            <div class="info-meta">
                                ${formatIcon(node.format)}
                                ${formatLabel(node.format)}
                            </div>
                          `
                        : ""
                }

                ${
                    node.dates
                        ? `
                            <div class="info-meta">
                                📅 ${node.dates}
                            </div>
                          `
                        : ""
                }

                ${
                    node.location
                        ? `
                            <div class="info-meta">
                                📍 ${node.location}
                            </div>
                          `
                        : ""
                }

                ${
                    node.topics.length
                        ? `
                            <div class="info-section">

                                <h3>Topics</h3>

                                <div class="course-topic-tags">

                                    ${node.topics.map(topic => `
                                        <span>
                                            ${topic}
                                        </span>
                                    `).join("")}

                                </div>

                            </div>
                          `
                        : ""
                }

                ${
                    node.url
                        ? `
                            <a
                                href="${node.url}"
                                target="_blank"
                                rel="noopener"
                                class="primary-course-button"
                            >
                                View course →
                            </a>
                          `
                        : ""
                }

            `;

        }


        infoContent.innerHTML = html;

        infoPanel.classList.add("open");

        infoPanel.setAttribute(
            "aria-hidden",
            "false"
        );

    }


    // ============================================================
    // CLOSE PANEL
    // ============================================================

    function closeInfoPanel() {

        infoPanel.classList.remove("open");

        infoPanel.setAttribute(
            "aria-hidden",
            "true"
        );

    }


    closeInfoButton.addEventListener(
        "click",
        function (event) {

            event.stopPropagation();

            closeInfoPanel();

            clearHighlight();

        }
    );


    // ============================================================
    // HIGHLIGHT NODE + CONNECTIONS
    // ============================================================

    function highlightNode(node) {

        const connectedIds =
            new Set([node.id]);


        links.forEach(link => {

            const sourceId =
                typeof link.source === "object"
                    ? link.source.id
                    : link.source;

            const targetId =
                typeof link.target === "object"
                    ? link.target.id
                    : link.target;


            if (sourceId === node.id) {
                connectedIds.add(targetId);
            }

            if (targetId === node.id) {
                connectedIds.add(sourceId);
            }

        });


        nodeElements.classed(
            "dimmed",
            d => !connectedIds.has(d.id)
        );


        linkElements.classed(
            "dimmed",
            link => {

                const sourceId =
                    typeof link.source === "object"
                        ? link.source.id
                        : link.source;

                const targetId =
                    typeof link.target === "object"
                        ? link.target.id
                        : link.target;


                return !(
                    connectedIds.has(sourceId) &&
                    connectedIds.has(targetId)
                );

            }
        );

    }


    // ============================================================
    // CLEAR HIGHLIGHT
    // ============================================================

    function clearHighlight() {

        nodeElements.classed(
            "dimmed",
            false
        );

        linkElements.classed(
            "dimmed",
            false
        );

    }


    // ============================================================
    // SEARCH
    // ============================================================

    searchInput.addEventListener(
        "input",
        function () {

            const query =
                this.value
                    .trim()
                    .toLowerCase();


            if (!query) {

                clearHighlight();

                emptyMessage.style.display = "none";

                return;

            }


            const matchingNodes =
                nodes.filter(node => {

                    const label =
                        (node.label || "")
                            .toLowerCase();

                    const organisation =
                        (node.organisation || "")
                            .toLowerCase();


                    return (
                        label.includes(query) ||
                        organisation.includes(query)
                    );

                });


            if (!matchingNodes.length) {

                emptyMessage.style.display =
                    "block";

                nodeElements.classed(
                    "dimmed",
                    true
                );

                linkElements.classed(
                    "dimmed",
                    true
                );

                return;

            }


            emptyMessage.style.display =
                "none";


            const matchingIds =
                new Set(
                    matchingNodes.map(
                        node => node.id
                    )
                );


            nodeElements.classed(
                "dimmed",
                node =>
                    !matchingIds.has(node.id)
            );


            linkElements.classed(
                "dimmed",
                true
            );


            // Highlight links connected to matches
            linkElements.classed(
                "search-match",
                link => {

                    const sourceId =
                        typeof link.source === "object"
                            ? link.source.id
                            : link.source;

                    const targetId =
                        typeof link.target === "object"
                            ? link.target.id
                            : link.target;


                    return (
                        matchingIds.has(sourceId) ||
                        matchingIds.has(targetId)
                    );

                }
            );

        }
    );


    // ============================================================
    // ZOOM CONTROLS
    // ============================================================

    zoomInButton.addEventListener(
        "click",
        function () {

            svg.transition()
                .duration(300)
                .call(
                    zoom.scaleBy,
                    1.35
                );

        }
    );


    zoomOutButton.addEventListener(
        "click",
        function () {

            svg.transition()
                .duration(300)
                .call(
                    zoom.scaleBy,
                    0.75
                );

        }
    );


    // ============================================================
    // RESET
    // ============================================================

    resetButton.addEventListener(
        "click",
        resetMap
    );


    function resetMap() {

        searchInput.value = "";

        emptyMessage.style.display =
            "none";

        clearHighlight();

        simulation.alpha(1).restart();


        svg.transition()
            .duration(500)
            .call(
                zoom.transform,
                d3.zoomIdentity
            );


        closeInfoPanel();

    }


    // ============================================================
    // DRAGGING
    // ============================================================

    function dragStarted(
        event,
        d
    ) {

        if (!event.active) {

            simulation.alphaTarget(
                0.3
            ).restart();

        }

        d.fx = d.x;
        d.fy = d.y;

    }


    function dragged(
        event,
        d
    ) {

        d.fx = event.x;
        d.fy = event.y;

    }


    function dragEnded(
        event,
        d
    ) {

        if (!event.active) {

            simulation.alphaTarget(0);

        }

        d.fx = null;
        d.fy = null;

    }


    // ============================================================
    // HELPERS
    // ============================================================

    function slugify(value) {

        return String(value)
            .toLowerCase()
            .trim()
            .replace(/\s+/g, "-")
            .replace(/[^\w-]/g, "");

    }


    function courseIndex(course) {

        /*
         * Use the course URL when available because it should
         * uniquely identify a course.
         */

        if (course.url) {

            return slugify(course.url);

        }


        /*
         * Fallback to the title.
         */

        return slugify(
            course.title ||
            Math.random().toString()
        );

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

            "Scheduled (online)": "Scheduled — Online",

            "Scheduled (hybrid)": "Scheduled — Hybrid",

            "Scheduled (in-person)": "Scheduled — In-person",

            "Upcoming": "Upcoming",

            "Other": "Other"

        };


        return labels[format] || format;

    }


    // ============================================================
    // RESPONSIVE RESIZE
    // ============================================================

    window.addEventListener(
        "resize",
        function () {

            mapSize = getMapSize();

            svg
                .attr(
                    "width",
                    mapSize.width
                )
                .attr(
                    "height",
                    mapSize.height
                )
                .attr(
                    "viewBox",
                    `0 0 ${mapSize.width} ${mapSize.height}`
                );


            simulation
                .force(
                    "x",
                    d3.forceX(
                        mapSize.width / 2
                    ).strength(0.04)
                )
                .force(
                    "y",
                    d3.forceY(
                        mapSize.height / 2
                    ).strength(0.04)
                )
                .alpha(0.3)
                .restart();

        }
    );


});


</script>


<!-- ============================================================
     STYLES
============================================================ -->

<style>

/* ==============================================================
   PAGE INTRO
============================================================== */

.training-map-intro {
    max-width: 950px;
    margin-bottom: 1.5rem;
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
        rgba(148, 5, 148, 0.12);

}


.map-controls {

    display: flex;

    align-items: center;

    gap: 0.5rem;

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
   MAP
============================================================== */

.training-map-wrapper {

    position: relative;

    width: 100%;

    min-height: 650px;

    height: 75vh;

    max-height: 900px;

    overflow: hidden;

    border: 1px solid #e2e8f0;

    border-radius: 12px;

    background:
        radial-gradient(
            circle at center,
            #ffffff 0%,
            #f8fafc 100%
        );

}


#training-map {

    display: block;

    width: 100%;

    height: 100%;

    cursor: grab;

}


#training-map:active {

    cursor: grabbing;

}


/* ==============================================================
   LOADING / EMPTY
============================================================== */

.map-message {

    position: absolute;

    inset: 0;

    display: flex;

    align-items: center;

    justify-content: center;

    color: #64748b;

    pointer-events: none;

}


/* ==============================================================
   LINKS
============================================================== */

.map-link {

    stroke: #cbd5e1;

    stroke-width: 1.5px;

    opacity: 0.75;

}


.root-group-link {

    stroke: #940594;

    stroke-width: 2.5px;

    opacity: 0.6;

}


.group-topic-link {

    stroke: #94a3b8;

    stroke-width: 1.8px;

}


.topic-course-link {

    stroke: #cbd5e1;

    stroke-width: 1px;

    opacity: 0.45;

}


.map-link.dimmed {

    opacity: 0.05;

}


.map-link.search-match {

    stroke: #940594;

    stroke-width: 2.5px;

    opacity: 0.9;

}


/* ==============================================================
   NODES
============================================================== */

.map-node {

    transition: opacity 0.2s ease;

}


.map-node.dimmed {

    opacity: 0.12;

}


.node-circle {

    stroke-width: 2px;

    transition:
        r 0.2s ease,
        filter 0.2s ease;

}


/* Root */

.root-node .node-circle {

    fill: #002a41;

    stroke: #002a41;

}


.root-node:hover .node-circle {

    filter:
        drop-shadow(
            0 4px 8px
            rgba(0, 42, 65, 0.3)
        );

}


/* Groups */

.group-node .node-circle {

    fill: #940594;

    stroke: #740574;

}


.group-node:hover .node-circle {

    filter:
        drop-shadow(
            0 4px 7px
            rgba(148, 5, 148, 0.3)
        );

}


/* Topics */

.topic-node .node-circle {

    fill: #ffffff;

    stroke: #940594;

}


.topic-node:hover .node-circle {

    filter:
        drop-shadow(
            0 3px 6px
            rgba(148, 5, 148, 0.25)
        );

}


/* Courses */

.course-node .node-circle {

    fill: #e2e8f0;

    stroke: #94a3b8;

}


.course-node:hover .node-circle {

    filter:
        drop-shadow(
            0 2px 5px
            rgba(15, 23, 42, 0.2)
        );

}


/* ==============================================================
   LABELS
============================================================== */

.node-label {

    fill: #334155;

    font-size: 12px;

    font-weight: 500;

    pointer-events: none;

}


.root-node .node-label {

    fill: #002a41;

    font-size: 15px;

    font-weight: 700;

}


.group-node .node-label {

    fill: #334155;

    font-size: 13px;

    font-weight: 700;

}


.topic-node .node-label {

    fill: #475569;

    font-size: 11px;

    font-weight: 600;

}


.course-node .node-label {

    fill: #64748b;

    font-size: 9px;

    font-weight: 400;

}


.group-icon {

    font-size: 14px;

    pointer-events: none;

}


.node-count {

    fill: #940594;

    font-size: 9px;

    font-weight: 700;

    pointer-events: none;

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

    font-size: 0.8rem;

    color: #64748b;

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

    border: 2px solid #940594;

    box-sizing: border-box;

}


.legend-node.course-node {

    background: #e2e8f0;

    border: 1px solid #94a3b8;

}


/* ==============================================================
   INFORMATION PANEL
============================================================== */

.map-info-panel {

    position: fixed;

    z-index: 1000;

    top: 0;

    right: 0;

    width: min(430px, 92vw);

    height: 100vh;

    box-sizing: border-box;

    padding: 2rem;

    overflow-y: auto;

    background: #ffffff;

    border-left: 1px solid #e2e8f0;

    box-shadow:
        -8px 0 30px
        rgba(15, 23, 42, 0.12);

    transform: translateX(105%);

    transition:
        transform 0.3s ease;

}


.map-info-panel.open {

    transform: translateX(0);

}


.close-info-panel {

    position: absolute;

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

    margin-bottom: 1rem;

    color: #002a41;

}


#map-info-content h3 {

    margin-top: 1.5rem;

    margin-bottom: 0.75rem;

    color: #334155;

    font-size: 1rem;

}


/* ==============================================================
   STATS
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
   TOPIC LIST
============================================================== */

.info-topic-list {

    margin: 0;

    padding: 0;

    list-style: none;

}


.info-topic-list li {

    display: flex;

    justify-content: space-between;

    gap: 1rem;

    padding: 0.6rem 0;

    border-bottom: 1px solid #f1f5f9;

    font-size: 0.9rem;

}


.info-topic-list li span {

    color: #940594;

    font-weight: 700;

}


/* ==============================================================
   COURSE CARDS
============================================================== */

.course-list {

    display: flex;

    flex-direction: column;

    gap: 0.8rem;

}


.map-course-card {

    padding: 1rem;

    border: 1px solid #e2e8f0;

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

    margin: 0 0 0.7rem;

    color: #334155;

    font-size: 0.95rem;

    line-height: 1.35;

}


.map-course-meta {

    margin-top: 0.35rem;

    color: #64748b;

    font-size: 0.78rem;

}


.map-course-link {

    display: inline-block;

    margin-top: 0.75rem;

    color: #940594;

    font-size: 0.8rem;

    font-weight: 700;

    text-decoration: none;

}


.map-course-link:hover {

    text-decoration: underline;

}


/* ==============================================================
   COURSE INFO
============================================================== */

.info-meta {

    margin: 0.5rem 0;

    color: #64748b;

    font-size: 0.85rem;

}


.course-topic-tags {

    display: flex;

    flex-wrap: wrap;

    gap: 0.4rem;

}


.course-topic-tags span {

    padding: 0.3rem 0.6rem;

    border-radius: 999px;

    background: #f3e8f3;

    color: #740574;

    font-size: 0.75rem;

}


.primary-course-button {

    display: inline-block;

    margin-top: 1.5rem;

    padding: 0.7rem 1rem;

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
   MOBILE
============================================================== */

@media (max-width: 700px) {

    .map-toolbar {

        align-items: stretch;

    }


    .map-controls {

        width: 100%;

        justify-content: flex-end;

    }


    .training-map-wrapper {

        height: 70vh;

        min-height: 500px;

    }


    .course-node .node-label {

        display: none;

    }


    .node-label {

        font-size: 10px;

    }


    .group-node .node-label {

        font-size: 11px;

    }


    .topic-node .node-label {

        font-size: 9px;

    }


    .map-info-panel {

        width: 100%;

        padding: 1.5rem;

    }

}

</style>