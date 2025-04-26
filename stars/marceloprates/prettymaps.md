---
project: prettymaps
stars: 11618
description: Draw pretty maps from OpenStreetMap data! Built with osmnx +matplotlib + shapely
url: https://github.com/marceloprates/prettymaps
---

prettymaps
==========

A minimal Python library to draw customized maps from OpenStreetMap created using the osmnx, matplotlib, shapely and vsketch packages.

Prettymaps is now available as a streamlit app!
===============================================

This work is licensed under a GNU Affero General Public License v3.0 (you can make commercial use, distribute and modify this project, but must **disclose** the source code with the license and copyright notice)

Note about crediting and NFTs:
------------------------------

-   Please keep the printed message on the figures crediting my repository and OpenStreetMap (mandatory by their license).
-   I am personally **against** NFTs for their environmental impact, the fact that they're a giant money-laundering pyramid scheme and the structural incentives they create for theft in the open source and generative art communities.
-   **I do not authorize in any way this project to be used for selling NFTs**, although I cannot legally enforce it. **Respect the creator**.
-   The AeternaCivitas and geoartnft projects have used this work to sell NFTs and refused to credit it. See how they reacted after being exposed: AeternaCivitas, geoartnft.
-   **I have closed my other generative art projects on Github and won't be sharing new ones as open source to protect me from the NFT community**.

As seen on Hacker News:
-----------------------

prettymaps subreddit
--------------------

Google Colaboratory Demo
------------------------

Installation
============

### Install locally:

Install prettymaps with:

```
pip install prettymaps
```

### Install on Google Colaboratory:

Install prettymaps with:

```
!pip install -e "git+https://github.com/marceloprates/prettymaps#egg=prettymaps"
```

Then **restart the runtime** (Runtime -> Restart Runtime) before importing prettymaps

Run front-end
=============

After prettymaps is installed, you can run the front-end (streamlit) application from the prettymaps repository using:

```
streamlit run app.py
```

Tutorial
========

Plotting with prettymaps is very simple. Run:

prettymaps.plot(your\_query)

**your\_query** can be:

1.  An address (Example: "Porto Alegre"),
2.  Latitude / Longitude coordinates (Example: (-30.0324999, -51.2303767))
3.  A custom boundary in GeoDataFrame format

%reload\_ext autoreload
%autoreload 2

import prettymaps

plot \= prettymaps.plot('Stad van de Zon, Heerhugowaard, Netherlands')

You can also choose from different "presets" (parameter combinations saved in JSON files)

See below an example using the "minimal" preset

import prettymaps

plot \= prettymaps.plot(
    'Stad van de Zon, Heerhugowaard, Netherlands',
    preset \= 'minimal'
)

Run

prettymaps.presets()

to list all available presets:

import prettymaps

prettymaps.presets()

<style scoped> .dataframe tbody tr th:only-of-type { vertical-align: middle; }

```
.dataframe tbody tr th {
    vertical-align: top;
}

.dataframe thead th {
    text-align: right;
}
```

</style>

preset

params

0

abraca-redencao

