---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

{% if site.author.googlescholar %}
  <div class="wordwrap">You can also find my articles on <a href="{{site.author.googlescholar}}">my Google Scholar profile</a>.</div>
{% endif %}

After 2023
======
* Peng, K., Wright, D., et al., (2024). STREAM-Sat: A Novel Near-Realtime Quasi-global Satellite-Only Ensemble Precipitation Dataset. Water resources research
* Peng, K., Wright, D., & Derin, Y., Alexander, A., Pradhan, A., Hartke S., Li, Z., Tan, J., Quantifying Satellite Precipitation and Hydrologic Model Parameter Uncertainties to Advance Large-Scale Flood Prediction Systems, WaterSciCon24, 2024
* Peng, K., Wright, D., & Derin, Y., Hartke S., Li, Z., Tan, J., and Alexander, A., Advancing Hydrologic Prediction and Decision-making in Ungauged Regions Through Satellite Precipitation Uncertainty Estimation, 2023 AGU Annual Fall Meeting, 2023
* Wright, D., Peng, K., & Tan J., Global Multiscale Uncertainty Estimation for Satellite Precipitation Products to Improve Hydrologic Prediction., 2023 NASA Precipitation Measurement Mission Science Team Meeting, 2023

Before 2023
======
* Peng, K., Xie, H., Xu, Q., Huang, P., & Liu, Z. (2022). A Physics-Assisted Convolutional Neural Network for Bathymetric Mapping Using ICESat-2 and Sentinel-2 Data. IEEE Transactions on Geoscience and Remote Sensing, 60, 1-13. doi:10.1109/TGRS.2022.3213248
* Peng, K., Wang, Q., Tang, Y., Tong, X., & Atkinson, P. M. (2022). Geographically Weighted Spatial Unmixing for Spatiotemporal Fusion. IEEE Transactions on Geoscience and Remote Sensing, 60, 1-17. doi:10.1109/TGRS.2021.3115136
* Wang, Q., Peng, K., Tang, Y., Tong, X., & Atkinson, P. M. (2021). Blocks-removed spatial unmixing for downscaling MODIS images. Remote Sensing of Environment, 256, 112325. doi: https://doi.org/10.1016/j.rse.2021.112325

{% assign pubs_by_year = site.publications | sort: "date" | reverse | group_by_exp: "item", "item.date | date: '%Y'" %}

<div class="row">
    <div class="col-12 col-lg-10">
        {% for year in pubs_by_year %}
        {% assign num_papers = year.items | size %}
        <h2 class="pt-4" id="year-{{ year.name }}">{{ year.name }}</h2>
        <div class="my-0 p-0 bg-white shadow-sm rounded-sm">
            {% for item in year.items %}
                {% include widgets/publication_item.html item=item hide_bottom_border=forloop.last first=forloop.first last=forloop.last %}
            {% endfor %}
        </div>
        {% endfor %}
    </div>

    <div class="col-2 d-none d-lg-block">
        <div id="navbar-year" class="nav nav-pills flex-column sticky-top" style="top: 80px">
            {% for year in pubs_by_year %}
            <a class="nav-link d-block" href="#year-{{ year.name }}">{{ year.name }}</a>
            {% endfor %}
        </div>
    </div>

</div>
