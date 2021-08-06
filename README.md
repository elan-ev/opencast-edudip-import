Opencast Edudip Importer
========================

This tool automates the import of webinar recordings from
[edudip](https://edudip.com) into Opencast for further processing and
distribution.


How it works
------------

1. The importer talks to the edudip event api to get all available recordings
2. The importer requests the recording file location and hands that to Opencast for import
3. The importer stores the already imported events to not import the same event twice


Configuration
-------------

The importer will try loading its configuration in the following order, halting
if a valid configuration is found:

- ./edudip-import.yml
- /etc/edudip-import/config.yml

For further details about the configuration keys, take a look at the
configuration file. All keys are documented in the file.

To verify the syntax of the configuration is okay, you can run:

    ./import -t


Workflow
--------

While you can use any Opencast workflow with the importer, this repository
contains a minimal recommended workflow to use. The workflow is very simple and
consists of just three steps:

- Set a default workflow configuration (the options you would otherwise select
  in the admin interface “add event” dialog)
- Download the recording from the edudip cloud
- Start another workflow (“studio-upload” by default)

You can easily modify this and e.g. configure a different workflow to be
included at the end.


License
-------

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

See LICENSE for more details.
