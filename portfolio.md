---
layout: page
title: Portfolio
permalink: /portfolio/
---

<style>
.projects-container {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
    justify-content: space-between;
}
.project {
    flex: 1 1 calc(50% - 40px);
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    padding: 10px;
    margin: 10px 0;
    border-radius: 5px;
    background-color: #fff;
}
.project img {
    width: 100%;
    border-radius: 5px;
}
@media (max-width: 768px) {
    .project {
        flex: 1 1 100%;
    }
}
button {
    margin: 5px;
    padding: 10px;
    border: none;
    background-color: #007BFF;
    color: white;
    border-radius: 5px;
    cursor: pointer;
}
button.active {
    background-color: #0056b3;
}
</style>

<div>
    <button class="filter-button" data-filter="all">All</button>
    <button class="filter-button" data-filter="classification">Classification</button>
    <button class="filter-button" data-filter="detection">Detection</button>
    <button class="filter-button" data-filter="segmentation">Segmentation</button>
    <button class="filter-button" data-filter="face">Face</button>
</div>



<script>
document.addEventListener('DOMContentLoaded', function () {
    const buttons = document.querySelectorAll('.filter-button');
    const projects = document.querySelectorAll('.project');

    buttons.forEach(button => {
        button.addEventListener('click', () => {
            buttons.forEach(btn => btn.classList.remove('active'));
            button.classList.add('active');

            const filter = button.getAttribute('data-filter');

            projects.forEach(project => {
                if (filter === 'all' || project.getAttribute('data-tags').includes(filter)) {
                    project.style.display = 'block';
                } else {
                    project.style.display = 'none';
                }
            });
        });
    });

});
</script>
