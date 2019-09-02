---
title: Performing a Site Survey
---

Before a new node can be added to the NYC Mesh network, it must meet some minimum requirements. A *site survey* visit is intended to determine whether or not an installation attempt at the new node site will be successful. Performing a site survey before starting an installation can save precious time and energy by avoiding the need to carry equipment to the new node site or by uncovering hidden issues with the new node location before too much work is put into making the node operational.

A good site survey will provide an Install Team with the following:

* Annotated panorama photographs of the install site. See [Taking Panoarama Photos]({{< relref "panoramas" >}}) for details and [§ Determining LOS](#assess-los-to-an-existing-node).
* Advance warning of any physical hazards at the install site. See [Site Safety]({{< relref "safety" >}}) for details.
* A report on pre-existing radio spectrum emissions at the install site that may interfere with new node equipment. See [§ Wireless Site Survey](#perform-a-wireless-site-survey) for details.

## Before you travel

In many cases, you can expeditate the task of performing a site survey by gathering the information you need before you arrive on-site.

* Request panorama photos of the new node location from the new NYC Mesh member.
* Use the [NYC Mesh Line of Sight Web application](https://los.nycmesh.net/) to check for LOS to an existing node. (Note that this application has not been updated since 2014 and may not produce accurate results.)
* Request that the new NYC Mesh member provide you with any additional detail that they can. This may include but is not limited to:
    * Architectural blueprints of the building.
    * Photographs of possible indoor router's installation locations.
    * Video walkthrough detailing how to get to the roof or other install location.
    * Contact information for the new NYC Mesh member, and the contact information for a backup liaison in case they are unavailable.

## Assess physical access

1. Determine that you can access the roof (or window) where the CPE will be installed.
1. Document any physical hazards in the way to the install location.
1. Document a route for any cabling you will need (Ethernet, etc.) to run down from the roof or indoors.
    * Be certain to note the need for new cable passes or other modifications you will need to make to the building!

Unless you are the only installer, consider adding any pre-install documentation to the [NYC Mesh Docs Node Reference]({{< relref "nodes" >}}) so that other volunteers can pick up where you left off.

## Assess LOS to an existing node

Once you are safely at the spot where you expect to install the new node's outdoor router, antenna(s), and other equipment, you should double-check that you have direct line-of-sight (LOS) to an existing node. Without LOS, the new node location will not be able to physically connect to the rest of NYC Mesh's mesh network.

* If you were provided with panorama photos before your arrival, use them to orient yourself.
* Use binoculars or a hand-held telescope to help get a visual on the neighboring node's antenna.
* If necessary or useful, add supplemental annotations to the panorama photos that you have, or take new panorama photos to update the ones you were given. This is especially useful if the existing panorama photos are old; New York City changes rapidly with new construction happening constantly.

## Perform a Wireless Site Survey

Once you have verified LOS to an existing node, you should next conduct a survey of the new node location's RF (radio frequency) environment. Since outdoor routers work by transmitting and receiving radio waves (i.e., they are radio *transceivers*), any existing radio interference can potentially disrupt or degrade the performance of the new node. In the most severe cases, a new node may not be feasible even if it has direct line-of-sight to an existing node due to a very poor RF environment.

[Wikpedia maintains a list of wireless site survey applications](https://en.wikipedia.org/wiki/Comparison_of_wireless_site_survey_applications) you can use to conduct the RF survey.

## Report your conclusions

After you complete the site survey, share your conclusions with the rest of your NYC Mesh Install Team. Further, please consider dating and documenting your findings in our [Node Reference]({{< relref "nodes" >}}) to save future volunteers from duplicating your effort.
