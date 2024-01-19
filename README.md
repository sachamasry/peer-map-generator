# Peer Map Generator

Generate [Mermaid](https://mermaid.js.org/) flowchart-based diagrams from data
defined in spreadsheets.

## Overview

Contextual safeguarding practitioners have incomplete data on teenagers at risk
of harm. Through working with numerous external agencies, data on individuals is
collected and combined. By making this data visual, certain patterns—of gang
violence, exploitation, trafficking and slavery, amongst other risks—can become
apparent and actionable. 

This generator ingests carefully-formatted spreadsheets, creating
[Mermaid](https://mermaid.js.org/) flowchart-based peer maps.

## Detailed description

Peer mapping is used as a visual tool, helping to support—and itentify those
needing support—young people affected by _extra-familiar harm_ (Peace et al.,
2022). While it's straightforward to simply build a diagram directly in a
diagramming program, it can be slow and error-prone to copy and paste the names,
ages and often involved actions of all the individuals involved. Instead, as
much of this data already exists in spreadsheets, it is easier and less
error-prone to create a _good-enough_ diagram from that data, as a feedback and
prototyping first step. This diagram provides a quick visualisation of the data,
so that practitioners can check that all information is complete at this stage.

Mermaid is used as a tool in this process, as it opens up the functionality to
programmatically take in data to be presented, and, using sophisticated algorithms,
automatically lay out that data. Usually, this data is complex and Mermaid is
unable to lay out diagrams in a way that helps practitioners infer patterns,
which is a job for the next step.

With the automatically generated diagram, this tool-a simple web app-also
exposes the code defining the diagram, which can then be imported into a
dedicated diagramming software. By importing this code into software such as
[Draw.io](https://www.drawio.com/), the practitioner can aesthetically format
the automatic first diagram with the agency's preferred colour scheme,
established use of symbols, shapes and relationships, into an informative and
presentable diagram. At this stage it is laid out in just such a way to make it
easier to recognise relevant patterns, quickly identifying teenagers most at
risk, in need of intervention.

The ingestion, conversion and Mermaid diagram code generation is done inside
this Livebook. Click on the button below to import the Livebook to your local
instance, to read detailed documentation, inspect and run the code and generate
diagrams.

[![Run in Livebook](https://livebook.dev/badge/v1/pink.svg)](https://livebook.dev/run?url=https%3A%2F%2Fgithub.com%2Fsachamasry%2Fpeer-map-generator%2Fblob%2Fmain%2FPeer-map-generator.livemd)

The process is summarised in the following figure, describing all the steps.

![Figure 1: Peer map creation process](./assets/peer-map-process-flowchart-light.png "Figure 1: Peer map creation process")

## Features

* _Reduces errors_ Quickly create simple peer map diagrams, reducing tedious
  copying and pasting of data into diagram software
* _Quick process_ Makes the process of creating the initial diagram, checking
  the result, and tweaking the data, very quick and simple
* _Very easy to use_ Data is entered in a spreadsheet, the diagram is created
  in a super-simple application directly in your browser
* _Makes sophisticated diagrams possible_ Provides diagram definition code, to
  import into Draw.io diagramming software, or further into Lucidchart
* _Offline and private use guaranteed_ The software runs locally on your own
  computer; you can complete your finished diagram locally as well in Draw.io,
  no data is sent to the cloud or off your computer, so data remains private and
  confidential

## Setup & Installation

Install [Livebook](https://livebook.dev/#install) on your computer. Livebook
has a few dependencies, all of which will be downloaded and installed
automatically for you.

Once installed, open the Livebook application, this will automatically open your
default browser, opening a new tab into Livebook.

## Usage & Details

NOTE: This section assumes abilities in installation and system administration.
Practitioners are advised to contact the developer for installation and initial
configuration of the software.

The quickest and easiest way to get started is to click the button below, which
will import the peer-map generating Livebook to your computer.

[![Run in Livebook](https://livebook.dev/badge/v1/pink.svg)](https://livebook.dev/run?url=https%3A%2F%2Fgithub.com%2Fsachamasry%2Fpeer-map-generator%2Fblob%2Fmain%2FPeer-map-generator.livemd)

After clicking, you will be asked to confirm, simply click the "Run notebook"
button on the next screen. If prompted by a pop-up screen, click the "Open
Livebook" button, and you will be dropped into the Livebook, with its default
documentation and code.

-------------------------------------------------------------------------------

Alternatively, to make sure you have all the files, including this README and the
template spreadsheet, it is better to download, or clone this entire repository
to your computer.

Doing this also ensures that all the data stays on your computer, and doesn't
interact with the cloud in any way. Also, to prevent data upload, we recommend
that you install the Draw.io desktop application, otherwise it would have to be
run in the cloud.

Once the repository is on your computer and you have Livebook installed and
running in your browser, from the Livebook application's main screen, click the
"Open" button, browse to the repository, select the `Peer-map-generator.livemd`
file and click the "Open" button. You will be in the peer map Livebook, just as
in the above description.

-------------------------------------------------------------------------------

With the peer map Livebook file open, the first section you will see is the
preamble code, such as the example code block below. The code you see on your
screen may be slightly different from the example.

``` elixir
Mix.install([
  {:kino, "~> 0.11.2"},
  {:faker, "~> 0.17.0"},
  {:kino_vega_lite, "~> 0.1.10"},
  {:xlsx_reader, "~> 0.7.0"}
])
```

Above this code block is a button labelled "Setup". Click it, as this will
download all dependent libraries needed to generate peer maps. This may take a
few minutes. Once it's done and ready, you will see a green dot in the lower
right corner, with the word "Evaluated" next to it, and a new system-generated
message below simply saying `:ok`.

The system has now been installed and is nearly ready for use. All that remains
is to run it as a web application. To do that, find and click the "App settings"
icon in the left-hand sidebar (it looks like a rocket-ship!), and click the
"Deploy" button.

Once the web app is deployed and ready for use, you will see a new section
appear, "Running Sessions", with a new session that has a green dot next to it,
signifying readiness. Underneath the green dot is a chain-link icon. Click this
and it will take you to the peer mapping generator.

-------------------------------------------------------------------------------

Near the top of the page, there is a section labelled: "Please select your input
spreadsheet". Click the section below and browse to your spreadsheet, with the
data already input.

Alternatively, you can drag the file directly onto this section, for the same
result.

As soon as the file is recognised, a new _Play_ button will come up in the
lower-right corner. Click it to generate the diagram from your spreadsheet.

If all went well, you will quickly have a diagram generated and displayed on the
page. Check that it has all the data presented on it, changing it as necessary
in the original spreadsheet, browsing to the file again and re-running the
diagram generation step, as necessary.

-------------------------------------------------------------------------------

Just below the diagram, you will see a code block that defines the diagram. Copy
this whole block precisely and open the Draw.io software on your desktop.

When prompted, click on "Create new diagram", to start a new diagram, selecting
"Blank diagram" when asked. Click "Create".

With a blank diagram on the screen, all that remains is to import the Mermaid
diagram from the previous step; in the toolbar, click on the "+" icon, the
"Advanced" men choice, "Mermaid" option.

A new window pops up, with sample diagram code in the text box. Highlight this
sample code and delete it, then paste the code you already copied from the peer
map generator in a previous step.

Finally, click "Insert"

You now have an identical copy of the previous diagram, this time ready for you
to lay out in a visually informative way, styling it to your needs.


## References

* Peace, D., Notarianni, M., & Latimer, K. (2022). Peer mapping case studies and examples. University of Bedfordshire. https://www.contextualsafeguarding.org.uk/media/cbwawfmj/peer-mapping-examples.pdf
* Osinde, D. (2022). Reflections on using the peer assessment tool in child and family assessments. London Borough of Barking & Dagenham. https://www.contextualsafeguarding.org.uk/media/ir0hqxhy/5g-practitioner-perspectives-level-1.pdf

