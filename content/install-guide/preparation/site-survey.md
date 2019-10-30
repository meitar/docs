---
title: Performing a Site Survey
---

Before a new node can be added to the NYC Mesh network, it must meet some minimum requirements. A *site survey* visit is intended to determine whether or not an installation attempt at the new node site will be successful. Performing a site survey before starting an installation can save precious time and energy by avoiding the need to carry equipment to the new node site or by uncovering hidden issues with the new node location before too much work is put into making the node operational.

A good site survey will provide an Install Team with the following:

* Annotated panorama photographs of the install site. See [Taking Panoarama Photos]({{< relref "panoramas" >}}) for details.
* Advance warning of any physical hazards at the install site. See [Site Safety]({{< relref "safety" >}}) for details.
* A report on pre-existing radio spectrum emissions at the install site that may interfere with new node equipment.

## Page Contents

1. [Before you travel](#before-you-travel)
    1. [Request detailed information from the new node owner](#request-detailed-information-from-the-new-node-owner)
    1. [Estimate line-of-sight to an existing node](#estimate-line-of-sight-to-an-existing-node)
        1. [NYC Mesh LOS Web App](#nyc-mesh-los-web-app)
        1. [Google Earth with NYC Mesh KML data file](#google-earth-with-nyc-mesh-kml-data-file)
    1. [Estimate radio link signal strength](#estimate-radio-link-signal-strength)
1. [On-site](#on-site)
    1. [Assess physical access](#assess-physical-access)
    1. [Visually confirm LOS to an existing node](#visually-confirm-los-to-an-existing-node)
    1. [Perform a Wireless Site Survey](#perform-a-wireless-site-survey)
1. [Report your conclusions](#report-your-conclusions)

## Before you travel

In many cases, you can expedite the task of performing a site survey by gathering additional information about the new node's location and characteristics before you arrive on-site.

### Request detailed information from the new node owner

It is often the case that simply asking for detailed information will provide you with plenty of helpful advice that could prove useful during the new node installation procedure. At a minimum, consider asking the new node owner for the following pieces of information before visiting the new node owner at their install location:

* Request [panorama photos]({{< relref "panoramas" >}}) of the new node location from the new NYC Mesh member.
* Request that the new NYC Mesh member provide you with any additional detail that they can. This may include but is not limited to:
    * Architectural blueprints of the building.
    * Photographs of possible indoor router's installation locations.
    * Video walkthrough detailing how to get to the roof or other install location.
    * Contact information for the new NYC Mesh member, and the contact information for a backup liaison in case they are unavailable.

### Estimate line-of-sight to an existing node

Unless the new node location has a direct line-of-sight (LOS) to an existing node, the installation cannot proceed. Acquiring hi-res [panorama photographs]({{< relref "panoramas" >}}) of the new node location will often help you determine whether or not the new node will be able to see an existing node and is the recommended method of doing so. However, even without panorama photos, there are numerous tools available to you to assess the potential for LOS from a given location to an existing NYC Mesh node.

#### NYC Mesh LOS Web App

One way to estimate whether the new node will have LOS to an existing node is to use the [NYC Mesh Line of Sight Web application](https://los.nycmesh.net/), but please note that this application has not been updated in many years and does not seem to consider elevation data, so it may not produce accurate results. It's a handy tool, but don't be immediately discouraged if the app tells you that your location cannot connect to the mesh.

To use this application, enter the postal address of the new node's building and press the *Check* button. The application will provide a report of nearby locations and whether they are likely to be within radio range of an existing NYC Mesh node.

The [source code for the NYC Mesh LOS Web App is available on GitHub](https://github.com/nycmeshnet/line-of-sight).

#### Google Earth with NYC Mesh KML data file

Another way to estimate LOS for a new node is to make use of [Google Earth](https://en.wikipedia.org/wiki/Google_Earth). NYC Mesh maintains a database of node information (as a Google Spreadsheet) along with [a small, open source Google Apps Script codebase](https://github.com/nycmeshnet/apps-script) for retrieving this node information in the format of a [Keyhole Markup Language (KML)](https://en.wikipedia.org/wiki/Keyhole_Markup_Language) file. The KML file can then be imported to Google Earth in order to map the location of each NYC Mesh node overlayed atop Google Earth data. A video demonstration of the process is provided next, followed by terse step-by-step instructions in textual form:

<video controls="controls"
    title="How to import NYC Mesh node data in KML to Google Earth"
    src="/video/nycmesh-google-earth-kml-howto.m4v"
    width="100%"
/>

1. Log in to your Google Account.
1. Load [the NYC Mesh KML file (`nycmesh.kml`) hosted on Google Drive](https://drive.google.com/file/d/0B6UiR4opmB4JU29VWVVNRmpva2M/view) in your Web browser.
1. Click the "Add to Drive" button to add the file to your personal Google Drive.
1. In a new tab, launch [Google Earth](https://earth.google.com/) in your Web browser.
1. Click the "My Places" button in the Google Earth sidebar.
1. You may need to [enable the (experimental) KML import feature](https://support.google.com/earth/answer/7365595).
1. Choose *Import KML File* &rarr; *Open from Google Drive…* and select the `nycmesh.kml` file you added earlier.
1. Wait a few moments for the KML data to be generated, downloaded to your Web browser, and loaded into Google Earth.

The KML file itself uses a [KML network link](https://developers.google.com/kml/documentation/kml_tut#network-links) that refers to the NYC Mesh Apps Script HTTP endpoint in order to ensure that each use is always up to date. This means each time you load this KML file into a KML viewer (such as Google Earth), you will be loading the most up-to-date copy of the NYC Mesh node database.

### Estimate radio link signal strength

Once you have a rough estimate of whether the new node will have LOS, the next step is to estimate whether or not the new node location will be able to establish a radio link with an existing node that is strong enough to supply connectivity to the new node.

* Load the [NYC Mesh node map](https://www.nycmesh.net/map) to view basic radio coverage estimates for the new node location. ([Source code for the NYC Mesh node map is available on GitHub](https://github.com/nycmeshnet/node-map).)
* If your prior LOS research revealed that a nearby existing node uses a Ubiquiti-branded outdoor router, consider using the [Ubiquiti airLink™ Web site](https://link.ui.com/) to more precisely simulate an RF environment to estimate connectivity levels.

## On-site

Having accomplished as much as possible during your site survey pre-planning, the next step is to physically visit the new node location for an on-site survey visit. Be sure to coordinate the timing of this visit with the new node owner so that they know to expect you and can let you in to their property. Also be certain to review the [NYC Mesh Install Team Etiquette Guide]({{< relref "etiquette" >}}) before you communicate with the new NYC Mesh member.

### Assess physical access

1. Determine that you can access the roof (or window) where the CPE will be installed.
1. Document any physical hazards in the way to the install location.
    * Especially for large buildings, take photographs at each step in your route from the entrance to the install location as you go through the building.
1. Document a route for any cabling you will need (Ethernet, etc.) to run down from the roof or indoors.
    * In some buildings, existing ethernet, coaxial, or even fiber cabling may have been abandoned by a previous installation effort and can be repurposed for use by NYC Mesh. If so, identifying these cable runs can save a huge amount of time and money.
    * Be certain to note the need for new cable passes or other modifications you may need to make to the building!
    * Large buildings often require a cable to be run from the roof to the location of a centralized telecom equipment closet, often in the basement. In these cases, try to identify existing conduits that can be used as cable drops. Unless the building itself owns the conduits, NYC Mesh is not permitted to make use of existing Internet Service Provider (ISP) conduits in the building.
    * In many building hallways, there are dedicated conduits where the wall meets the ceiling, called a raceway. If these raceways are owned by the building managers and are available for our use, they are a good choice for cable passes into apartments and general cable runs from one side of a building to another.

Unless you are the only installer, consider adding any pre-install documentation to the [NYC Mesh Docs Node Reference]({{< relref "nodes" >}}) so that other volunteers can pick up where you left off.

### Visually confirm LOS to an existing node

Once you are safely at the spot where you expect to install the new node's outdoor router, antenna(s), and other equipment, you should double-check that you have direct line-of-sight (LOS) to an existing node. Without LOS, the new node location will not be able to physically connect to the rest of NYC Mesh's mesh network.

* If you were provided with panorama photos before your arrival, use them to orient yourself.
* Use binoculars or a hand-held telescope to help get a visual on the neighboring node's antenna.
* If necessary or useful, add supplemental annotations to the panorama photos that you have, or take new panorama photos to update the ones you were given. This is especially useful if the existing panorama photos are old; New York City changes rapidly with new construction happening constantly.

### Perform a Wireless Site Survey

Once you have verified LOS to an existing node, you should next conduct a survey of the new node location's RF (radio frequency) environment. Since outdoor routers work by transmitting and receiving radio waves (i.e., they are radio *transceivers*), any existing radio interference can potentially disrupt or degrade the performance of the new node. In the most severe cases, a new node may not be feasible even if it has direct line-of-sight to an existing node due to a very poor RF environment.

[Wikpedia maintains a list of wireless site survey applications](https://en.wikipedia.org/wiki/Comparison_of_wireless_site_survey_applications) you can use to conduct the RF survey.

As part of the wireless site survey, attempt a connection to the hub or hubs the new node owner is planning to connect to and perform a bandwidth test to these existing nodes. Even if the RF environment is suitable for the new node in theory, in practice it is the achievable bandwidth to the existing nodes that really matters at the end of the day.

## Report your conclusions

After you complete the site survey, share your conclusions with the rest of your NYC Mesh Install Team. Currently, this often takes the form of a shared Google Doc. Further, please consider dating and documenting your findings in our [Node Reference]({{< relref "nodes" >}}) to save future volunteers from duplicating your effort.
