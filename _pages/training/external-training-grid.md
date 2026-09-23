---
layout: splash
permalink: /training/external-training-grid
classes: wide
---

<section class="page-intro training-grid-intro">

```
<h1>Training Explorer</h1>

<p>
    Explore the training available through SHAREing by topic.
    Browse the different training areas, expand a topic to see
    available courses, and click on a course for more information.
</p>
```

</section>

<!-- ============================================================
     TOOLBAR
============================================================ -->

<div class="grid-toolbar">

```
<div class="grid-search-wrapper">

    <input
        type="search"
        id="grid-search"
        class="grid-search"
        placeholder="🔍 Search topics or courses..."
        aria-label="Search topics or courses"
    >

</div>


<div class="grid-toolbar-actions">

    <button
        type="button"
        id="expand-all"
        class="grid-control-button"
    >
        Expand all
    </button>

    <button
        type="button"
        id="collapse-all"
        class="grid-control-button"
    >
        Collapse all
    </button>

    <button
        type="button"
        id="clear-search"
        class="grid-control-button"
    >
        ↺ Reset
    </button>

</div>
```

</div>

<!-- ============================================================
     SEARCH RESULTS MESSAGE
============================================================ -->

<div
    id="grid-empty"
    class="grid-empty"
    style="display: none;"
>
    No matching topics or courses found.
</div>

<!-- ============================================================
     TRAINING GRID
============================================================ -->

<div
    id="training-grid"
    class="training-grid"
>

```
<div class="grid-loading">
    Loading training...
</div>
```

</div>

<!-- ============================================================
     COURSE INFORMATION PANEL
============================================================ -->

<aside
    id="grid-info-panel"
    class="grid-info-panel"
    aria-hidden="true"
>

```
<button
    type="button"
    id="close-grid-info"
    class="close-grid-info"
    aria-label="Close course information"
>
    ×
</button>

<div id="grid-info-content"></div>
```

</aside>

<script>

