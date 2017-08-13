# Hammertime Kassel

## Maintenance of Equipment

The workshop's available or planned equipment is displayed on the [equipment page](http://hammertimekassel.de/equipment.html) and its subordinated pages. The data for this sites is stored within the [\_data/areas](https://github.com/Hammertime-Kassel/htks/tree/master/_data/areas) folder.

### Areas

Each subfolder of the [\_data/areas](https://github.com/Hammertime-Kassel/htks/tree/master/_data/areas) folder represents a specific area of the workshop, e.g. the sewing area or the Fab lab area. The `info.yml` within each folder provides informations about the area.

#### Add a New Area

To create a new area, create a new subfolder within the [\_data/areas](https://github.com/Hammertime-Kassel/htks/tree/master/_data/areas) folder. The folder's name must be lowercase and words must be separated by underscores, e.g. `wood_workshop` and is now called the `area_id`.

Place an `info.yml` file within the folder and add the following informations:

```yaml
name: "" # the full name of the area
short_description: "" # a short description of the area in a few words
description: "" # a more lengthy description of the area
```

### Equipment

Each subfolder of an area folder represents a specific part of our equipment, e.g. a tool or machine. The `info.yml` within each folder provides informations.

#### Add a New Service

To create a new service, create a new subfolder within the `equipment` folder in the [\_data/areas](https://github.com/Hammertime-Kassel/htks/tree/master/_data/areas) folder. If there is no fitting area folder, you need to create a new one (see above). The folder's name must be lowercase and words must be separated by underscores, e.g. `secabo_ts7_swing_away_heat_press` and is now called the `equipment_id`. The `equipment_id` needs to be unique. Hint: Use the tool's or device's model number.

Place an `info.yml` file within the folder and add the following informations:

```yaml
type: "" # the general type of the equipment, e.g. "3D-Printer"
producer: "" # name of the producer
producer_link: "" # (optional) link to producer's website
model: "" # name of the model
model_link: "" # (optional) link to the model's page on the producer's website
equipment: # list of additional equipment that comes with the tool or machine. List of "name" and "value" pairs.
  -
    name: ""
    value: ""
  -
    name: ""
    value: ""
short_description: "" # short description of the machine or tool in a few words
description: "" # a more lengthy description of the tool or machine
technical_data: # list of technical informations. List of "name" and "value" pairs.
  -
    name: ""
    value: ""
  -
    name: ""
    value: ""
status: "" # possible values: "planned" => equipment is not available yet; "okay" => equipment is available and functional; "limited" => equipment is available but limited in functionality; "broken" => equipment is broken and cannot be used; "repairing" => the equipment is being repaired and cannot be used
additional_status_text: "" # (optional) an additional note that will be displayed beneath the status
images: # (optional) list of images of the equipment. images needs to be placed in the `/images/areas/<area_id>/<equipment_id>/` folder
  - original: "" # original, bigger image. needs to be placed in the `/images/areas/<area_id>/<equipment_id>/original` folder
    small: "" # smaller preview image. needs to be placed in the `/images/areas/<area_id>/<equipment_id>/small` folder
    title: "" # (optional) description for the picture
  - original: ""
    small: ""
    title: ""
```

After this, the equipment needs its own page. To do that, create a file called `<equipment_id>.html` within the `/equipment/` folder. Insert the `area_id` and `equipment_id` as follows:

```yaml
---
area_id: "" # the area_id
equipment_id: "" # the equipment_id
---
```

**TODO** the page will not yet show up automatically… until then: contact Thorben for help :-)

## Development

### Run site locally

#### Setup

You need to do this once.

1. Open Terminal
2. Check whether you have Ruby 2.1.0 or higher installed:

```shell
ruby --version
```

3. If you don't have Ruby installed, install [Ruby 2.1.0 or higher](https://www.ruby-lang.org/en/downloads/).
4. Install Bundler:

```shell
gem install bundler
```

5. Install requirements

```shell
bundle install
```

#### Run site

Regulary run `bundle update` to update depedencies.

To preview the site, run:

```shell
bundle exec jekyll serve
```

Open http://localhost:4000 in your browser.

## Contribute

TODO
