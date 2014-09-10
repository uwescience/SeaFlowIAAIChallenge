SeaFlowIAAIChallenge
====================

This repository exists to provide instructions and information about the SeaFlow
data association with the IAAI Challenge Paper. This data set contains data from
three relatively small SeaFlow cruises, the Thompson 0, 1, and 10 cruises, respectively.

Each record of the data represents one observed particle (after filtering).
SeaFlow data has the following schema for all particles:
Cruise,Day,File_Id,Cell_Id,fsc_small,fsc_perp,pe,chl_small,pop

* Cruise: which cruise this particle came from (i.e. 'Thompson 1')
* Day: string representing date. This is an artifact of how SeaFlow data was previously recorded.
* File_Id: string represent file id under date. Again, this is an artificact.
* Cell_Id: a particle id for a particle under cruise/day/file_id.

The combination cruise/day/file_id/cell_id forms the primary key for a particle.

* fsc_small: forward scatter of a particle
* fsc_perp: perpendicular scatter of a particle
* pe: phycoerythrin measurement of a particle
* chl_small: chlorophyll measurement of a particle

These four dimensions are the measurements typically used to cluster SeaFlow data.

* pop: the hand-labeled population value. This is almost always a string (i.e. 'beads', 'noise', 'nano'),
but because some automation was used in labeling, it is possible that the label will be an integer.
Integer labeled particles can be ignored for testing goodness of a classifier.

The data as raw text is roughly 5GB; it can be downloaded here:

http://rest.myria.cs.washington.edu:1776/dataset/user-hyrkas/program-iaai/relation-sample_cruises/data?format=csv
