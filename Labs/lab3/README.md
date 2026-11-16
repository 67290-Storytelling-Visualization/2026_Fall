# Lab 3 · ArcGIS and Integration in Observable Dashboard

**67-290 Storytelling with Data Visualization · CMU-Qatar · Monday 9 November 2026 · 90 minutes · 5 points**

This lab walks through signing on to ArcGIS online account and creating storytelling with maps. An optional section
at the end walks through publishing an ArcGIS web map and embedding it in a web page with HTML, the same way you can
embed it in an Observable dashboard.

> **No Canvas submission for this lab.** You submit your Exercise 1 map and your StoryMap by sharing them with our
> course group in ArcGIS Online. After you sign in to ArcGIS Online for the first time (see Start of class), we will add
> you to that group. If you miss the lab, please sign in once and let the TA know, so we can still add you after class.

## What you will make

By the end of this lab, you will have made these two products, which are also what you submit:

1. A map of earthquakes, volcanoes and tectonic plates around the Ring of Fire (Exercise 1):

   ![Earthquakes, volcanoes and tectonic plates around the Ring of Fire](images/ring-of-fire.png)

2. A StoryMap that tells the story of Dr. John Snow's 1854 London cholera map (Exercise 3). Open this example:
   [London Cholera - 1854](https://storymaps.arcgis.com/stories/0af1b66fc8e5438fb20ae3e8513605c0)

## Files in this folder

| File | Purpose |
|---|---|
| `README.md` | Full lab instructions (this page) |
| `images/` | Images used on this page |
| `arcgis-map.html` | Starter file for the optional embedding section (HTML embed) |

## Start of class: ArcGIS Account Access

Note: There is no need to download ArcGIS Pro desktop as the Heinz software site indicates. The Pro version will not
be used for our class. Rather, we will be using the ArcGIS Online product which requires no additional downloaded
software.

1. ESRI ArcGIS Software package access:

   https://www.heinz.cmu.edu/current-students/computing-services/software

   Or directly from

   https://carnegiemellon.maps.arcgis.com/home/index.html

   ![Sign in to Carnegie Mellon University](images/arcgis-signin.png)

2. Don't create a username and a password. Instead, click on "Carnegie Mellon University"
3. Sign in using your CMU credentials.
4. Once logged in, you should see the Carnegie Mellon University start page.

   ![Carnegie Mellon University start page](images/arcgis-start-page.jpg)

5. Click on the Map option at the top of the frame. A map showing Canada, the United States, Mexico and Central America
   should appear. If so, your account is good to go!
6. Stay signed in. We will now explore the product and do several practice exercises together. (After class, if you
   wish, feel free to experiment. There are tutorials online or you can view some recent student projects under the
   Gallery option.)

---

# ArcGIS Tutorial

### Exercise 1: Basic Earth Science: Earthquakes, Volcanoes and Tectonic Plates

In this exercise, we create maps that give us insight into some of our planet's natural seismic phenomena.

"An earthquake is a natural phenomenon characterized by the sudden shaking or trembling of the ground, caused by the
movement of tectonic plates beneath the Earth's surface. These movements can occur due to various factors, including
volcanic activity, the shifting of the Earths crust, or the release of stress accumulated along geological faults. The
energy released during an earthquake travels through the Earth in the form of seismic waves, which is what we feel as
shaking."

Earthquake magnitude is a measure of the size of an earthquake at its source. It is a logarithmic scale. For example,
the amplitude of seismic waves of a magnitude 5 earthquake is 10 times as large as a magnitude 4 earthquake. A magnitude
3 to 4.9 earthquake is considered minor; 5 to 6.9 is moderate to strong; 7 to 7.9 is major; and 8 or more is an
extremely powerful earthquake.

Earthquake intensity measures the strength of shaking and damage experienced at a specific location. The intensity of
an earthquake at a location is a number (I - XII) that characterizes the severity of ground shaking at that location by
considering the effects of the shaking on people, on built structures, and on the landscape.

**THE MAP**

From the home page of your CMU ArcGIS Online account, create a new map by clicking the Map option at the top. A base
map should appear, like this:

![A new, untitled map with the base map](images/new-map.png)

We next add various layers to visualize seismic activity.

Select the 'Add layer' option and, instead of 'My content', select 'Living Atlas'. In the Search box, enter
'Earthquakes'. A list of potential layers appears. Add the layer 'Recent Earthquakes' by ESRI to your map:

![Adding the Recent Earthquakes layer from Living Atlas](images/add-layer-living-atlas.png)

The layer appears on your map and the legend appears on the right of your work area. Note how the recent earthquakes
are color coded. You can collapse the Layers panel for a larger view of your map. Pan and Zoom around your map to see
where earthquakes occur globally. Click on a few for details.

Can you notice any patterns in the distribution of earthquakes? Of major earthquakes?

When you reach a convenient check point in your work, save your map (icon on the left; highlighted with a blue dot.)
Give your map a descriptive name and add some useful tags.

To add an additional layer, select either the Add option (plus sign) or Layers / Add. Again, select 'Living Atlas' and
search the term 'Volcano'. Add the layer 'Significant Global Volcanic Eruptions' to your map. Close the Layers pane and
note the legend on the right. Close that pane. Pan and Zoom around your map. If you open the Layers pane on the left you
can toggle each layer on and off or rearrange them.

Is there any apparent relationship between the locations of recent earthquakes and volcanic activity?

Add one more layer, this time from 'ArcGIS Online' rather than 'Living Atlas'. Search 'Tectonic' and add the layer
'Earth's Tectonic Plates' by ESRI Canada Education and Research. Hit the home button (lower right) to enlarge your map
to the default view. You can hide the Properties pane at the right and the Layers pane at the left. Save your map.

Pan and Zoom around your map. Do you see the 'Ring of Fire'? (Some of most densely populated countries and cities on
earth sit directly on the Ring of Fire. Name a few! Do you personally know any of these places?)

Finally, experiment with Base maps - the fourth icon in the left side panel. You will generally want to select base
maps that highlight the features you want to demonstrate in a useful and pleasing way. (Personally, I like 'Imagery
Hybrid' or 'National Geographic' for this application.)

With all three layers and the 'Imagery Hybrid' base map, your map should look something like this. The earthquakes
(circles) and volcanoes (triangles) trace the plate boundaries around the Pacific Ocean, from New Zealand and Indonesia
up through Japan and Alaska and down the west coast of the Americas: this horseshoe is the Ring of Fire.

![Earthquakes, volcanoes and tectonic plates around the Ring of Fire](images/ring-of-fire.png)

You can see that adding layers to a map is an easy task; interpreting the underlying story is the challenge!

When you are happy with your work, save your map. When you return to ArcGIS Online, you will find it under Content.

Next, share your map with our course group: this is the first part of your submission. Select the Share button in the
left side panel and set the sharing level to 'Organization':

![The Share window with the Organization sharing level](images/share-map.png)

Select 'Edit group sharing', tick our course group and select Apply. Then select Save in the Share window:

![Group sharing with the course group ticked](images/group-sharing.png)

When you are ready, we will try a filter function together.

### Exercise 2: The Famous London Cholera Map (1854)

![Death's Dispensary](images/deaths-dispensary.jpg)

Many people died in Europe during the deadly and recurring cholera epidemics. In times before modern bacteriology,
medicine, epidemiology and public health, there was great debate and misunderstanding about the causes and spread of
this disease.

In this exercise, we will re-create Dr. John Snow's famous 1854 map of the Soho region of London, one of the hardest hit
spots during this cholera epidemic. At the time of this epidemic (one of several in Europe and London) during the
1840's and 1850's, Dr. Snow had already become well known through his pioneering work in use of chloroform (having
helped deliver two of Queen Victoria's children) and his early work in what has become the field of epidemiology.

At the time, it was generally assumed, and accepted, that cholera was an airborne disease (miasma). Given the open
sewers in London (and elsewhere), the presence of livestock, the crowded conditions, and the general lack of proper
sanitation, there was plenty of reason to believe the miasma theory. Dr. John Snow, a resident of the area, thought
otherwise.

**Instructions:**

Sign into your ArcGIS Online Account: https://carnegiemellon.maps.arcgis.com/

Create a New Map (select Map from the top row of menu items).

Under Layers / Add / select 'ArcGIS Online' and enter cholera in the search box. Many results will be returned. To
narrow your search, you can use the 'owner' keyword. Add the clause owner:sappleton_Education to your search criteria.
Three layers should be returned: Snow's Cholera Map, Cholera Cases and Water Pumps, all authored by Sarah Appleton:

![The three cholera layers by Sarah Appleton in ArcGIS Online](images/add-layer-cholera.png)

Add the layers: "Cholera Cases", "Water Pumps", and "Snow's Cholera Map" layers.

(The '<' returns you to the layers pane). Reposition layers, if necessary, so that the Water Pumps layer is on the top
and Snow's Cholera Map is on the bottom.

Snow's Cholera Map layer shows the Soho neighborhood as it would have mapped in 1854. It is a digital, or 'raster'
image, and has been 'georectified' to match the base map's spatial grid. He used tick marks in his original map to
indicate the number of deaths at each location. Cholera Cases shows the addresses where cholera deaths occurred along
with the number recorded. Water Pumps shows the location of water pumps throughout the area. Click on any point to see
relevant data.

Zoom to the extent of John Snow's Map and create a bookmark (sixth option on the left hand command bar) called 'Soho
1854'. This will make your map easier to find in the future. Save your map with a descriptive name (disk icon on the
left with blue dot.).

Experiment turning your layers on and off individually. Clicking on '…' in the Water Pumps or the Cholera Cases layer
brings up some additional options. Show the table for each to see the underlying data.

Next, we will do some styling to better visualize the situation. Select Layers and highlight the Cholera Cases layer. It
should be highlighted in gray. We will style the cholera deaths so that the symbols are in proportion to the number of
deaths at each location. Select the styles option on the right hand command bar. Under 'Choose attributes' add the field
'Deaths' as the attribute to show. The style changes to 'Counts and Amounts' as circles. Click on 'Style options' and
adjust the 'Size range' so that the maximum size is 30 px. Experiment with different colors or sizes so the map is easy
to read and interpret. 'Done' when ready to go on. Save your map with a descriptive name and, optionally, with useful
tags.

Open the table for Cholera Cases ( ... Show table) and carefully examine the data. Note the attributes. Sort, in
descending order, by number of cases. What is the top address and how many deaths were there at this address? Select
the record (check the box) and note its location on the map. You can zoom to this location with the '… Zoom to
selection' option (header row of the table). Zoom back out (you can use your bookmark here!). Locate the next two most
deadly addresses and zoom in. Note that the rows you select will be faintly highlighted on your map.

Finally, style the Cholera Cases layer with a heat map and see if you can locate the epicenter of this outbreak of
cholera. Adjust the Area of influence so that your map is most illustrative. Save your map. Your map should look
something like this:

![The Cholera Cases heat map, the sorted table and the water pumps](images/cholera-heat-map.png)

What might you (or Dr. Snow) conclude? How would you interpret Dr. Snow's original map? Can you explain why certain parts
of the areas in question seemed less likely to be infected?

Experiment with controls or style options as you wish and save your map frequently when you reach a good checkpoint.
(There is no 'easy' undo control.)

### Exercise 3: The Famous London Cholera Map (1854) - StoryMap

![Death's Dispensary](images/deaths-dispensary.jpg)

Open the London Cholera map you have already created. It should depict three layers - Cholera Cases, Water Pumps and
Snow's Cholera Map. Refer back to the case study if needed.

Next, we create a simple StoryMap to tell the story of Dr. Snow's map. Note the 9 dots matrix at the top of your work
area. Select 'StoryMaps':

![The 9 dots app launcher with StoryMaps](images/app-launcher-storymaps.png)

A new tab should open into the StoryMap editor. In the upper right hand corner, select '+Create / Story' and you should
now be in the StoryMap editor. It is very simple to use and a great tool for telling your story.

Begin by giving your story a descriptive title, like 'London Cholera - 1854' or something interesting. In the short
introduction or summary box, enter a one sentence description, like "The story of Dr. John Snow's famous Cholera map".
Your work is automatically saved in draft form as you make your edits.

Find and download an image that creates an interesting impression of the cholera epidemic and record the source of the
image (which we will use later for attribution). This will become your cover image. When ready, select 'Add cover image
or video' and upload your image. You are well on the way!

At the top of the work area, select Design and select theme or browse through the 'Featured themes gallery' to find one
that is appropriate for this most grim story. Turn on 'Credits'.

Wherever you see a plus sign in green, can add content. At the first green plus sign (Tell your story), select Text, and
add paragraph or two explaining the situation. Some like (or copy this one): "Many people died in Europe during the
deadly and recurring cholera epidemics. In times before modern bacteriology, medicine, epidemiology and public health,
there was great debate and misunderstanding about the causes and spread of this disease."

Add text again and add a second paragraph, like this (or copy this one):

"At the time, it was generally assumed, and accepted, that cholera was an airborne disease (miasma). Given the open
sewers in London (and elsewhere), the presence of livestock, the crowded conditions, and the general lack of proper
sanitation, there was plenty of reason to believe the miasma theory. Dr. John Snow, a resident of the area, thought
otherwise."

Next, add your Cholera Map. Under the plus sign, select Map and add your Cholera map. If you have created other maps,
they will also show up here. When you have selected your map, you can decide which layers you want to appear. For
example, you could deselect the Cholera Cases layer and only show the original map and the pump locations. Do so and
add some basic text below the map to explain it, like this (or copy this one):

"This is Dr. Snow's original 1854 map of the Soho neighborhood, laid over a modern map of London. The tick marks show
the number of deaths at each address, and the 'P' pins mark the water pumps where people drew their water. Look closely:
the deaths are not spread evenly across the neighborhood."

Select the Preview option at the top of the map to preview your work at any time. Choose the small x at the bottom right
to return to the design/edit mode.

Next, add your Cholera map once again, but also select the Cholera Cases layer. This should show your heat map. Add some
descriptive text, like this (or copy this one):

"With the cholera cases shown as a heat map, the pattern becomes clear: the deaths cluster around a single water pump on
Broad Street (today's Broadwick Street). Dr. Snow concluded that cholera was spreading through the water from this pump,
not through the air, and he persuaded the local authorities to remove the pump's handle."

Note: If you make any changes to your original Cholera map in ArcGIS, these changes will be reflected in your StoryMap
the next time you load it.

Add a credit for the image you downloaded and any other content or finishing touches you would like to complete your
basic StoryMap.

When you are ready to share your StoryMap, select Publish and set the sharing level to 'Organization'. Under 'Set group
sharing', also search for our course group and add it: this is the second part of your submission.

![Publishing the StoryMap: sharing level and group sharing](images/publish-share.png)

If the builder asks to update the sharing of your map, accept, so that your map shows in the story.

---

# Submission

There is nothing to submit on Canvas for this lab. Your submission is your Earthquakes map (Exercise 1) and your London
Cholera StoryMap (Exercise 3), both shared with our course group in ArcGIS Online (see the end of each exercise).

If you don't see the course group when you share, you have not been added yet: let the TA know.

Full marks are for participating and finishing. If something broke and you could not fix it, let the TA know what you
tried.

---

# Optional · Using External Data

### Exercise 4 (optional): California Fires

This exercise is optional and not part of your submission. It shows how to use external data: a layer published on
ArcGIS Online by an outside agency, the California Department of Forestry and Fire Protection (CAL FIRE).

In this exercise, we create a map and a story map that illustrates the extent and dangers of recent California fires.

**THE MAP**

From the home page of your CMU ArcGIS Online account, create a new map by clicking the Map option at the top. A base
map should appear. We next add various layers to visualize the extent of major California fires.

Select the 'Add layer' option and, instead of 'My content', select 'ArcGIS Online'. In the Search box, enter
'California fires'. A list of potential layers appears. Add the layer 'California Historical Fire Perimeters' by
'California Department of ...' to your map. The layer appears on your map and the properties panel appears on the right
of your work area. Go ahead and close the properties panel.

Open the 'California Historical Fire Perimeters' layer. Note there are three layers contained within. We will examine
recent fires. Hide the 'California Fire Perimeters (1950+)' layer and show the 'Recent Large Fire Perimeters (GT 5000
acres)'. Save your map with a descriptive name and, optionally, some useful tags. Your map will be available in the
Content section of your account if you need to return to it.

Open the data table ( ... / Show table ). Can you identify the five largest fires, by name, since 2021? (Hint: Sort the
table on the 'GIS Calculated Acres') field. Many of these fires caused tremendous damage and loss of life. Select one of
the largest fires, zoom in on it, and do a quick bit of background research on it. Prepare a few facts about this fire
for your StoryMap.

When you are happy with your work, again save your map. When you return to ArcGIS Online, you will find it under
Content.

**THE STORYMAP**

Next, we create a StoryMap to illustrate your findings.

Under the 9-dot array at the top (next to your name), select StoryMaps. Under the Create option, select 'Story'. A blank
template shows up.

Enter a descriptive story title (for example, maybe something like 'The Quarry Fire of 2023', with, of course, the name
of your chosen fire.) Add a short introduction or subtitle.

Your work is constantly saved and will be available in the Content section of your account, and will be present as an
option when you return to the StoryMap builder.

Download a dramatic and relevant 'cover' image for your story map. Add it to your story map where it will
appear at the top.

Under 'Design' select a Cover design and a Theme. Use one of the default themes or pick one from the Featured Themes
gallery. Your theme should complement the story you intend to tell.

Wherever you see a plus sign in green, can add content of various types. At the first green plus sign (Tell your
story), select Text, and add a brief paragraph or two explaining the situation. If you highlight your text, various
formatting options appear.

Next, under the plus sign, select Map and add your California Fires map. If you have created other maps, they will also
show up here. When you have selected your map, you can decide which layers you want to appear. Add some basic text below
the map to explain it.

Select the Preview option at the top of the map to preview your work at any time. Choose the small x at the bottom right
to return to the design/edit mode.

Optionally, add any other text, images, or other media that help your audience understand the story you are telling.

Note: If you make any changes to your original Cal Fires map in ArcGIS, these changes will be reflected in your StoryMap
the next time you load it.

---

# Optional · Embedding an ArcGIS Map

This section is optional and not part of your submission. It shows how to embed your map from Exercise 1 in a web page
with HTML. You can use the same code to add an ArcGIS map to your final project dashboard.

Follow the steps below to find your map URL, then embed it in the starter file `arcgis-map.html`, which is in this
folder.

## Before You Begin: Get Your ArcGIS Map URL

Complete these steps first. You will need your **Web Map ID** before filling out the template.

### PRE-STEP 1 — Publish your map

- Find your map on **ArcGIS Online**
- Save the map, then share it publicly.

![Save and Share buttons in ArcGIS Online](images/save-and-share.png)

### PRE-STEP 2 — Copy your Web Map ID

- Open your published map in ArcGIS Online.
- Go to the Content tab
- Click on your map from Exercise 1
- Click on **Share** on the top right corner, below "Open in Field Maps Designer"

![Share button on the item page](images/content-item.png)

- Your Web Map ID is the value after ?id= in the URL

Example URL:

```
https://carnegiemellon.maps.arcgis.com/home/item.html?id=YOUR_WEBMAP_ID
```

> **Keep this ID handy** — you will paste it into the code below.

---

## Embed it: HTML file (`arcgis-map.html`)

Open `arcgis-map.html` and fill in each marked step.

### STEP 1 — Add the ArcGIS CSS

Inside `<head>`, paste:

```html
<link rel="stylesheet" href="https://js.arcgis.com/4.32/esri/themes/light/main.css" />
```

### STEP 2 — Set the map size

Still inside `<head>`, paste:

```html
<style>
  #viewDiv {
    width: 100%;
    height: 800px;
  }
</style>
```

### STEP 3 — Add the map container

Inside `<body>`, paste:

```html
<div id="viewDiv"></div>
```

### STEP 4 — Load the ArcGIS SDK

After the `<div>`, paste:

```html
<script src="https://js.arcgis.com/4.32/"></script>
```

### STEP 5 — Add the map logic

After the SDK script tag, paste. Replace `YOUR_WEBMAP_ID` with the ID you copied in Pre-Step 2.

```html
<script>
  require([
    "esri/WebMap",
    "esri/views/MapView"
  ], (WebMap, MapView) => {

    const webmap = new WebMap({
      portalItem: {
        id: "YOUR_WEBMAP_ID"
      }
    });

    const view = new MapView({
      container: "viewDiv",
      map: webmap
    });
  });
</script>
```

**Done.** Open the file in a browser to run it.

---

## Notes

- The web map must be shared publicly.
- Interactive features (pan, zoom, pop-ups) remain available when embedded.
- The web map ID is the `?id=` value in the ArcGIS item URL.
