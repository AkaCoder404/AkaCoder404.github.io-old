---
title: Photography
subtitle: 
has_more_link: true
more_link_text: Keep reading
carousel-images: 
  - ../images/photographs/9.JPG
  - ../images/photographs/5.jpg
  - ../images/photographs/8.JPG
images: 
  - ../images/photographs/1.png
  - ../images/photographs/2.png
  - ../images/photographs/4.png
  - ../images/photographs/5.jpg
  - ../images/photographs/6.JPG
  - ../images/photographs/7.JPG
  - ../images/photographs/8.JPG
  - ../images/photographs/9.JPG
  - ../images/photographs/10.JPG
  - ../images/photographs/3.JPG
seo:
  title: Photography
  description: personal photo album
  extra:
    - name: 'og:type'
      value: website
      keyName: property
    - name: 'og:title'
      value: Personal Website
      keyName: property
    - name: 'og:description'
      value: personal photo album
      keyName: property
    - name: 'og:image'
      value: images/home.jpg
      keyName: property
      relativeUrl: true
    - name: 'twitter:card'
      value: summary_large_image
    - name: 'twitter:title'
      value: Personal Website
    - name: 'twitter:description'
      value: personal photo album
    - name: 'twitter:image'
      value: images/home.jpg
      relativeUrl: true
layout: photos

---

<div id="carouselExampleControls" class="carousel slide mb-4" data-ride="carousel">
    <div class="carousel-inner">
        {% for car-img in page.carousel-images %}
            <div class="carousel-item {% if forloop.first %}active{% endif %}">
                <img src="{{ car-img }}" class="d-block w-100" alt="">
            </div>
        {% endfor %}
    </div>
    <a class="carousel-control-prev" href="#carouselExampleControls" role="button" data-slide="prev">
        <span class="carousel-control-prev-icon" aria-hidden="true"></span>
        <span class="sr-only">Previous</span>
    </a>
    <a class="carousel-control-next" href="#carouselExampleControls" role="button" data-slide="next">
        <span class="carousel-control-next-icon" aria-hidden="true"></span>
        <span class="sr-only">Next</span>
    </a>
</div>

<!-- layout -->

<div class="card-columns">
    {% for img in page.images %}
    <div class="card" data-toggle="modal" data-target="#exampleModal" data-img="{{ img }}">
        <img class="card-img-top" src="{{ img }}" />
    </div>
    {% endfor %}
</div>

<div class="modal fade" id="exampleModal">
  <div class="modal-dialog modal-lg modal-dialog-centered">
    <div class="modal-content">
      <div class="modal-body">
        <img class="modal-img w-100" />
      </div>
    </div>
  </div>
</div>

<script type="text/javascript">
  $(document).ready(function() {
    $('#exampleModal').on('show.bs.modal', function (event) {
      var button = $(event.relatedTarget)
      var img = button.data('img')
      var modal = $(this)
      modal.find('.modal-img').attr('src', img)
      console.log("hello")
    })
  })
</script>

