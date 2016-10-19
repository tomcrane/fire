# fire

https://tomcrane.github.io/fire/

(contains sound, requires mp4 support - for demo only!)

This is an experiment with time in the IIIF Presentation API, by allowing a temporal dimension (e.g., `t=5,20`) as well as the existing spatial dimensions in the fragment part of an annotation target:

`
"on": "https://tomcrane.github.io/fire/canvas/1#xywh=70,60,500,100&t=5,20"
`

The canvas itself also has a duration:

`"duration": 120`

## Why?

Adding time to Shared Canvas is necessary for AV in IIIF. This allows media to be positioned in space and time. Reconstructing [The Magnificent Ambersons](https://en.wikipedia.org/wiki/The_Magnificent_Ambersons_(film)) with annotation of studio stills, screenplay, scores etc is an AV use case analagous to existing manuscript use cases for images. Conveying the audio sequencing and the packaging of [The White Album](http://www.whitealbumregistry.com/inside.php) is important for Sound collections.

Time in the Presentation API allows storytelling. If your collection is full of images, audio, video and text, you can create IIIF collections and manifests that tell stories through annotation, and pull in fragments of video from anywhere over HTTP. This demo is simple, to give context to discussions about the Presentation API and IIIF AV APIs, but the same model could be used to create things like http://apollo17.org/ and almost any timed presentation or exhibit.

It would be great if, for example, the [multimedia works of Charles and Ray Eames](http://www.eamesoffice.com/catalog-category/multimedia/) were modelled with the IIIF Presentation API and available for annotation, from relatively simple [three projector](http://www.eamesoffice.com/the-work/g-e-m-slide-show/) slide shows to the complexity of [Think](http://www.eamesoffice.com/the-work/think-2/) from the 1964 New York World's Fair.  

This demo only supports integer seconds. Other time fragment syntax is required as specified in https://www.w3.org/TR/media-frags/#naming-time.

Time is required for IIIF AV, but a bitstream API equivalent to the Image API is not required for simple presentation of AV material, just as the Presentation API does not require images to have Image API services. The simplest AV example would be a single video annotation filling the whole canvas for its entire duration, just as a single image annotates a whole canvas in the simplest image use case.

## Clock

The use of setTimeout to show and hide the annotations is probably naive. A IIIF client should offer pause, play, and scrub over a canvas clock (a global clock separate from the play time of the individual media). Video, audio and text annotations need to be synchonised, and stay synchronised in the face of variable CPU load.

A real client can use libraries such as http://popcornjs.org/ and/or techniques such as https://www.sitepoint.com/creating-accurate-timers-in-javascript/ to do this more reliably.

## Client side

The Presentation API model can describe comples things that modern browsers are quite capable of doing client-side. See http://ronallo.com/blog/client-side-video-tricks/ for more information.

