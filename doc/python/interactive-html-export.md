---
jupyter:
  jupytext:
    notebook_metadata_filter: all
    text_representation:
      extension: .md
      format_name: markdown
      format_version: '1.3'
      jupytext_version: 1.14.1
  kernelspec:
    display_name: Python 3
    language: python
    name: python3
  language_info:
    codemirror_mode:
      name: ipython
      version: 3
    file_extension: .py
    mimetype: text/x-python
    name: python
    nbconvert_exporter: python
    pygments_lexer: ipython3
    version: 3.8.8
  plotly:
    description: Plotly allows you to save interactive HTML versions of your figures
      to your local disk.
    display_as: file_settings
    language: python
    layout: base
    name: Interactive HTML Export
    order: 31
    page_type: u-guide
    permalink: python/interactive-html-export/
    thumbnail: thumbnail/static-image-export.png
---

### Interactive vs Static Export

Plotly figures are interactive when viewed in a web browser: you can hover over data points, pan and zoom axes, and show and hide traces by clicking or double-clicking on the legend. You can export figures either to [static image file formats like PNG, JPEG, SVG or PDF](/python/static-image-export/) or you can export them to HTML files which can be opened in a browser. This page explains how to do the latter.

<!-- #region -->
### Saving to an HTML file

Any figure can be saved as an HTML file using the `write_html` method. These HTML files can be opened in any web browser to access the fully interactive figure.

```python
import plotly.express as px

fig = px.scatter(x=range(10), y=range(10))
fig.write_html("path/to/file.html")
```
<!-- #endregion -->

### Controlling the size of the HTML file

By default, the resulting HTML file is a fully self-contained HTML file which can be uploaded to a web server or shared via email or other file-sharing mechanisms. The downside to this approach is that the file is very large (5Mb+) because it contains an inlined copy of the Plotly.js library required to make the figure interactive. This can be controlled via the `include_plotlyjs` argument (see below).


### HTML export in Dash

[Dash](https://plotly.com/dash/) is the best way to build analytical apps in Python using Plotly figures. To run the app below, run `pip install dash`, click "Download" to get the code and run `python app.py`.

Get started  with [the official Dash docs](https://dash.plotly.com/installation) and **learn how to effortlessly [style](https://plotly.com/dash/design-kit/) & [deploy](https://plotly.com/dash/app-manager/) apps like this with <a class="plotly-red" href="https://plotly.com/dash/">Dash Enterprise</a>.**


```python hide_code=true
from IPython.display import IFrame
snippet_url = 'https://python-docs-dash-snippets.herokuapp.com/python-docs-dash-snippets/'
IFrame(snippet_url + 'interactive-html-export', width='100%', height=1200)
```

<div style="font-size: 0.9em;"><div style="width: calc(100% - 30px); box-shadow: none; border: thin solid rgb(229, 229, 229);"><div style="padding: 5px;"><div><p><strong>Sign up for Dash Club</strong> → Free cheat sheets plus updates from Chris Parmer and Adam Schroeder delivered to your inbox every two months. Includes tips and tricks, community apps, and deep dives into the Dash architecture.
<u><a href="https://go.plotly.com/dash-club?utm_source=Dash+Club+2022&utm_medium=graphing_libraries&utm_content=inline">Join now</a></u>.</p></div></div></div></div>


### Full Parameter Documentation

```python
import plotly.graph_objects as go

help(go.Figure.write_html)
```
