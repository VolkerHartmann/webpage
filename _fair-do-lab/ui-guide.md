---
title: FAIR DO Lab - User Interfaces
breadcrumbs: /typed-pid-maker/ui-guide
layout: default
description: Demo interfaces for exporation.
repository_url: https://github.com/kit-data-manager/FAIR-DO-Lab
repository_name: kit-data-manager/FAIR-DO-Lab
navigation_id: fair_do_lab_index
---

# {{ page.title }}

The FAIR DO Lab contains user interfaces to demonstrate the services. Not all of them are meant for production.

## Kibana

Kibana can be used to explore the database, but is being considered a management interface. It is not a simple interface for everyday search requests that should be accessible to all users. Kibana is available via <http://127.0.0.1:5601>.

- Click on discover in the left-side menu.

    ![](../assets/images/fair-do-lab/Kibana-1-discover.png){:class="max-h-96"}

- Set `record*` as the index pattern.

    ![](../assets/images/fair-do-lab/Kibana-2-index-pattern.png){:class="max-h-52"}

- You can not set a time filter or choose not to.

    ![](../assets/images/fair-do-lab/Kibana-3-time-filter.png){:class="max-h-52"}

- Click on Discover again (see first image)

- View and search through your PIDs.

    ![](../assets/images/fair-do-lab/Kibana-4-query.png){:class="max-h-96"}