document.addEventListener("DOMContentLoaded", function () {


    // ============================================================
    // DATA
    // ============================================================

    const courses =
        {{ site.data["external-training"] | jsonify }};


    // ============================================================
    // TOPIC GROUPS
    //
    // Keep this aligned with the main training catalogue.
    // ============================================================

    const topicGroups = {

        "Languages": {

            icon: "💬",

            description:
                "Programming languages and language-specific training.",

            topics: [
                "Fortran",
                "C++",
                "Julia",
                "Python"
            ]

        },


        "Parallelism": {

            icon: "🔀",

            description:
                "Parallel programming, distributed computing and shared memory.",

            topics: [
                "MPI",
                "OpenMP",
                "Parallel Programming",
                "Parallel Computing"
            ]

        },


        "GPU": {

            icon: "🎮",

            description:
                "GPU programming, acceleration and heterogeneous computing.",

            topics: [
                "GPU",
                "CUDA",
                "HIP",
                "OpenACC"
            ]

        },


        "Performance": {

            icon: "📈",

            description:
                "Performance analysis, benchmarking, profiling and optimisation.",

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

            description:
                "Tools, containers, I/O and research software engineering.",

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

            description:
                "Community, professional development and career-focused training.",

            topics: [
                "Seminar",
                "Community",
                "Career Development",
                "Professional Skills"
            ]

        }

    };


    // ============================================================
    // ELEMENTS
    // ============================================================

    const grid =
        document.getElementById("training-grid");

    const searchInput =
        document.getElementById("grid-search");

    const emptyMessage =
        document.getElementById("grid-empty");

    const expandAllButton =
        document.getElementById("expand-all");

    const collapseAllButton =
        document.getElementById("collapse-all");

    const clearSearchButton =
        document.getElementById("clear-search");

    const infoPanel =
        document.getElementById("grid-info-panel");

    const infoContent =
        document.getElementById("grid-info-content");

    const closeInfoButton =
        document.getElementById("close-grid-info");


    // ============================================================
    // PREPARE COURSE DATA
    // ============================================================

    const coursesByTopic = {};


    courses.forEach(course => {

        if (!course.tags) {
            return;
        }


        const topics =
            course.tags
                .split(",")
                .map(tag => tag.trim())
                .filter(Boolean);


        topics.forEach(topic => {

            if (!coursesByTopic[topic]) {
                coursesByTopic[topic] = [];
            }


            /*
             * Avoid duplicate courses if the CSV happens
             * to contain the same course more than once.
             */

            const exists =
                coursesByTopic[topic].some(
                    existing =>
                        courseKey(existing) === courseKey(course)
                );


            if (!exists) {

                coursesByTopic[topic].push(course);

            }

        });

    });


    // ============================================================
    // ADD UNGROUPED TOPICS TO "OTHER"
    // ============================================================

    const knownTopics =
        new Set();


    Object.values(topicGroups).forEach(group => {

        group.topics.forEach(topic => {

            knownTopics.add(topic);

        });

    });


    Object.keys(coursesByTopic).forEach(topic => {

        if (!knownTopics.has(topic)) {

            if (
                !topicGroups["Other"].topics.includes(topic)
            ) {

                topicGroups["Other"].topics.push(topic);

            }

        }

    });


    // ============================================================
    // STATE
    // ============================================================

    const expandedTopics =
        new Set();


    const collapsedGroups =
        new Set();


    // ============================================================
    // RENDER
    // ============================================================

    function render(searchTerm = "") {

        const query =
            searchTerm
                .trim()
                .toLowerCase();


        grid.innerHTML = "";


        let visibleTopicCount = 0;


        Object.entries(topicGroups).forEach(
            ([groupName, groupData]) => {


                // ------------------------------------------------
                // AVAILABLE TOPICS
                // ------------------------------------------------

                const availableTopics =
                    groupData.topics.filter(
                        topic =>
                            coursesByTopic[topic] &&
                            coursesByTopic[topic].length
                    );


                if (!availableTopics.length) {
                    return;
                }


                // ------------------------------------------------
                // FILTER TOPICS
                // ------------------------------------------------

                const matchingTopics =
                    availableTopics.filter(topic => {

                        const topicMatches =
                            topic
                                .toLowerCase()
                                .includes(query);


                        const topicCourses =
                            coursesByTopic[topic] || [];


                        const courseMatches =
                            topicCourses.some(course => {

                                const title =
                                    (
                                        course.title ||
                                        ""
                                    ).toLowerCase();


                                const organisation =
                                    (
                                        course.organisation ||
                                        ""
                                    ).toLowerCase();


                                const tags =
                                    (
                                        course.tags ||
                                        ""
                                    ).toLowerCase();


                                return (
                                    title.includes(query) ||
                                    organisation.includes(query) ||
                                    tags.includes(query)
                                );

                            });


                        return (
                            !query ||
                            topicMatches ||
                            courseMatches
                        );

                    });


                /*
                 * Don't render groups where nothing matches.
                 */

                if (!matchingTopics.length) {
                    return;
                }


                visibleTopicCount +=
                    matchingTopics.length;


                // ------------------------------------------------
                // GROUP CONTAINER
                // ------------------------------------------------

                const groupSection =
                    document.createElement("section");

                groupSection.className =
                    "training-grid-group";


                groupSection.dataset.group =
                    groupName;


                // ------------------------------------------------
                // GROUP HEADER
                // ------------------------------------------------

                const groupHeader =
                    document.createElement("button");

                groupHeader.type =
                    "button";

                groupHeader.className =
                    "training-grid-group-header";


                groupHeader.setAttribute(
                    "aria-expanded",
                    collapsedGroups.has(groupName)
                        ? "false"
                        : "true"
                );


                groupHeader.innerHTML = `

                    <div class="group-heading-main">

                        <span class="group-heading-icon">
                            ${groupData.icon}
                        </span>

                        <div>

                            <h2>
                                ${groupName}
                            </h2>

                            <p>
                                ${groupData.description}
                            </p>

                        </div>

                    </div>


                    <div class="group-heading-meta">

                        <span class="group-count">
                            ${matchingTopics.length}
                            ${
                                matchingTopics.length === 1
                                    ? "topic"
                                    : "topics"
                            }
                        </span>

                        <span class="group-chevron">
                            ${collapsedGroups.has(groupName)
                                ? "+"
                                : "−"}
                        </span>

                    </div>

                `;


                groupHeader.addEventListener(
                    "click",
                    function () {

                        if (
                            collapsedGroups.has(groupName)
                        ) {

                            collapsedGroups.delete(
                                groupName
                            );

                        } else {

                            collapsedGroups.add(
                                groupName
                            );

                        }


                        render(searchInput.value);

                    }
                );


                groupSection.appendChild(
                    groupHeader
                );


                // ------------------------------------------------
                // GROUP CONTENT
                // ------------------------------------------------

                if (
                    !collapsedGroups.has(groupName)
                ) {

                    const topicGrid =
                        document.createElement("div");

                    topicGrid.className =
                        "topic-card-grid";


                    matchingTopics.forEach(topic => {

                        const card =
                            createTopicCard(
                                topic,
                                query
                            );


                        topicGrid.appendChild(card);

                    });


                    groupSection.appendChild(
                        topicGrid
                    );

                }


                grid.appendChild(
                    groupSection
                );

            }
        );


        // ========================================================
        // EMPTY STATE
        // ========================================================

        if (!visibleTopicCount) {

            emptyMessage.style.display =
                "block";

        } else {

            emptyMessage.style.display =
                "none";

        }

    }


    // ============================================================
    // CREATE TOPIC CARD
    // ============================================================

    function createTopicCard(
        topic,
        query
    ) {

        const topicCourses =
            coursesByTopic[topic] || [];


        const card =
            document.createElement("article");

        card.className =
            "topic-card";


        card.dataset.topic =
            topic;


        const isExpanded =
            expandedTopics.has(topic);


        // --------------------------------------------------------
        // FIND SEARCH-MATCHING COURSES
        // --------------------------------------------------------

        let visibleCourses =
            topicCourses;


        if (query) {

            const topicMatches =
                topic
                    .toLowerCase()
                    .includes(query);


            if (!topicMatches) {

                visibleCourses =
                    topicCourses.filter(course => {

                        const title =
                            (
                                course.title ||
                                ""
                            ).toLowerCase();


                        const organisation =
                            (
                                course.organisation ||
                                ""
                            ).toLowerCase();


                        const tags =
                            (
                                course.tags ||
                                ""
                            ).toLowerCase();


                        return (
                            title.includes(query) ||
                            organisation.includes(query) ||
                            tags.includes(query)
                        );

                    });

            }

        }


        // --------------------------------------------------------
        // CARD HEADER
        // --------------------------------------------------------

        const cardButton =
            document.createElement("button");

        cardButton.type =
            "button";

        cardButton.className =
            "topic-card-button";


        cardButton.setAttribute(
            "aria-expanded",
            isExpanded
                ? "true"
                : "false"
        );


        cardButton.innerHTML = `

            <div class="topic-card-top">

                <div class="topic-card-icon">
                    ${topicIcon(topic)}
                </div>

                <div class="topic-card-count">
                    ${topicCourses.length}
                </div>

            </div>


            <div class="topic-card-title">
                ${escapeHtml(topic)}
            </div>


            <div class="topic-card-footer">

                <span>
                    ${
                        topicCourses.length === 1
                            ? "course"
                            : "courses"
                    }
                </span>

                <span class="topic-card-arrow">
                    ${isExpanded ? "↑" : "→"}
                </span>

            </div>

        `;


        cardButton.addEventListener(
            "click",
            function () {

                if (
                    expandedTopics.has(topic)
                ) {

                    expandedTopics.delete(
                        topic
                    );

                } else {

                    expandedTopics.add(
                        topic
                    );

                }


                render(searchInput.value);

            }
        );


        card.appendChild(
            cardButton
        );


        // --------------------------------------------------------
        // EXPANDED COURSE LIST
        // --------------------------------------------------------

        if (isExpanded) {

            const courseContainer =
                document.createElement("div");

            courseContainer.className =
                "topic-expanded-courses";


            visibleCourses.forEach(course => {

                const courseCard =
                    createCourseCard(course);

                courseContainer.appendChild(
                    courseCard
                );

            });


            card.appendChild(
                courseContainer
            );

        }


        return card;

    }


    // ============================================================
    // COURSE CARD
    // ============================================================

    function createCourseCard(course) {

        const courseCard =
            document.createElement("article");

        courseCard.className =
            "grid-course-card";


        courseCard.innerHTML = `

            <div class="grid-course-organisation">

                ${escapeHtml(
                    course.organisation || ""
                )}

            </div>


            <h3>

                ${escapeHtml(
                    course.title ||
                    "Untitled course"
                )}

            </h3>


            ${
                course.format
                    ? `

                        <div class="grid-course-meta">

                            ${formatIcon(course.format)}

                            ${escapeHtml(
                                formatLabel(course.format)
                            )}

                        </div>

                      `
                    : ""
            }


            ${
                course.dates
                    ? `

                        <div class="grid-course-meta">

                            📅

                            ${escapeHtml(
                                course.dates
                            )}

                        </div>

                      `
                    : ""
            }


            ${
                course.location
                    ? `

                        <div class="grid-course-meta">

                            📍

                            ${escapeHtml(
                                course.location
                            )}

                        </div>

                      `
                    : ""
            }


            <div class="grid-course-actions">

                <button
                    type="button"
                    class="grid-course-details"
                >
                    Course details
                </button>


                ${
                    course.url
                        ? `

                            <a
                                href="${escapeAttribute(
                                    course.url
                                )}"
                                target="_blank"
                                rel="noopener"
                                class="grid-course-link"
                            >
                                View course →
                            </a>

                          `
                        : ""
                }

            </div>

        `;


        const detailsButton =
            courseCard.querySelector(
                ".grid-course-details"
            );


        detailsButton.addEventListener(
            "click",
            function (event) {

                event.stopPropagation();

                showCourseInfo(course);

            }
        );


        return courseCard;

    }


    // ============================================================
    // COURSE INFORMATION PANEL
    // ============================================================

    function showCourseInfo(course) {

        const topics =
            course.tags
                ? course.tags
                    .split(",")
                    .map(tag => tag.trim())
                    .filter(Boolean)
                : [];


        infoContent.innerHTML = `

            <div class="grid-info-type">
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

                        <div class="grid-info-organisation">

                            ${escapeHtml(
                                course.organisation
                            )}

                        </div>

                      `
                    : ""
            }


            <div class="grid-info-details">

                ${
                    course.format
                        ? `

                            <div class="grid-info-meta">

                                <span>
                                    ${formatIcon(
                                        course.format
                                    )}
                                </span>

                                <span>
                                    ${escapeHtml(
                                        formatLabel(
                                            course.format
                                        )
                                    )}
                                </span>

                            </div>

                          `
                        : ""
                }


                ${
                    course.dates
                        ? `

                            <div class="grid-info-meta">

                                <span>📅</span>

                                <span>
                                    ${escapeHtml(
                                        course.dates
                                    )}
                                </span>

                            </div>

                          `
                        : ""
                }


                ${
                    course.location
                        ? `

                            <div class="grid-info-meta">

                                <span>📍</span>

                                <span>
                                    ${escapeHtml(
                                        course.location
                                    )}
                                </span>

                            </div>

                          `
                        : ""
                }

            </div>


            ${
                topics.length
                    ? `

                        <div class="grid-info-section">

                            <h3>
                                Topics
                            </h3>


                            <div class="grid-topic-tags">

                                ${topics.map(topic => `

                                    <span>
                                        ${escapeHtml(
                                            topic
                                        )}
                                    </span>

                                `).join("")}

                            </div>

                        </div>

                      `
                    : ""
            }


            ${
                course.url
                    ? `

                        <a
                            href="${escapeAttribute(
                                course.url
                            )}"
                            target="_blank"
                            rel="noopener"
                            class="grid-primary-button"
                        >
                            View course →
                        </a>

                      `
                    : ""
            }

        `;


        infoPanel.classList.add(
            "open"
        );


        infoPanel.setAttribute(
            "aria-hidden",
            "false"
        );

    }


    // ============================================================
    // CLOSE INFORMATION PANEL
    // ============================================================

    function closeInfoPanel() {

        infoPanel.classList.remove(
            "open"
        );


        infoPanel.setAttribute(
            "aria-hidden",
            "true"
        );

    }


    closeInfoButton.addEventListener(
        "click",
        closeInfoPanel
    );


    // ============================================================
    // SEARCH
    // ============================================================

    searchInput.addEventListener(
        "input",
        function () {

            /*
             * When searching, automatically expand topics
             * containing matching courses.
             */

            const query =
                this.value
                    .trim()
                    .toLowerCase();


            if (query) {

                Object.keys(
                    coursesByTopic
                ).forEach(topic => {

                    const topicMatches =
                        topic
                            .toLowerCase()
                            .includes(query);


                    const courseMatches =
                        (
                            coursesByTopic[topic] ||
                            []
                        ).some(course => {

                            const title =
                                (
                                    course.title ||
                                    ""
                                ).toLowerCase();


                            const organisation =
                                (
                                    course.organisation ||
                                    ""
                                ).toLowerCase();


                            const tags =
                                (
                                    course.tags ||
                                    ""
                                ).toLowerCase();


                            return (
                                title.includes(query) ||
                                organisation.includes(query) ||
                                tags.includes(query)
                            );

                        });


                    if (
                        topicMatches ||
                        courseMatches
                    ) {

                        expandedTopics.add(
                            topic
                        );

                    }

                });

            }


            render(query);

        }
    );


    // ============================================================
    // CLEAR SEARCH
    // ============================================================

    clearSearchButton.addEventListener(
        "click",
        function () {

            searchInput.value = "";

            expandedTopics.clear();

            collapsedGroups.clear();

            render();

            closeInfoPanel();

        }
    );


    // ============================================================
    // EXPAND ALL
    // ============================================================

    expandAllButton.addEventListener(
        "click",
        function () {

            Object.keys(
                coursesByTopic
            ).forEach(topic => {

                expandedTopics.add(
                    topic
                );

            });


            collapsedGroups.clear();

            render(
                searchInput.value
            );

        }
    );


    // ============================================================
    // COLLAPSE ALL
    // ============================================================

    collapseAllButton.addEventListener(
        "click",
        function () {

            expandedTopics.clear();


            Object.keys(
                topicGroups
            ).forEach(group => {

                collapsedGroups.add(
                    group
                );

            });


            render(
                searchInput.value
            );

        }
    );


    // ============================================================
    // ICONS
    // ============================================================

    function topicIcon(topic) {

        const icons = {

            "Fortran": "F",

            "C++": "C++",

            "Julia": "J",

            "Python": "🐍",

            "MPI": "↔",

            "OpenMP": "▦",

            "Parallel Programming": "⚡",

            "Parallel Computing": "⚡",

            "GPU": "🎮",

            "CUDA": "C",

            "HIP": "H",

            "OpenACC": "A",

            "Performance": "📈",

            "Performance Analysis": "🔎",

            "Benchmarking": "📊",

            "Optimisation": "⚙",

            "Profiling": "🔬",

            "Containers": "▣",

            "I/O": "⇄",

            "Tools": "🛠",

            "Software Engineering": "💻",

            "Research Software Engineering": "RSE",

            "Seminar": "🎤",

            "Community": "🌍",

            "Career Development": "🚀",

            "Professional Skills": "⭐"

        };


        return icons[topic] || "•";

    }


    // ============================================================
    // FORMAT HELPERS
    // ============================================================

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
    // COURSE KEY
    // ============================================================

    function courseKey(course) {

        if (course.url) {

            return course.url;

        }


        return (
            course.title ||
            ""
        ).toLowerCase();

    }


    // ============================================================
    // HTML ESCAPING
    // ============================================================

    function escapeHtml(value) {

        return String(value)
            .replace(/&/g, "&amp;")
            .replace(/</g, "&lt;")
            .replace(/>/g, "&gt;")
            .replace(/"/g, "&quot;")
            .replace(/'/g, "&#039;");

    }


    function escapeAttribute(value) {

        return String(value)
            .replace(/&/g, "&amp;")
            .replace(/"/g, "&quot;")
            .replace(/</g, "&lt;")
            .replace(/>/g, "&gt;");

    }


    // ============================================================
    // INITIAL RENDER
    // ============================================================

    render();


});
</script>

<style>

/* ==============================================================
   PAGE INTRO
============================================================== */

.training-grid-intro {

    max-width: 950px;

    margin-bottom: 1.5rem;

}


/* ==============================================================
   TOOLBAR
============================================================== */

.grid-toolbar {

    display: flex;

    align-items: center;

    justify-content: space-between;

    gap: 1rem;

    margin: 1.5rem 0;

    flex-wrap: wrap;

}


.grid-search-wrapper {

    flex: 1;

    min-width: 260px;

}


.grid-search {

    width: 100%;

    box-sizing: border-box;

    padding: 0.8rem 1rem;

    border: 1px solid #cbd5e1;

    border-radius: 8px;

    background: #ffffff;

    color: #334155;

    font-size: 0.95rem;

}


.grid-search:focus {

    outline: none;

    border-color: #940594;

    box-shadow:
        0 0 0 3px
        rgba(148, 5, 148, 0.12);

}


.grid-toolbar-actions {

    display: flex;

    gap: 0.5rem;

    flex-wrap: wrap;

}


.grid-control-button {

    border: 1px solid #cbd5e1;

    background: #ffffff;

    color: #334155;

    padding: 0.65rem 0.85rem;

    border-radius: 7px;

    cursor: pointer;

    font-size: 0.85rem;

    transition:
        background 0.15s ease,
        border-color 0.15s ease;

}


.grid-control-button:hover {

    background: #f8fafc;

    border-color: #940594;

}


/* ==============================================================
   EMPTY STATE
============================================================== */

.grid-empty {

    margin: 2rem 0;

    padding: 2rem;

    text-align: center;

    border: 1px solid #e2e8f0;

    border-radius: 10px;

    color: #64748b;

    background: #f8fafc;

}


.grid-loading {

    padding: 3rem;

    text-align: center;

    color: #64748b;

}


/* ==============================================================
   GROUP
============================================================== */

.training-grid-group {

    margin-bottom: 2.5rem;

}


.training-grid-group-header {

    width: 100%;

    display: flex;

    align-items: center;

    justify-content: space-between;

    gap: 1rem;

    padding: 1.1rem 1.25rem;

    margin: 0 0 1rem;

    border: 1px solid #e2e8f0;

    border-radius: 10px;

    background: #f8fafc;

    color: #334155;

    text-align: left;

    cursor: pointer;

    transition:
        border-color 0.2s ease,
        background 0.2s ease,
        box-shadow 0.2s ease;

}


.training-grid-group-header:hover {

    border-color: #c084c0;

    background: #ffffff;

    box-shadow:
        0 3px 10px
        rgba(15, 23, 42, 0.05);

}


.group-heading-main {

    display: flex;

    align-items: center;

    gap: 1rem;

}


.group-heading-icon {

    width: 44px;

    height: 44px;

    flex-shrink: 0;

    display: flex;

    align-items: center;

    justify-content: center;

    border-radius: 10px;

    background: #940594;

    color: #ffffff;

    font-size: 1.3rem;

}


.group-heading-main h2 {

    margin: 0;

    color: #002a41;

    font-size: 1.25rem;

}


.group-heading-main p {

    margin: 0.2rem 0 0;

    color: #64748b;

    font-size: 0.82rem;

}


.group-heading-meta {

    display: flex;

    align-items: center;

    gap: 0.9rem;

    flex-shrink: 0;

}


.group-count {

    color: #940594;

    font-size: 0.8rem;

    font-weight: 700;

}


.group-chevron {

    width: 28px;

    height: 28px;

    display: flex;

    align-items: center;

    justify-content: center;

    border-radius: 50%;

    background: #ffffff;

    border: 1px solid #e2e8f0;

    color: #940594;

    font-size: 1.1rem;

    line-height: 1;

}


/* ==============================================================
   TOPIC GRID
============================================================== */

.topic-card-grid {

    display: grid;

    grid-template-columns:
        repeat(
            auto-fit,
            minmax(
                220px,
                1fr
            )
        );

    gap: 1rem;

}


/* ==============================================================
   TOPIC CARD
============================================================== */

.topic-card {

    min-width: 0;

    border: 1px solid #e2e8f0;

    border-radius: 10px;

    background: #ffffff;

    overflow: hidden;

    transition:
        border-color 0.2s ease,
        box-shadow 0.2s ease,
        transform 0.2s ease;

}


.topic-card:hover {

    border-color: #c084c0;

    box-shadow:
        0 5px 16px
        rgba(15, 23, 42, 0.08);

    transform: translateY(-2px);

}


.topic-card-button {

    width: 100%;

    padding: 1.15rem;

    border: 0;

    background: #ffffff;

    color: #334155;

    text-align: left;

    cursor: pointer;

}


.topic-card-top {

    display: flex;

    align-items: center;

    justify-content: space-between;

    margin-bottom: 1rem;

}


.topic-card-icon {

    width: 42px;

    height: 42px;

    display: flex;

    align-items: center;

    justify-content: center;

    border-radius: 9px;

    background: #f3e8f3;

    color: #740574;

    font-size: 1rem;

    font-weight: 700;

}


.topic-card-count {

    color: #940594;

    font-size: 1.3rem;

    font-weight: 700;

}


.topic-card-title {

    min-height: 2.8rem;

    color: #002a41;

    font-size: 1rem;

    font-weight: 700;

    line-height: 1.4;

}


.topic-card-footer {

    display: flex;

    align-items: center;

    justify-content: space-between;

    margin-top: 1rem;

    padding-top: 0.75rem;

    border-top: 1px solid #f1f5f9;

    color: #64748b;

    font-size: 0.75rem;

}


.topic-card-arrow {

    color: #940594;

    font-size: 1rem;

    font-weight: 700;

}


/* ==============================================================
   EXPANDED COURSES
============================================================== */

.topic-expanded-courses {

    display: flex;

    flex-direction: column;

    gap: 0.6rem;

    padding: 0 0.8rem 0.8rem;

    background: #fafbfc;

    border-top: 1px solid #f1f5f9;

}


/* ==============================================================
   COURSE CARDS
============================================================== */

.grid-course-card {

    padding: 0.85rem;

    border: 1px solid #e2e8f0;

    border-radius: 8px;

    background: #ffffff;

}


.grid-course-card h3 {

    margin: 0.25rem 0 0.6rem;

    color: #334155;

    font-size: 0.88rem;

    line-height: 1.35;

}


.grid-course-organisation {

    color: #940594;

    font-size: 0.65rem;

    font-weight: 700;

    text-transform: uppercase;

    letter-spacing: 0.04em;

}


.grid-course-meta {

    margin-top: 0.3rem;

    color: #64748b;

    font-size: 0.72rem;

}


.grid-course-actions {

    display: flex;

    align-items: center;

    justify-content: space-between;

    gap: 0.5rem;

    margin-top: 0.75rem;

}


.grid-course-details {

    padding: 0;

    border: 0;

    background: transparent;

    color: #940594;

    font-size: 0.72rem;

    font-weight: 700;

    cursor: pointer;

}


.grid-course-details:hover {

    text-decoration: underline;

}


.grid-course-link {

    color: #940594;

    font-size: 0.72rem;

    font-weight: 700;

    text-decoration: none;

}


.grid-course-link:hover {

    text-decoration: underline;

}


/* ==============================================================
   INFORMATION PANEL
============================================================== */

.grid-info-panel {

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


.grid-info-panel.open {

    transform: translateX(0);

}


.close-grid-info {

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


.close-grid-info:hover {

    background: #e2e8f0;

}


#grid-info-content {

    padding-top: 1rem;

}


.grid-info-type {

    margin-bottom: 0.5rem;

    color: #940594;

    font-size: 0.75rem;

    font-weight: 700;

    text-transform: uppercase;

    letter-spacing: 0.06em;

}


#grid-info-content h2 {

    margin-top: 0;

    margin-bottom: 0.8rem;

    padding-right: 2rem;

    color: #002a41;

    font-size: 1.5rem;

    line-height: 1.3;

}


.grid-info-organisation {

    margin-bottom: 1.2rem;

    color: #940594;

    font-size: 0.75rem;

    font-weight: 700;

    text-transform: uppercase;

    letter-spacing: 0.04em;

}


.grid-info-details {

    padding: 0.9rem 1rem;

    border-radius: 8px;

    background: #f8fafc;

}


.grid-info-meta {

    display: flex;

    gap: 0.6rem;

    margin: 0.4rem 0;

    color: #64748b;

    font-size: 0.85rem;

}


.grid-info-section {

    margin-top: 1.5rem;

}


.grid-info-section h3 {

    margin: 0 0 0.7rem;

    color: #334155;

    font-size: 1rem;

}


.grid-topic-tags {

    display: flex;

    flex-wrap: wrap;

    gap: 0.4rem;

}


.grid-topic-tags span {

    padding: 0.3rem 0.6rem;

    border-radius: 999px;

    background: #f3e8f3;

    color: #740574;

    font-size: 0.75rem;

}


.grid-primary-button {

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


.grid-primary-button:hover {

    background: #740574;

}


/* ==============================================================
   MOBILE
============================================================== */

@media (max-width: 700px) {

    .grid-toolbar {

        align-items: stretch;

    }


    .grid-search-wrapper {

        min-width: 100%;

    }


    .grid-toolbar-actions {

        width: 100%;

    }


    .grid-control-button {

        flex: 1;

    }


    .training-grid-group-header {

        padding: 0.9rem;

    }


    .group-heading-icon {

        width: 38px;

        height: 38px;

        font-size: 1.1rem;

    }


    .group-heading-main {

        gap: 0.7rem;

    }


    .group-heading-main h2 {

        font-size: 1.05rem;

    }


    .group-heading-main p {

        font-size: 0.72rem;

    }


    .group-count {

        display: none;

    }


    .topic-card-grid {

        grid-template-columns:
            repeat(
                2,
                minmax(
                    0,
                    1fr
                )
            );

        gap: 0.7rem;

    }


    .topic-card-button {

        padding: 0.85rem;

    }


    .topic-card-icon {

        width: 34px;

        height: 34px;

        font-size: 0.85rem;

    }


    .topic-card-count {

        font-size: 1.05rem;

    }


    .topic-card-title {

        min-height: auto;

        font-size: 0.85rem;

    }


    .topic-card-footer {

        font-size: 0.68rem;

    }


    .grid-info-panel {

        width: 100%;

        padding: 1.5rem;

    }

}


@media (max-width: 430px) {

    .topic-card-grid {

        grid-template-columns: 1fr;

    }

}

</style>
