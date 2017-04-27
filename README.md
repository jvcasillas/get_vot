# get_vot

### VOT procedures for Praat  

### Authors: Jaekoo Kang, D. H. Whalen

---

This directory contains procedures for Praat (Boersma & Weenink, 2009) to assist in the
measurement of Voice Onset Time (VOT; Lisker & Abramson, 1964; Abramson & Whalen, 
submitted). It also contains example files for the user to explore.

  One procedure takes a Praat TextGrid with segments labeled (interval labels) 
and prepopulates a new interval tier ("Phone") with labels appropriate for measuring VOT:  
* VDCLO: the voiced portion of a closure  
* VLCLO: the voiceless portion of a closure  
* REL: the release burst  
* ASP: the aspiration after the burst  

For later analysis, only REL is required, and it is required even if the release burst is absent (an arbitrarily short interval should be used).  The other intervals may or
may not be present.  See Abramson & Whalen (submitted) for details.

  To use "[prepopulate.praat](https://github.com/HaskinsLabs/get_vot/blob/master/prepopulate.praat)", create labels for a speech file with, at a minimum, an
interval tier (default name = "Segment") that labels the segments of interest with IPA 
symbols.  The default set of symbols expected is "b,d,g,p,t,k", but others 
(e.g., "s,sʰ,pʰ,tʰ,kʰ) can be added. Then, open Praat and run "prepopulate.praat".
It will allow the choice of directories and files, as well as segments to be
analyzed.  For each segment named, the four intervals are inserted in a new tier, 
"Phone".  The duration of that segment is divided arbitrarily
into four equal lengths for the initiation of the labels.  The user can then modify them
in Praat, opening the new TextGrid with the Sound files, and adjusting the boundaries 
to the true locations; any unneeded labels can be removed.

  These labels can also be entered entirely by hand.  We have found it quicker to
adjust the boundaries than to have to type the label names many times.

  Once the "Phone" tier is complete, the second procedure, "[get_vot.praat](https://github.com/HaskinsLabs/get_vot/blob/master/get_vot.praat)", can be
used.  It will allow the choice of directories and files, as well as segments to be
analyzed.  A new tier, "VOT", is created and the VOT measurements are stored there.
Positive VOTs will have the label "VOT", while negative VOTs (prevoicing) will have
the label "mVOT" (for "minus VOT").  A .csv file can also be created with these values.

  **Note**: Before creating a .csv file, go to Praat -> Preferences -> Text writing preferences.
There, choose UTF-8 so that the file will open properly in Excel.

Additional information can be found at the beginning of each procedure.