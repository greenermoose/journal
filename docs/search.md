---
layout: page
title: Search & Tags
---

<div class="search-container">
  <input type="text" id="search-input" placeholder="Search posts..." class="search-input" autocomplete="off">
</div>

<div class="tag-cloud">
  {% assign rawtags = "" %}
  {% for post in site.posts %}
    {% assign ttags = post.tags | join:'|' | append:'|' %}
    {% assign rawtags = rawtags | append:ttags %}
  {% endfor %}
  {% assign rawtags = rawtags | split:'|' | sort %}

  {% assign tags = "" %}
  {% for tag in rawtags %}
    {% if tag != "" %}
      {% if tags == "" %}
        {% assign tags = tag | split:'|' %}
      {% endif %}
      {% unless tags contains tag %}
        {% assign tags = tags | join:'|' | append:'|' | append:tag | split:'|' %}
      {% endunless %}
    {% endif %}
  {% endfor %}

  {% for tag in tags %}
    <button class="tag-btn" data-tag="{{ tag }}">{{ tag }}</button>
  {% endfor %}
</div>

<ul id="search-results" class="homesec homesecwritings homesec-content search-results-list">
  <!-- Results will be injected here -->
</ul>

<script>
document.addEventListener("DOMContentLoaded", function() {
  const searchInput = document.getElementById('search-input');
  const resultsContainer = document.getElementById('search-results');
  const tagButtons = document.querySelectorAll('.tag-btn');
  
  let allPosts = [];
  let currentSearch = '';
  let activeTag = null;

  // Fetch search index
  fetch('{{ "/search.json" | relative_url }}')
    .then(response => response.json())
    .then(data => {
      allPosts = data;
      renderResults(allPosts);
    })
    .catch(error => console.error('Error fetching search data:', error));

  searchInput.addEventListener('input', function(e) {
    currentSearch = e.target.value.toLowerCase();
    filterPosts();
  });

  tagButtons.forEach(btn => {
    btn.addEventListener('click', function() {
      const tag = this.getAttribute('data-tag');
      
      // Toggle tag selection
      if (activeTag === tag) {
        activeTag = null;
        this.classList.remove('active');
      } else {
        activeTag = tag;
        tagButtons.forEach(b => b.classList.remove('active'));
        this.classList.add('active');
      }
      
      filterPosts();
    });
  });

  function filterPosts() {
    const filtered = allPosts.filter(post => {
      const matchesSearch = currentSearch === '' || 
                            post.title.toLowerCase().includes(currentSearch) ||
                            post.tags.some(t => t.toLowerCase().includes(currentSearch));
      
      const matchesTag = activeTag === null || post.tags.includes(activeTag);
      
      return matchesSearch && matchesTag;
    });
    
    renderResults(filtered);
  }

  function renderResults(posts) {
    if (posts.length === 0) {
      resultsContainer.innerHTML = '<li><p>No posts found.</p></li>';
      return;
    }
    
    resultsContainer.innerHTML = posts.map(post => {
      return `<li><a href="${post.url}">${post.title}</a> <span class="date-meta">&mdash; ${post.date}</span></li>`;
    }).join('');
  }
});
</script>