{'layers': {'perimeter': {}, 'streets': {'widt...

1

barcelona

{'layers': {'perimeter': {'circle': False}, 's...

2

barcelona-plotter

{'layers': {'streets': {'width': {'primary': 5...

3

cb-bf-f

{'layers': {'streets': {'width': {'trunk': 6, ...

4

default

{'layers': {'perimeter': {}, 'streets': {'widt...

5

heerhugowaard

{'layers': {'perimeter': {}, 'streets': {'widt...

6

macao

{'layers': {'perimeter': {}, 'streets': {'cust...

7

minimal

{'layers': {'perimeter': {}, 'streets': {'widt...

8

my-preset

{'layers': {'building': {'tags': {'building': ...

9

plotter

{'layers': {'perimeter': {}, 'streets': {'widt...

10

tijuca

{'layers': {'perimeter': {}, 'streets': {'widt...

To examine a specific preset, run:

import prettymaps

prettymaps.preset('default')

```
Preset(params={'layers': {'perimeter': {}, 'streets': {'width': {'motorway': 5, 'trunk': 5, 'primary': 4.5, 'secondary': 4, 'tertiary': 3.5, 'cycleway': 3.5, 'residential': 3, 'service': 2, 'unclassified': 2, 'pedestrian': 2, 'footway': 1}}, 'waterway': {'tags': {'waterway': ['river', 'stream']}, 'width': {'river': 20, 'stream': 10}}, 'building': {'tags': {'building': True, 'landuse': 'construction'}}, 'water': {'tags': {'natural': ['water', 'bay']}}, 'sea': {}, 'forest': {'tags': {'landuse': 'forest'}}, 'green': {'tags': {'landuse': ['grass', 'orchard'], 'natural': ['island', 'wood', 'wetland'], 'leisure': 'park'}}, 'rock': {'tags': {'natural': 'bare_rock'}}, 'beach': {'tags': {'natural': 'beach'}}, 'parking': {'tags': {'amenity': 'parking', 'highway': 'pedestrian', 'man_made': 'pier'}}}, 'style': {'perimeter': {'fill': False, 'lw': 0, 'zorder': 0}, 'background': {'fc': '#F2F4CB', 'zorder': -1}, 'green': {'fc': '#8BB174', 'ec': '#2F3737', 'hatch_c': '#A7C497', 'hatch': 'ooo...', 'lw': 1, 'zorder': 1}, 'forest': {'fc': '#64B96A', 'ec': '#2F3737', 'lw': 1, 'zorder': 2}, 'water': {'fc': '#a8e1e6', 'ec': '#2F3737', 'hatch_c': '#9bc3d4', 'hatch': 'ooo...', 'lw': 1, 'zorder': 99}, 'sea': {'fc': '#a8e1e6', 'ec': '#2F3737', 'hatch_c': '#9bc3d4', 'hatch': 'ooo...', 'lw': 1, 'zorder': 99}, 'waterway': {'fc': '#a8e1e6', 'ec': '#2F3737', 'hatch_c': '#9bc3d4', 'hatch': 'ooo...', 'lw': 1, 'zorder': 200}, 'beach': {'fc': '#FCE19C', 'ec': '#2F3737', 'hatch_c': '#d4d196', 'hatch': 'ooo...', 'lw': 1, 'zorder': 3}, 'parking': {'fc': '#F2F4CB', 'ec': '#2F3737', 'lw': 1, 'zorder': 3}, 'streets': {'fc': '#2F3737', 'ec': '#475657', 'alpha': 1, 'lw': 0, 'zorder': 4}, 'building': {'palette': ['#433633', '#FF5E5B'], 'ec': '#2F3737', 'lw': 0.5, 'zorder': 5}, 'rock': {'fc': '#BDC0BA', 'ec': '#2F3737', 'lw': 1, 'zorder': 6}}, 'circle': None, 'radius': 500})
```

Insted of using the default configuration you can customize several parameters. The most important are:

-   layers: A dictionary of OpenStreetMap layers to fetch.
    -   Keys: layer names (arbitrary)
    -   Values: dicts representing OpenStreetMap queries
-   style: Matplotlib style parameters
    -   Keys: layer names (the same as before)
    -   Values: dicts representing Matplotlib style parameters

plot \= prettymaps.plot(
    \# Your query. Example: "Porto Alegre" or (-30.0324999, -51.2303767) (GPS coords)
    your\_query,
    \# Dict of OpenStreetMap Layers to plot. Example:
    \# {'building': {'tags': {'building': True}}, 'water': {'tags': {'natural': 'water'}}}
    \# Check the /presets folder for more examples
    layers,
    \# Dict of style parameters for matplotlib. Example:
    \# {'building': {'palette': \['#f00','#0f0','#00f'\], 'edge\_color': '#333'}}
    style,
    \# Preset to load. Options include:
    \# \['default', 'minimal', 'macao', 'tijuca'\]
    preset,
    \# Save current parameters to a preset file.
    \# Example: "my-preset" will save to "presets/my-preset.json"
    save\_preset,
    \# Whether to update loaded preset with additional provided parameters. Boolean
    update\_preset,
    \# Plot with circular boundary. Boolean
    circle,
    \# Plot area radius. Float
    radius,
    \# Dilate the boundary by this amount. Float
    dilate
)

**plot** is a python dataclass containing:

@dataclass
class Plot:
    \# A dictionary of GeoDataFrames (one for each plot layer)
    geodataframes: Dict\[str, gp.GeoDataFrame\]
    \# A matplotlib figure
    fig: matplotlib.figure.Figure
    \# A matplotlib axis object
    ax: matplotlib.axes.Axes

Here's an example of running prettymaps.plot() with customized parameters:

import prettymaps

plot \= prettymaps.plot(
    'Praça Ferreira do Amaral, Macau',
    circle \= True,
    radius \= 1100,
    layers \= {
        "green": {
            "tags": {
                "landuse": "grass",
                "natural": \["island", "wood"\],
                "leisure": "park"
            }
        },
        "forest": {
            "tags": {
                "landuse": "forest"
            }
        },
        "water": {
            "tags": {
                "natural": \["water", "bay"\]
            }
        },
        "parking": {
            "tags": {
                "amenity": "parking",
                "highway": "pedestrian",
                "man\_made": "pier"
            }
        },
        "streets": {
            "width": {
                "motorway": 5,
                "trunk": 5,
                "primary": 4.5,
                "secondary": 4,
                "tertiary": 3.5,
                "residential": 3,
            }
        },
        "building": {
            "tags": {"building": True},
        },
    },
    style \= {
        "background": {
            "fc": "#F2F4CB",
            "ec": "#dadbc1",
            "hatch": "ooo...",
        },
        "perimeter": {
            "fc": "#F2F4CB",
            "ec": "#dadbc1",
            "lw": 0,
            "hatch": "ooo...",
        },
        "green": {
            "fc": "#D0F1BF",
            "ec": "#2F3737",
            "lw": 1,
        },
        "forest": {
            "fc": "#64B96A",
            "ec": "#2F3737",
            "lw": 1,
        },
        "water": {
            "fc": "#a1e3ff",
            "ec": "#2F3737",
            "hatch": "ooo...",
            "hatch\_c": "#85c9e6",
            "lw": 1,
        },
        "parking": {
            "fc": "#F2F4CB",
            "ec": "#2F3737",
            "lw": 1,
        },
        "streets": {
            "fc": "#2F3737",
            "ec": "#475657",
            "alpha": 1,
            "lw": 0,
        },
        "building": {
            "palette": \[
                "#FFC857",
                "#E9724C",
                "#C5283D"
            \],
            "ec": "#2F3737",
            "lw": 0.5,
        }
    }
)

In order to plot an entire region and not just a rectangular or circular area, set

radius \= False

import prettymaps

plot \= prettymaps.plot(
    'Bom Fim, Porto Alegre, Brasil', radius \= False,
)

You can access layers's GeoDataFrames directly like this:

import prettymaps

\# Run prettymaps in show = False mode (we're only interested in obtaining the GeoDataFrames)
plot \= prettymaps.plot('Centro Histórico, Porto Alegre', show \= False)
plot.geodataframes\['building'\]

<style scoped> .dataframe tbody tr th:only-of-type { vertical-align: middle; }

```
.dataframe tbody tr th {
    vertical-align: top;
}

.dataframe thead th {
    text-align: right;
}
```

</style>

geometry

bicycle

highway

leisure

addr:housenumber

addr:street

amenity

operator

website

historic

...

contact:website

bus

smoothness

inscription

ways

boat

name:fr

type

building:part

architect

(node, 2407915698)

POINT (-51.23212 -30.03670)

NaN

NaN

NaN

820

Rua Washington Luiz

NaN

NaN

NaN

NaN

...

NaN

NaN

NaN

NaN

NaN

NaN

NaN

NaN

NaN

NaN

(way, 126665330)

POLYGON ((-51.23518 -30.03275, -51.23512 -30.0...

NaN

NaN

NaN

387

Rua dos Andradas

place\_of\_worship

NaN

NaN

NaN

...

NaN

NaN

NaN

NaN

NaN

NaN

NaN

NaN

NaN

NaN

(way, 126665331)

POLYGON ((-51.23167 -30.03066, -51.23160 -30.0...

NaN

NaN

NaN

1001

Rua dos Andradas

NaN

NaN

https://www.ruadapraiashopping.com.br/

NaN

...

NaN

NaN

NaN

NaN

NaN

NaN

NaN

NaN

NaN

NaN

(way, 129176990)

POLYGON ((-51.23117 -30.02891, -51.23120 -30.0...

NaN

NaN

NaN

1020

Rua 7 de Setembro

NaN

NaN

http://www.memorial.rs.gov.br

NaN

...

NaN

NaN

NaN

NaN

NaN

NaN

NaN

NaN

NaN

NaN

(way, 129176991)

POLYGON ((-51.23153 -30.02914, -51.23156 -30.0...

NaN

NaN

NaN

NaN

Praça da Alfândega

NaN

NaN

https://www.margs.rs.gov.br/

NaN

...

NaN

NaN

NaN

NaN

NaN

NaN

NaN

NaN

NaN

NaN

...

...

...

...

...

...

...

...

...

...

...

...

...

...

...

...

...

...

...

...

...

...

(relation, 6760281)

POLYGON ((-51.23238 -30.03337, -51.23223 -30.0...

NaN

NaN

NaN

NaN

NaN

NaN

NaN

NaN

NaN

...

NaN

NaN

NaN

NaN

\[457506887, 457506886\]

NaN

NaN

multipolygon

NaN

NaN

(relation, 6760282)

POLYGON ((-51.23203 -30.03340, -51.23203 -30.0...

NaN

NaN

NaN

NaN

NaN

NaN

NaN

NaN

NaN

...

NaN

NaN

NaN

NaN

\[457506875, 457506889, 457506888\]

NaN

NaN

multipolygon

NaN

NaN

(relation, 6760283)

POLYGON ((-51.23284 -30.03367, -51.23288 -30.0...

NaN

NaN

NaN

NaN

NaN

NaN

NaN

NaN

NaN

...

NaN

NaN

NaN

NaN

\[457506897, 457506896\]

NaN

NaN

multipolygon

NaN

Theodor Wiederspahn

(relation, 6760284)

POLYGON ((-51.23499 -30.03412, -51.23498 -30.0...

NaN

NaN

NaN

NaN

NaN

NaN

NaN

NaN

NaN

...

NaN

NaN

NaN

NaN

\[457506910, 457506913\]

NaN

NaN

multipolygon

NaN

NaN

(relation, 14393526)

POLYGON ((-51.23125 -30.02813, -51.23128 -30.0...

NaN

NaN

NaN

1044

Rua Siqueira Campos

NaN

NaN

https://www.sefaz.rs.gov.br

NaN

...

NaN

NaN

NaN

NaN

\[236213286, 1081974882\]

NaN

NaN

multipolygon

NaN

NaN

2420 rows × 167 columns

Search a building by name and display it:

plot.geodataframes\['building'\]\[
        plot.geodataframes\['building'\].name \== 'Catedral Metropolitana Nossa Senhora Mãe de Deus'
\].geometry\[0\]

```
/home/marcelo/anaconda3/envs/prettymaps/lib/python3.11/site-packages/geopandas/geoseries.py:648: FutureWarning: Series.__getitem__ treating keys as positions is deprecated. In a future version, integer keys will always be treated as labels (consistent with DataFrame behavior). To access a value by position, use `ser.iloc[pos]`
  val = getattr(super(), mtd)(*args, **kwargs)
```

Plot mosaic of building footprints

import prettymaps
import numpy as np
import osmnx as ox
from matplotlib import pyplot as plt

\# Run prettymaps in show = False mode (we're only interested in obtaining the GeoDataFrames)
plot \= prettymaps.plot('Porto Alegre', show \= False)
\# Get list of buildings from plot's geodataframes dict
buildings \= plot.geodataframes\['building'\]
\# Project from lat / long
buildings \= ox.project\_gdf(buildings)
buildings \= \[b for b in buildings.geometry if b.area \> 0\]

\# Draw Matplotlib mosaic of n x n building footprints
n \= 6
fig,axes \= plt.subplots(n,n, figsize \= (7,6))
\# Set background color
fig.patch.set\_facecolor('#5cc0eb')
\# Figure title
fig.suptitle(
    'Buildings of Porto Alegre',
    size \= 25,
    color \= '#fff'
)
\# Draw each building footprint on a separate axis
for ax,building in zip(np.concatenate(axes),buildings):
    ax.plot(\*building.exterior.xy, c \= '#ffffff')
    ax.autoscale(); ax.axis('off'); ax.axis('equal')

Access plot.ax or plot.fig to add new elements to the matplotlib plot:

import prettymaps

plot \= prettymaps.plot(
    (41.39491,2.17557),
    preset \= 'barcelona',
    show \= False \# We don't want to render the map yet
)

\# Change background color
plot.fig.patch.set\_facecolor('#F2F4CB')
\# Add title
\_ \= plot.ax.set\_title(
    'Barcelona',
    font \= 'serif',
    size \= 50
)

Use **plotter** mode to export a pen plotter-compatible SVG (thanks to abey79's amazing vsketch library)

import prettymaps

plot \= prettymaps.plot(
    (41.39491,2.17557),
    mode \= 'plotter',
    layers \= dict(perimeter \= {}),
    preset \= 'barcelona-plotter',
    scale\_x \= .6,
    scale\_y \= \-.6,
)

Some other examples

import prettymaps

plot \= prettymaps.plot(
    'Barra da Tijuca',
    dilate \= 0,
    figsize \= (22,10),
    preset \= 'tijuca',
    adjust\_aspect\_ratio \= False
)

Use prettymaps.create\_preset() to create a preset:

import prettymaps

prettymaps.create\_preset(
    "my-preset",
    layers \= {
        "building": {
            "tags": {
                "building": True,
                "leisure": \[
                    "track",
                    "pitch"
                \]
            }
        },
        "streets": {
            "width": {
                "trunk": 6,
                "primary": 6,
                "secondary": 5,
                "tertiary": 4,
                "residential": 3.5,
                "pedestrian": 3,
                "footway": 3,
                "path": 3
            }
        },
    },
    style \= {
        "perimeter": {
            "fill": False,
            "lw": 0,
            "zorder": 0
        },
        "streets": {
            "fc": "#F1E6D0",
            "ec": "#2F3737",
            "lw": 1.5,
            "zorder": 3
        },
        "building": {
            "palette": \[
                "#fff"
            \],
            "ec": "#2F3737",
            "lw": 1,
            "zorder": 4
        }
    }
)

prettymaps.preset('my-preset')

```
Preset(params={'layers': {'building': {'tags': {'building': True, 'leisure': ['track', 'pitch']}}, 'streets': {'width': {'trunk': 6, 'primary': 6, 'secondary': 5, 'tertiary': 4, 'residential': 3.5, 'pedestrian': 3, 'footway': 3, 'path': 3}}}, 'style': {'perimeter': {'fill': False, 'lw': 0, 'zorder': 0}, 'streets': {'fc': '#F1E6D0', 'ec': '#2F3737', 'lw': 1.5, 'zorder': 3}, 'building': {'palette': ['#fff'], 'ec': '#2F3737', 'lw': 1, 'zorder': 4}}, 'circle': None, 'radius': None, 'dilate': None})
```

Use **prettymaps.multiplot** and **prettymaps.Subplot** to draw multiple regions on the same canvas

import prettymaps

\# Draw several regions on the same canvas
plot \= prettymaps.multiplot(
    prettymaps.Subplot(
        'Cidade Baixa, Porto Alegre',
        style\={'building': {'palette': \['#49392C', '#E1F2FE', '#98D2EB'\]}}
    ),
    prettymaps.Subplot(
        'Bom Fim, Porto Alegre',
        style\={'building': {'palette': \['#BA2D0B', '#D5F2E3', '#73BA9B', '#F79D5C'\]}}
    ),
    prettymaps.Subplot(
        'Farroupilha, Porto Alegre',
        layers \= {'building': {'tags': {'building': True}}},
        style\={'building': {'palette': \['#EEE4E1', '#E7D8C9', '#E6BEAE'\]}}
    ),
    \# Load a global preset
    preset\='cb-bf-f',
    \# Figure size
    figsize\=(12, 12)
)

Add hillshade
=============

plot \= prettymaps.plot(
    'Honolulu',
    radius \= 5500,
    figsize \= 'a4',
    layers \= {'hillshade': {
        'azdeg': 315,
        'altdeg': 45,
        'vert\_exag': 1,
        'dx': 1,
        'dy': 1,
        'alpha': 0.75,
    }},
)

```
The autoreload extension is already loaded. To reload it, use:
  %reload_ext autoreload
make: Entering directory '/home/marcelo/.cache/elevation/SRTM1'
make: Nothing to be done for 'download'.
make: Leaving directory '/home/marcelo/.cache/elevation/SRTM1'
make: Entering directory '/home/marcelo/.cache/elevation/SRTM1'
make: Nothing to be done for 'all'.
make: Leaving directory '/home/marcelo/.cache/elevation/SRTM1'
make: Entering directory '/home/marcelo/.cache/elevation/SRTM1'
cp SRTM1.vrt SRTM1.2d5b6f11e0e74b44a9386ba897fb0852.vrt
make: Leaving directory '/home/marcelo/.cache/elevation/SRTM1'
make: Entering directory '/home/marcelo/.cache/elevation/SRTM1'
gdal_translate -q -co TILED=YES -co COMPRESS=DEFLATE -co ZLEVEL=9 -co PREDICTOR=2 -projwin -157.90125854957773 21.364471426268267 -157.81006761682832 21.244615177105388 SRTM1.2d5b6f11e0e74b44a9386ba897fb0852.vrt /home/marcelo/Projects/Art/prettymaps/notebooks/elevationa.tif
rm -f SRTM1.2d5b6f11e0e74b44a9386ba897fb0852.vrt
make: Leaving directory '/home/marcelo/.cache/elevation/SRTM1'


WARNING:matplotlib.axes._base:Ignoring fixed y limits to fulfill fixed data aspect with adjustable data limits.
```

Add keypoints
=============

plot \= prettymaps.plot(
    'Garopaba',
    radius \= 5000,
    figsize \= 'a4',
    layers \= {'building': False},
    keypoints \= {
        \# Search for general keypoints specified by OSM tags
        'tags': {'natural': \['beach'\]},
        \# Or, search by specific name or free-text search
        \# pretymaps will use a fuzzy string matching to search for the specified name
        'specific': {
            'pedra branca': {'tags': {'natural': \['peak'\]}},
        }
    },
)
