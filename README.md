# fire

This demo explores time in the IIIF Presentation API, by allowing a temporal dimension as well as the existing spatial (xywh) dimension in the fragment part of an annotation target:

`"on": "https://tomcrane.github.io/fire/canvas/1#xywh=70,60,500,100&t=5,20"`

The canvas itself also has a duration:

`"duration": 120`

This demo only support integer seconds. Other time fragment syntax is required as specified in https://www.w3.org/TR/media-frags/#naming-time

Time is required for IIIF AV, but a bitstream API equivalent to the Image API is not required for simple presentation of AV material. The simplest example would be a single video annotation filling the whole canvas for its entire duration.

## Clock

The use of setTimeout to show and hide the annotations is probably naive. A IIIF client should offer pause, play, and scrub over a canvas clock (a global clock separate from the play time of the individual media). Video, audio and text annotations need to be synchonised, and stay synchronised in the face of variable CPU load and so on.

