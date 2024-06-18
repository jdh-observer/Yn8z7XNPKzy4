---
jupyter:
  jupytext:
    text_representation:
      extension: .md
      format_name: markdown
      format_version: '1.3'
      jupytext_version: 1.14.4
  kernelspec:
    display_name: Python 3 (ipykernel)
    language: python
    name: python3
---

<!-- #region citation-manager={"citations": {"": []}} tags=["title"] -->
# Super-Vision: Tracing EPFL History Through 8,000 Doctoral Theses
<!-- #endregion -->

<!-- #region tags=["contributor"] -->
### Dario Rodighiero [![orcid](https://orcid.org/sites/default/files/images/orcid_16x16.png)](https://orcid.org/0000-0002-1405-7062)
University of Groningen
<!-- #endregion -->

<!-- #region tags=["contributor"] -->
### Sarah Kenderdine [![orcid](https://orcid.org/sites/default/files/images/orcid_16x16.png)](https://orcid.org/0000-0002-7190-9946)
École polytechnique fédérale de Lausanne
<!-- #endregion -->

<!-- #region tags=["contributor"] -->
### Philippe Rivière
Visionscarto
<!-- #endregion -->

<!-- #region tags=["copyright"] -->
[![cc-by](https://licensebuttons.net/l/by/4.0/88x31.png)](https://creativecommons.org/licenses/by/4.0/)
© Dario Rodighiero - Sarah Kenderdine - Philippe Rivière. Published by De Gruyter in cooperation with the University of Luxembourg Centre for Contemporary and Digital History. This is an Open Access article distributed under the terms of the [Creative Commons Attribution License CC-BY](https://creativecommons.org/licenses/by/4.0/)

<!-- #endregion -->

<!-- #region tags=["keywords"] -->
dimensionality reduction, information design, knowledge design, network visualization, natural language processing, timeline
<!-- #endregion -->

<!-- #region tags=["abstract"] -->
The fiftieth anniversary of EPFL (*École Polytechnique Fédérale de Lausanne*) offered the opportunity to retrace its history through the digital archives housed by the institute itself. Part of the exhibition Infinity Room 2, the Super-Vision project investigates the practice of academic advising by visualizing 8,000 doctoral theses in a work at the intersection of art, science, and technology.

Inaugurated in September 2019 at EPFL Pavilions, Super-Vision presents a diachronic mapping that uses artificial intelligence to shed light on an institutional dataset that would be unobservable otherwise. To achieve such a goal, 8,000 doctoral theses are analysed with natural language processing and mapped with techniques of dimensionality reduction, combining language and time within in an interactive visualization accessible to the public.

The project title has a twofold meaning: on the one hand, it refers to the educational practice that connects doctoral students to supervisors; on the other hand, it employs information design like a macroscope to grasp complex phenomena from a distant standpoint. The result offers EPFL employees and museum visitors an original perspective to look at the institute with different eyes.
<!-- #endregion -->

## Introduction


The Swiss Federal Institute of Technology in Lausanne (*École Polytechnique Fédérale de Lausanne, or most commonly EPFL*) is a young university that celebrated its fiftieth anniversary in 2019 (<cite data-cite="1465847/9H3MJEZ9"></cite>). For this occasion, the EPFL campus hosted celebrations and events, including a special exhibition to chronicle its history via digital archives, organized by the director of the Laboratory of Experimental Museology Plus, Prof. Sarah Kenderdine. The Infinity Room 2 exhibition was inaugurated in September 2019 at the EPFL Pavilions, the wooden museum designed by the acclaimed architect Kengo Kuma.



Like organizations transitioning towards digital technology, EPFL puts into operation different information systems collecting and storing some aspects of local culture and academic activity. Among them, one of the most known offers support to the Montreux Jazz Festival, a renowned music event preserving high-quality audiovisual material from the 60s (<cite data-cite="1465847/AA6M2NSK"></cite>). Despite the popularity of this example, it is essential to bear in mind that every single archive takes a unique perspective on the institution, which can be revealed through recent techniques of storytelling (<cite data-cite="1465847/M52FM8TP"></cite>).



This article investigates the art of storytelling for academic digital archives. Since the advent of information systems, the wide-ranging practice of researchers, teachers, and professors (<cite data-cite="1465847/WBHF5924"></cite>) has been increasingly collected, stored, and shared for administrative purposes in a progressive process of datafication (<cite data-cite="1465847/W2YTXL4I"></cite>). As a part of the Infinity Room 2 exhibition, the Super-Vision project aims to shed light on the academic practice of academic advising, defined as these “situations in which an institutional representative gives insight or direction to a college student about an academic, social or personal matter” (<cite data-cite="1465847/VIKANIT7"></cite>). Specifically, the project narrows down to a particular type of advising that concerns graduates who aspire to an academic career. On the occasion of the fifty anniversary, Super-Vision retraces EPFL’s footsteps by visualizing the records of doctoral theses to offer museum visitors an overview of the journey the institute made to take first place in the academic ranking of young universities (<cite data-cite="1465847/P884VVVY"></cite>).


```python tags=["figure-exhibition-*"]
from IPython.display import Image
metadata={
    "jdh": {
        "module": "object",
        "object": {
            "type":"image",
            "source": [
                "The poster was created for the Infinity Room 2 exhibition, which took place between September 2019 and February 2020 at EPFL Pavilions, at the core of the polytechnic campus. Patrick Donaldson, in the role of exhibition designer, not only curated the poster layout but assured the consistency of visual communication, with a specific attention to the digital installations."
            ]
        }
    }
}
display(Image("media/exhibition.jpg"), metadata=metadata)
```

## Exhibiting Science in the Making


Before illustrating the design process, this section introduces the reader to the interdisciplinary context, which situates the Super-Vision project at the convergence among Experimental Museology, Science, and Technology Studies (STS) and Information Design, foregrounding the transition of museum space to digital and visual literacy (<cite data-cite="1465847/ATL2EKB3"></cite>).


The Infinity Room 2 exhibition was conceived at a time when cultural institutions are establishing cross-disciplinary collaborations under the acronym of GLAM, which stands for “galleries, libraries, archives, and museums” (<cite data-cite="1465847/WDKJBS8Q"></cite>). Empowered by digital technology, this initiative increasingly invests time and energy in digitalization, preservation, and visualization of archives and collections (Cameron and Kenderdine 2007). In this context, Super-Vision takes shape as a work of experimental museology situated at the intersection between STS (<cite data-cite="1465847/NHVMTI4P"></cite>) and the mapping of science (<cite data-cite="1465847/78VK4BTC"></cite>). These two apparently distant disciplines find common ground in understanding the making of science, referring to the ongoing and ever-evolving process of scientific discovery (<cite data-cite="1465847/33Z8KKDL"></cite>). While STS reinterprets museums like observatories from which visitors can understand the scientific output, science-mapping scholars use information design to extract organizational patterns from laboratories and scientific communities.


With respect to the practice of supervision, it can be said that STS is interested in looking at doctoral theses as a sociotechnical object in the academic environment. On the other hand, the science-mapping perspective is more attracted by the techniques of mapping to reveal scientific organization. With a digital installation in the public setting of the campus, the Super-Vision project not only enhances the vision capacity of the broader public on the making of science (<cite data-cite="1465847/SQTGR64H"></cite>) but also reveals the hidden organizational structure, reinforcing the imperative for public institutions to be open and accountable (<cite data-cite="1465847/AR3RZZPW"></cite>).


Such a convergence finds its origins in STS, which has always been interested in the many aspects of science from historical, cultural, and social perspectives. In 1986, Bruno Latour and Steve Woolgar published a groundbreaking book titled Laboratory Life (<cite data-cite="1465847/6WPDHMEA"></cite>). This publication disclosed for the first time the hidden process of science-making by observing scientists in the offices of the Salk Institute for Biological Studies. This unusual perspective drastically changed the public perception of science, which was previously based on publications, conferences, and awards only. Latour and Woolgar looked at scientists in their working environment, like animals were studied in their natural habitat by biologists. As pointed out in the book’s preface by the institute’s founder Jonas Salk, although scientists felt uncomfortable being observed, the study provided valuable information to understand the scientific practice. The investigation of Latour and Woolgar introduced an innovative way to look at science, contributing to develop the concept of “science in the making,” which aims to disclose science through social and technological relationships (<cite data-cite="1465847/33Z8KKDL"></cite>).


A few years later, in 1999, when curators Barbara Vanderlinden and Hans Ulrich Obrist curated an exhibition at the Fotomuseum Antwerpen, probably no one expected such a fruitful collaboration between STS and museology (<cite data-cite="1465847/N7CMP8L6"></cite>). The Laboratorium exhibition prompted questions related to the perception of science, investigating “the gap between the specialized vocabulary of science, art, and the general interest of the audience” by using the museum gallery as a laboratory for experiments (<cite data-cite="1465847/8I2BZDGH"></cite>). In the exhibition, the process of science in the making was presented to a broader audience by bringing the scientific practice into museums for public consumption. At that time, Bruno Latour and Peter Galison were put in touch with Caroline Jones and Peter Weibel, generating a spark that led to four exhibitions organized at ZKM, the *Zentrum für Kunst und Medien* (<cite data-cite="1465847/48GNWLP6"></cite><cite data-cite="1465847/28L9HNE5"></cite><cite data-cite="1465847/JA6EHWUC"></cite><cite data-cite="1465847/ABNINJEW"></cite>) — as recently described by Giulia Bini (<cite data-cite="1465847/EN8JQYU2"></cite>). This encounter between academics and curators represents a landmark in the collaboration between science and museums, giving fresh perspectives on how museums can establish a dialogue with visitors on scientific matters.


Simultaneously, as mentioned in the book Museum Object Lessons for the Digital Age, “old museum collections and new technologies c[a]me together, tracing the translation and extension of collections […] into digital websites, imaging platforms and collection management systems'” (<cite data-cite="1465847/DEILFR79"></cite>). Cultural institutions have digitalized and published their collections online (<cite data-cite="1465847/399NSLGL"></cite>)  and the exhibition space has been populated by digital devices (<cite data-cite="1465847/TKWTMKVY"></cite><cite data-cite="1465847/6NGZH9MV"></cite>). Along with digital devices, data visualizations also entered exhibitions (<cite data-cite="1465847/5X6UFN5W"></cite>). As early as 2008, Paola Antonelli featured data visualizations in the exhibition Design and the Elastic Mind (<cite data-cite="1465847/8RCLYZDN"></cite><cite data-cite="1465847/DACRJUQ5"></cite>) and included some of them in the MoMA permanent collection (<cite data-cite="1465847/D4SZGM6B"></cite><cite data-cite="1465847/PKI67WG3"></cite>). Since then, cultural institutions have increasingly embraced data-driven objects as centerpieces in their exhibitions.


```python tags=["figure-zkm-*"]
from IPython.display import Image
metadata={
    "jdh": {
        "module": "object",
        "object": {
            "type":"image",
            "source": [
                "Part of the AIME team in the book section of Reset Modernity!, one of the exhibitions organized by Bruno Latour and Peter Weibel at ZKM in Karlsruhe. Below from left to right: Martin Guinard-Terrin, Bruno Latour, Emmanuelle Duwez, and Mirella Pantano; Above from left to right: Dario Rodighiero, Christophe Leclercq, Donato Ricci, and Daniele Guido."
            ]
        }
    }
}
display(Image("media/zkm.jpg"), metadata=metadata)
```

## Data Investigation and Analysis



The initial idea was to design a visualization capable of representing the EPFL community through scientific literature, drawing on the experience of the Affinity Map project (<cite data-cite="1465847/CXZ3G9EL"></cite>). One of the most interesting outcomes of this project was to represent the scientific community in a more democratic way, preferring a more-equitable metric of linguistic similarity to a quantitative analysis that foregrounds the most cited scholars (<cite data-cite="1465847/EF2A2SQ3"></cite>). This approach leads to network visualizations in which all individuals occupy the same space, aiming at a more balanced representation and a more proper image of the entire organization.



The investigation started with Infoscience, the repository of EPFL research based on CERN’s open-source software Invenio (<cite data-cite="1465847/4DJLKULF"></cite>). Maintained by the library, the Infoscience repository collects, stores, and shares institutional scientific and gray literature, including around 8,000 doctoral theses. Whereas the Affinity Map project was exclusively relying on the analysis of article abstracts, the idea with Super-Vision was to advance the methodology by applying text analysis to full texts. However, to experiment this, it was necessary to use a homogeneous corpus of scientific literature that was identified into the doctoral theses. Unlike journal articles often affected by copyright restrictions (<cite data-cite="1465847/Q4H89YI6"></cite>), doctoral theses feature the rare qualities of being publicly available and having consistency over time. The accessibility of both metadata and full texts in PDF format makes the corpus of doctoral theses an ideal solution for visualization. In addition, the opportunity to look at a scientific organization from an original dataset, situated between academic education and research career, represents a barely explored area of mapping that diverges from the current institutional perception.



Technically speaking, the collection of doctoral theses enables a twofold navigation relating to textual information (<cite data-cite="1465847/H6CIZNSG"></cite>) and temporal dimension (<cite data-cite="1465847/WBB27VD2"></cite>). On the one hand, body texts offer the opportunity to explore techniques of natural language processing (<cite data-cite="1465847/PHTPQ458"></cite>) and dimensionality reduction (<cite data-cite="1465847/TZI9V4GP"></cite><cite data-cite="1465847/EGN3IT95"></cite>). On the other hand, metadata enables the temporal analysis of publications through techniques of data visualization (<cite data-cite="1465847/43C84E9N"></cite>). Both data dimensions can provide interesting insights on institutional evolution by visually reproducing the EPFL trajectory.



The entire data analysis and development was facilitated by Observable (<cite data-cite="1465847/SDVTBDDI"></cite>), a digital platform to treat and plot data by making use of real-time programming through an interface that recalls Jupyter Notebooks. Founded by Mike Bostock, who earned its reputation by working at the New York Times, such a platform makes advanced data visualization techniques accessible to a broad audience by using the d3.js library (<cite data-cite="1465847/D4SJ8DFK"></cite>).


The first attempt at exploring the dataset is represented by the scatter plot below, which organizes doctoral theses in a timeline. Despite its simplicity, this visual tells us much information about the collection. At first glance, the horizontal axis organizes the publication by year, which increases as the time goes by: the more space between ticks, the higher the number of doctoral theses in the specific time window. On the vertical dimension, distribution is aleatory but necessary to untangle the dot overlapping. In terms of precision, it is interesting to observe the temporal classification: the full date is part of the metadata except for the dissertation defended before 1999, and for unclear reasons, a time window between 2008 and 2012. Diversely, colours reveal some characteristics to consider carefully: in grey are doctoral theses that are not associated with any faculty, probably because of the institute’s reorganization; in orange and grey are those doctoral theses without abstract, whose absence affects in part the text analysis; in green are doctoral theses with a complete metadata set.

```python tags=["figure-wrangling-*"]
from IPython.display import Image
metadata={
    "jdh": {
        "module": "object",
        "object": {
            "type":"image",
            "source": [
                "The first attempt at exploring the dataset is represented by the scatter plot below, which organizes doctoral theses in a timeline. Despite its simplicity, this visual tells much information about the collection. At first glance, the horizontal axis organizes the publication by year, which increases as the time goes by: the more space between ticks, the higher the number of doctoral theses in the specific time window. On the vertical dimension, distribution is aleatory but necessary to untangle the dot overlapping. In terms of precision, it is interesting to observe the temporal classification: the full date is part of the metadata except for the dissertation defended before 1999, and for unclear reasons, a time window between 2008 and 2012. Diversely, colours reveal some characteristics to consider carefully: in grey are doctoral theses that are not associated with any faculty, probably because of the institute’s reorganization; in orange and grey are those doctoral theses without abstract, whose absence affects in part the text analysis; in green are doctoral theses with a complete metadata set."
            ]
        }
    }
}
display(Image("media/wrangling.png"), metadata=metadata)
```

This initial overview proves the steady growth of doctoral theses but also reveals something unexpected: considering that EPFL was celebrating its fifth anniversary, how was it possible that a consistent number of publications could date back to the beginning of the twentieth century? After a brief investigation, we realized that EPFL was previously integrated into the University of Lausanne and only in 1969 was transformed into an independent institute, bringing with it a selection of doctoral theses. The detachment was due to a political choice to balance the linguistic predominance of ETH Zürich in favour of the French-speaking part of Switzerland (<cite data-cite="1465847/9H3MJEZ9"></cite>).


Although doctoral theses’ increasing frequency represented a valuable insight for museum visitors, there was a more complex research question to address in the project: what kind of organizational structure could be extracted from doctoral supervision? Embracing the idea that scientific communities should be represented by all individual members (<cite data-cite="1465847/EF2A2SQ3"></cite>), it was decided to avoid any kind of quantitative analysis by focusing on doctoral students instead of their advisors. Representing a social network of both would have led the readers to identify the most central individuals, overshadowing everyone else. With the Super-Vision project, there was a general intention to give prominence to the individuality of the whole organization to present EPFL not as a hierarchical institute but as an extensive network of international scholars.


The basic idea was revealing EPFL’s structure through a network of doctoral students arranged according to a metric of textual similarity. Titles, abstracts, and the first ten pages of 8,000 doctoral theses were analysed to extract the most used terms for each publication, using the spaCy library for Python (<cite data-cite="1465847/2LBUXWW5"></cite>). The number of pages was limited due to the computational load of machines at our disposal. Successively, the algorithm TF-IDF — which stands for *term frequency-inverse document frequency* — identified the most relevant words for each doctoral thesis with respect to the entire corpus (Salton et al., 1975). Such a step is helpful to get rid of the most common terms of the corpus, which are not relevant to developing a metric of similarity. The resulting dataset was then processed through an algorithm of *dimensionality reduction* to create the mapping. The UMAP algorithm (<cite data-cite="1465847/XK5BRHQB"></cite>) can be indeed used to reduce the highly complex lexical dimensionality into two dimensions, enabling the mapping on the Cartesian plane in what is commonly known as word embedding (<cite data-cite="1465847/53E86Z6N"></cite>).


The result of this process is visible in the figure below where the network structure is created by using Urquhart, an algorithm that draws connectivity between near nodes to avoid line overlapping (<cite data-cite="1465847/HGDVFNHE"></cite>). The figure shows how doctoral theses/students are clearly grouped in specific areas, confirming the initial hypothesis that lexical information can reveal the overall organizational structure of the EPFL. A scattered structure, on the contrary, would have proved the presence of a non-uniform linguistic corpus, indicating a potential risk of inconsistency in data or methodology.


Looking at the figure below, we can easily see where the faculties are positioned. Assuming a faculty numbering on two lines, respectively A, B, C, and C, D, E, we can infer some information about the general interdisciplinary structure by looking at this small multiple. The School of Architecture, Civil and Environmental Engineering (A) and the School of Computer and Communication Sciences (B) are characterized by a well-defined lexical structure, which confines them to specific regions of the map. The School of Basic Sciences (C) and the School of Engineering (D) spread horizontally, suggesting the use of a lexicon that overlaps other disciplines. The School of Life Sciences (€) proves to have a strong identity despite its young age, and the College of Management of Technology has not enough doctoral students to delineate a clear border.

```python tags=["figure-faculties-*"]
from IPython.display import Image
metadata={
    "jdh": {
        "module": "object",
        "object": {
            "type":"image",
            "source": [
                "EPFL is structured into five schools and two colleges, represented here by their doctoral theses. Each image represents a specific faculty, highlighted in a brighter white. In reading order from top left, the School of Architecture, Civil and Environmental Engineering (ENAC), the School of Computer and Communication Sciences (IC), the School of Basic Sciences (SB), the School of Engineering (STI), the School of Life Sciences (SV), and the College of Management of Technology (CDM). The College of Humanities (CDH) is not represented as its doctoral school welcomed the first graduate after the creation of Super-Vision. It is interesting to notice how doctoral theses of the previous period not associated with any faculty, without English abstract, are clustered into the peninsula at the bottom of the network structure."
            ]
        }
    }
}
display(Image("media/faculties.jpg"), metadata=metadata)
```

## Graphic and Interaction Design


While the data investigation was active, provisional results underwent a design process to give them a form to advance understanding through visual and interactive means (<cite data-cite="1465847/CA3XKSB3"></cite><cite data-cite="1465847/NMBTVCIJ"></cite><cite data-cite="1465847/KES9SJPC"></cite>).



The Super-Vision project resulted from a participatory design (<cite data-cite="1465847/WZH4CHET"></cite>) that involved expertise from data science, information design, experimental museology, and academic research. Dario Rodighiero (MIT) oversaw the general concept and the data collection, Philippe Rivière (Visionscarto) the data analysis and visualization, Patrick Donaldson (EM+) the graphic design, and Sarah Kenderdine (EM+) the museum installation. It is worth noting that most of the development was carried out with collaborators from Switzerland, France, and the United States who could collaborate through Slack, Observable, and Dropbox. However, it is important to stress that a consistent part of the project budget was used to meet in person two months before the exhibition to take a look at the gallery space and adjust the graphic layout. Indeed, the calibration of colours, fonts, and shapes, and the testing of technical devices are operations that have to be  scrutinized by everyone in the exhibition location. Although the design process moved online smoothly, the opportunity to meet in person accelerated the finalization of the project.


The idea of a timespan- and structure-based data visualization representing EPFL evolution inspired the general concept of the digital installation. As a result, the Super-Vision project was created as a compound of two distinct but complementary visualizations representing time and space respectively. As visible in the figure below, the screenshot shows how the centre of this compound visualization hosts a network visualization arranging doctoral theses according to their lexical similarity: the more two of theses are nearby in the Cartesian plane, the greater their similarity ((<cite data-cite="1465847/UXAJSQYI"></cite><cite data-cite="1465847/SCADPH2G"></cite><cite data-cite="1465847/EF2A2SQ3"></cite><cite data-cite="1465847/2IY3BJAW"></cite>)). The network visualization draws an image of 8,000 doctoral theses, which allows the viewer to observe a visual classification by faculty of the entire corpus of doctoral theses, enabling spatial exploration. Around this network, a line chart marks an outer circle that works as an enclosing frame, showing the increasing frequency of doctoral defences. The network visualization and the line chart offer two complementary perspectives of the same dataset, creating a novel compound that can be described as an intermediary object between a dashboard and a basic visualization. In the case to imitate the incomparable Charles Joseph Minard’s infographic presenting Napoleon’s defeat (<cite data-cite="1465847/CVFJ63WL"></cite>), Super-Vision’s visualization guides the viewer through historical data through a multidimensional instrument to look into the institutional dimensionality of doctoral advising.

```python tags=["figure-design-*"]
from IPython.display import Image
metadata={
    "jdh": {
        "module": "object",
        "object": {
            "type":"image",
            "source": [
                "This screenshot shows an intermediate version of Super-Vision, created during design developments. The circular timeline embraces the institutional structure, offering two different points of view of the same dataset. This compound visual allows exploring 8,000 doctoral theses interacting simultaneously with the two data visualizations. The cyan colour indicates selections: the highlighted dots indicate those doctoral theses defended in the period highlighted by the timeline. The most visible selection allows the user to get information about a specific thesis, highlighting the faculty structure in the background network. "
            ]
        }
    }
}
display(Image("media/design.png"), metadata=metadata)
```

An additional level of information is given by interactivity, which allows users to explore the dataset in detail. The figure above shows how the compound visualization is characterized by cyan graphic elements indicating selections. One user can navigate through time on a laptop by scrolling the trackpad, which moves the selection bar.  In response to this input, some graphic elements start bumping to bring out from the intertwined tissue of the doctoral theses defended in the selected period. From this central space, the user is invited to select one bouncing dot to get further information: on click, the interactive interface will show the title, candidate, directors, and faculty of the selected doctoral thesis, accompanied by a background effect showing the relative faculty’s extension. Only at this point the user is offered to explore the neighbourhood by navigating transversally similar works. This combination shows us how information and interaction design are intimately connected by their shared goal of understanding data, as recently discussed by Manuel Lima in a recent interview (<cite data-cite="1465847/FLKAEEBR"></cite>).



In the timeline, the selection bar progressively diminishes its length when going forward. This solution was necessary because the corpus’ density would not otherwise enable neat navigation in the most recent years. Despite this visual limitation that prevents overwhelming information, the user can still perceive the deluge of doctoral theses by scrolling forward the time bar. When the timeline is scrolled quickly, the animation accumulates hundreds of bouncing dots from the scrolled period. Such a feeling of being overwhelmed is usually avoided in information design because it generates unreadable, chaotic visuals. However, the same experience of surprise (<cite data-cite="1465847/399NSLGL"></cite>) or sublime (<cite data-cite="1465847/CA3XKSB3"></cite>) can help the user to realize the vast number of elements in their wholeness, which are typically difficult to grasp.


A copy of the interactive interface of Super-Vision can be used on the Visionscarto website at https://visionscarto.net/maps/super-vision/, while the code is openly accessible on https://observablehq.com/@fil/epfl-super-vision.

```python tags=["figure-observable-*"]
from IPython.display import IFrame
IFrame('https://observablehq.com/embed/@fil/epfl-super-vision?cells=chart%2Ccss%2CshowWords%2Cstyle%2Cratio%2Cpolygon%2CyearShift%2ChtmlNode%2Cupdate_hover%2CN%2CmapSize%2Cx%2Cy%2CinitializeNodes%2Cbuffers%2Cstate%2C_worker%2CcreateWorkerFrom%2Cviewof+sensitivity%2CdefaultWheelDelta%2CdrawNodes%2Ccolors%2Cradius%2Cfont%2CH%2Cenclose%2CdrawUrquhart%2CdateReader%2CYEAR%2CbyYear%2Cres%2Chover%2CcircularTimeline%2CyearCount%2Cangle%2Cmodes%2CdrawModes%2Crawtheses%2Curl_umap_embedding%2Cumap_embed%2Calltheses%2Ctheses%2Cdata%2Cangle_a%2Cres_baked%2CapproximateCount%2CapproximateCountDerivative%2CintervalTheses%2Cd3%2Ctau%2CformatRow%2Cwidth%2Cheight%2Csin%2Ccos', width='100%', height='800')
```

## Physical Installation


Super-Vision was explicitly designed for Infinity Room 2, and some adopted solutions were offered by the exhibition space and the technical material at our disposal. For example, the choice of a circular projection was not only suggested by the form of the UMAP algorithm but also because of the availability of a round-shaped projection surface already employed in another exhibition. The surface measuring one meter and a half, previously used on the floor, this time was hung on the gallery’s wall to maintain the verticality of the textual information (see figure below).


The projection surface also represented a constraint to space out the projector. The two-meter distance from the wall balances the spectator’s view, the projector’s resolution, and the luminosity contrast between the projection screen and gallery illumination. The installation was thus completed with a one-meter column capable of hosting the projector and a device to interact with the data visualization. The chosen device was a three-dimensional mouse that allowed the visitor to browse the doctoral theses on the Cartesian plane and move throughout the timeline by rotating the wheel in clockwise or counter-clockwise directions. The rotation characteristic was particularly relevant for the final choice because it recalls the visualization’s rounded shape, creating a cognitive correspondence between shape and functionality.



The Super-Vision digital installation was positioned in a niche of the long hall of EPFL Pavilions during the exhibition, where the illumination was softer because of the video projection. The visitor was naturally invited to enter the dedicated space, finding immediately the controller placed on the column that implicitly suggested the preferred standpoint. In addition, an idle function that animated the data visualization by automatically advancing the timeline selector captured the audience’s curiosity by showcasing the system’s interactivity. Such an animation was frozen when the visitor took control of the mouse and reverted to idle mode after a short period of inactivity.


```python tags=["figure-installation-*"]
from IPython.display import Image
metadata={
    "jdh": {
        "module": "object",
        "object": {
            "type":"image",
            "source": [
                "This photograph shows how Super-Vision appeared in the EPFL Pavilions. One visitor takes position in front of the projection, behind a wooden column hosting the projector and the three-dimensional mouse. Their curiosity is attracted by automatic idle navigation and the light contrast."
            ]
        }
    }
}
display(Image("media/installation.jpg"), metadata=metadata)
```

## Conclusion


Digital archives are valuable information sources to retrace the most recent history of institutions. Leading scientists can use data analysis and visualization techniques to investigate historical records, obtaining unique perspectives that would be difficult to read otherwise.


This article addresses the potential of collaboration, especially for experimental museology and, more extensively, for digital humanities. In a moment in which interdisciplinarity seems to be struggling to establish itself in academia, museums represent ideal experimental platforms for pioneering at the intersection of data, art, and science.



Observing how data visualization runs across disciplines and professionals is engaging. Its transversality allows scholars to cover the distance between academia and the private sector, as computer science did in the last few decades. The subsequent developments must be followed closely, especially when focusing on public spaces where information can be addressed to a larger public than the academic one. Museums offer physical space for data visualization and blur the borders between art and science more freely than academia. As Hans Ulrich Obrist and Barbara Vanderlinden mentioned, museums can be considered scientific laboratories where scholars can experiment more freely by conveying critical thoughts to museum visitors.



In particular, the most critical thought in the Super-Vision project raises concerns about the university’s fast-growing model. The data visualization clearly shows how there was roughly one doctoral defence per month during the 1960s, while EPFL today exceeds one thesis per day. To a keen eye, this stunning insight not only represents a statistical increase but also reveals more-hidden institutional regulations. Indeed, this university model prefers to invest money in doctoral students rather than intermediary research positions like researchers and senior researchers, which are disappearing from the organizational chart, obliging many scholars to move out of the institute or accept administrative employment. On the one hand, the increase in doctoral students represents a more significant opportunity to pursue doctoral studies, but on the other hand, it makes the academic career more difficult than before because of the higher number of potential candidates for professorships.



The insights of Super-Vision let the museum visitor thoughtfully look at institutions from an innovative perspective while maintaining a critical eye on data and society. Digital archives already show the potential for future inquiries, and the field of contemporary history needs to be revised through digital means.



## Acknowledgments


This article would not be possible without the financial help of the Swiss National Science Foundation, which funded grant number P400PS_194442, Recommendation System for Academic Mobility. Thanks to Patrick Donaldson and Giulia Bini, who supported the project from its early development. Thanks also to Maxene Graze and Linda Ardenghi, whose editing was invaluable to give the text the final form.


<!-- #region tags=["hidden"] -->
## Bibliography
<!-- #endregion -->

<!-- #region tags=["hidden"] -->
<div class="cite2c-biblio"></div>
<!-- #endregion -->

```python

```
