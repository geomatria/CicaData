# CicaData

Files:
CicaData.json - A catalogue of Cicada 3301 files, their attributes and relationships, using JSON.

Folders:
assets/ - repository of files, each asset has a folder corresponding to its "id".
templates/ - contains JSON templates for predefining attributes for common and specific file types.

Hierarchy - assets can spawn child objects and we can define these relationships.
Example; the very first image, final.jpg, was the parent of two child objects; the decoy duck and the first outguess message:

[
  {
    "id": 0,                          ## This is the first asset, begin at 0.
    "friendly-name": "final.jpg",     
    "parent-id": null,                ## As this is the first asset, there is no parent.
    "child-id": null,                 ## It is not a child of any other object, being the first.    
    "child-objects": [                ## It does spawn two child objects; the decoy duck and an outguess message.
      0,                              ## Define the child objects, using the "child-id" of the subsequent object.
      1
    ]
  }
],

[
  {
    "id": 1,                          ## This is the second asset in the series.
    "friendly-name": "decoy duck.",
    "parent-id": 0,                   ## The parent of this file is final.jpg. Define the parent by the parent's "id".
    "child-id": 0,                    ## This object is the very first of child object, begin at 0.
    "child-objects": null             ## It has no child objects.
  }
]

[
  {
    "id": 2,                          ## This is the third asset in the series.
    "friendly-name": "outguess 1",
    "parent-id": 0,                   ## The parent of this file is final.jpg. Define the parent by the parent's "id".
    "child-id": 1,                    ## This is the second child object.
    "child-objects": 2                ## This asset spawns a child object; a link to the subreddit.";    ]             
  }
]

.. and so on.
