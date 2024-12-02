---
project: prettymaps
stars: 11189
description: A small set of Python functions to draw pretty maps from OpenStreetMap data. Based on osmnx, matplotlib and shapely libraries.
url: https://github.com/marceloprates/prettymaps
---

\# Install prettymaps using pip:
#!pip install prettymaps

prettymaps
==========

A minimal Python library to draw customized maps from OpenStreetMap created using the osmnx, matplotlib, shapely and vsketch packages.

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

To enable plotter mode:

```
pip install git+https://github.com/abey79/vsketch@1.0.0
```

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

Tutorial
========

Plotting with prettymaps is very simple. Run:

prettymaps.plot(your\_query)

**your\_query** can be:

1.  An address (Example: "Porto Alegre"),
2.  Latitude / Longitude coordinates (Example: (-30.0324999, -51.2303767))
3.  A custom boundary in GeoDataFrame format

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

plotter

{'layers': {'perimeter': {}, 'streets': {'widt...

9

tijuca

{'layers': {'perimeter': {}, 'streets': {'widt...

To examine a specific preset, run:

import prettymaps

prettymaps.preset('default')

```
Preset(params={'layers': {'perimeter': {}, 'streets': {'width': {'motorway': 5, 'trunk': 5, 'primary': 4.5, 'secondary': 4, 'tertiary': 3.5, 'cycleway': 3.5, 'residential': 3, 'service': 2, 'unclassified': 2, 'pedestrian': 2, 'footway': 1}}, 'building': {'tags': {'building': True, 'landuse': 'construction'}}, 'water': {'tags': {'natural': ['water', 'bay']}}, 'forest': {'tags': {'landuse': 'forest'}}, 'green': {'tags': {'landuse': ['grass', 'orchard'], 'natural': ['island', 'wood'], 'leisure': 'park'}}, 'beach': {'tags': {'natural': 'beach'}}, 'parking': {'tags': {'amenity': 'parking', 'highway': 'pedestrian', 'man_made': 'pier'}}}, 'style': {'perimeter': {'fill': False, 'lw': 0, 'zorder': 0}, 'background': {'fc': '#F2F4CB', 'zorder': -1}, 'green': {'fc': '#8BB174', 'ec': '#2F3737', 'hatch_c': '#A7C497', 'hatch': 'ooo...', 'lw': 1, 'zorder': 1}, 'forest': {'fc': '#64B96A', 'ec': '#2F3737', 'lw': 1, 'zorder': 2}, 'water': {'fc': '#a8e1e6', 'ec': '#2F3737', 'hatch_c': '#9bc3d4', 'hatch': 'ooo...', 'lw': 1, 'zorder': 3}, 'beach': {'fc': '#FCE19C', 'ec': '#2F3737', 'hatch_c': '#d4d196', 'hatch': 'ooo...', 'lw': 1, 'zorder': 3}, 'parking': {'fc': '#F2F4CB', 'ec': '#2F3737', 'lw': 1, 'zorder': 3}, 'streets': {'fc': '#2F3737', 'ec': '#475657', 'alpha': 1, 'lw': 0, 'zorder': 4}, 'building': {'palette': ['#433633', '#FF5E5B'], 'ec': '#2F3737', 'lw': 0.5, 'zorder': 5}}, 'circle': None, 'radius': 500})
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

addr:housenumber

addr:street

amenity

operator

website

geometry

addr:postcode

name

office

opening\_hours

...

contact:phone

bus

public\_transport

source:name

government

ways

name:fr

type

building:part

architect

element\_type

osmid

node

2407915698

820

Rua Washington Luiz

NaN

NaN

NaN

POINT (-51.23212 -30.0367)

90010-460

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

way

126665330

387

Rua dos Andradas

place\_of\_worship

NaN

NaN

POLYGON ((-51.23518 -30.03275, -51.23512 -30.0...

90020-002

Igreja Nossa Senhora das Dores

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

126665331

1001

Rua dos Andradas

NaN

NaN

http://www.ruadapraiashopping.com.br

POLYGON ((-51.23167 -30.03066, -51.2316 -30.03...

90020-015

Rua da Praia Shopping

NaN

Mo-Fr 09:00-21:00; Sa 08:00-20:00

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

129176990

1020

Rua 7 de Setembro

NaN

NaN

http://www.memorial.rs.gov.br

POLYGON ((-51.23117 -30.02891, -51.2312 -30.02...

90010-191

Memorial do Rio Grande do Sul

NaN

Tu-Sa 10:00-18:00

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

129176991

NaN

Praça da Alfândega

NaN

NaN

http://www.margs.rs.gov.br

POLYGON ((-51.23153 -30.02914, -51.23156 -30.0...

90010-150

Museu de Arte do Rio Grande do Sul

NaN

Tu-Su 10:00-19:00

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

...

relation

6760281

NaN

NaN

NaN

NaN

NaN

POLYGON ((-51.23238 -30.03337, -51.23223 -30.0...

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

\[457506887, 457506886\]

NaN

multipolygon

NaN

NaN

6760282

NaN

NaN

NaN

NaN

NaN

POLYGON ((-51.23203 -30.0334, -51.23203 -30.03...

NaN

Atheneu Espírita Cruzeiro do Sul

NaN

NaN

...

NaN

NaN

NaN

NaN

NaN

\[457506875, 457506889, 457506888\]

NaN

multipolygon

NaN

NaN

6760283

NaN

NaN

NaN

NaN

NaN

POLYGON ((-51.23284 -30.03367, -51.23288 -30.0...

NaN

Palacete Chaves

NaN

NaN

...

NaN

NaN

NaN

NaN

NaN

\[457506897, 457506896\]

NaN

multipolygon

NaN

Theodor Wiederspahn

6760284

NaN

NaN

NaN

NaN

NaN

POLYGON ((-51.23499 -30.03412, -51.23498 -30.0...

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

\[457506910, 457506913\]

NaN

multipolygon

NaN

NaN

14393526

1044

Rua Siqueira Campos

NaN

NaN

https://www.sefaz.rs.gov.br

POLYGON ((-51.23125 -30.02813, -51.23128 -30.0...

NaN

Secretaria Estadual da Fazenda

NaN

NaN

...

NaN

NaN

NaN

NaN

NaN

\[236213286, 1081974882\]

NaN

multipolygon

NaN

NaN

2423 rows × 105 columns

Search a building by name and display it:

plot.geodataframes\['building'\]\[
        plot.geodataframes\['building'\].name \== 'Catedral Metropolitana Nossa Senhora Mãe de Deus'
\].geometry\[0\]

```
/home/marcelo/anaconda3/envs/prettymaps/lib/python3.11/site-packages/geopandas/geoseries.py:720: FutureWarning: Series.__getitem__ treating keys as positions is deprecated. In a future version, integer keys will always be treated as labels (consistent with DataFrame behavior). To access a value by position, use `ser.iloc[pos]`
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
    \# City name
    'Barra da Tijuca',
    dilate \= 0,
    figsize \= (22,10),
    preset \= 'tijuca',
)

import prettymaps

plot \= prettymaps.plot(
    'Stad van de Zon, Heerhugowaard, Netherlands',
    preset \= 'heerhugowaard',
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

Use prettymaps.delete\_preset() to delete presets:

\# Show presets before deletion
print('Before deletion:')
display(prettymaps.presets())
\# Delete 'my-preset'
prettymaps.delete\_preset('my-preset')
\# Show presets after deletion
print('After deletion:')
display(prettymaps.presets())

```
Before deletion:
```

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

```
After deletion:
```

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

plotter

{'layers': {'perimeter': {}, 'streets': {'widt...

9

tijuca

{'layers': {'perimeter': {}, 'streets': {'widt...

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
        style\={'building': {'palette': \['#EEE4E1', '#E7D8C9', '#E6BEAE'\]}}
    ),
    \# Load a global preset
    preset\='cb-bf-f',
    \# Figure size
    figsize\=(12, 12)
)

```
<Figure size 3600x3600 with 0 Axes>



<Figure size 3600x3600 with 0 Axes>



<Figure size 3600x3600 with 0 Axes>
```
