# Road Resilience Analysis in Uttarakhand

*Predicting Precipitation-Induced Road Closures in Uttarakhand*

In Uttarakhand, irregular rainfall patterns and mountainous terrain make roads susceptible to precipitation-induced closures by flooding or slope failure. These road closures have a significant impact on the livelihood of individuals in Uttarakhand’s rural communities, who rely on roads to access basic amenities.

With the availability of granular micro-weather data, we can build upon previous methods to develop a dynamic model that predicts real-time and forecasted road closures. With this model, local transportation authorities can engage in proactive emergency planning for predicted road closures, such as rerouting traffic or sending early-warning alerts to villagers.

The analysis will be performed through the following steps (from left to right on the diagram):

1. Gather and clean three types of variables that could impact road closures: topography, road characteristics, and weather.
2. Run a logistic regression model to analyze the impact of these variables on road closures.
3. Perform a population density buffer analysis to assess road criticality.
4. Combining weather forecasting with assessed road criticality, create a road closure risk report for the following week.

## Installation

### Basics

Clone the code to your machine using the standard Git clone command. If you have SSH keys setup the command is:

```
git clone git@github.com:datapartnership/road-resilience-in-uttarakhand.git
```

### Docker

You will need to have Docker and docker-compose installed on your system to run the code.

#### Install Docker

- For Mac: <https://store.docker.com/editions/community/docker-ce-desktop-mac>

- For Windows: <https://store.docker.com/editions/community/docker-ce-desktop-windows>
- For Linux: Go to this page and choose the appropriate install for your Linux distro: <https://www.docker.com/community-edition>

## Usage

### Starting the container and entering Jupyter

- From the repo directory, run `./run_env.sh`. (On certain linux installations, you might need to use `sudo ./run_env.sh`).

- If the Docker container is already on your system, it will start.  Otherwise, it will first update from [the container on Docker Hub](https://hub.docker.com/r/mrmaksimize/hospital-access-env), then start.
- You should see the following in your terminal.  Copy the link outlined to your browser:

![](https://s3.amazonaws.com/files.maksimpecherskiy.com/2020-09-09_10-58.png)

- Once you pull up Jupyter, all of the code is inside the `/work` folder.

### Dev Environment

After you started the Docker container, your development environment will look like this:

![](https://s3-us-west-1.amazonaws.com/manifold-public-no-vpn/torus_local_dev.png)
*Credit: [Manifold AI](https://github.com/manifoldai/orbyter-cookiecutter)*

All of the modules are installed inside the docker container, and that is where code execution happens.  However, you're able to edit your files locally, just like you would with any other project.

### Repo Structure

```
├── README.md          <- The top-level README for developers using this project.
├── run_env.sh         <- Convenience wrapper for starting the docker container.
├── Dockerfile         <- Docker container configuration.
├── .env.example       <- Sample environment file to be copied to `.env`
├── data
│   ├── external       <- Data from third party sources.
│   ├── interim        <- Intermediate data that has been transformed.
│   └── processed      <- The final, canonical data sets for modeling.
│
├── docs               <- A default Sphinx project; see sphinx-doc.org for details
│
├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
│                    and a short `-` delimited description, e.g.
│                         `01-initial-data-exploration`.
│
├── references         <- Data dictionaries, manuals, and all other explanatory materials.
│
├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
│
│
└─src                <- Source code for use in this project.
  ├── __init__.py    <- Makes src a Python module
  ├── functions.py   <- Functions for running analysis
  ├── mapbox.py      <- Mapbox specific functions
  ├── raster_ops.py  <- Raster helper functions
  └── utility.py     <- Various utility functions
```

## Contribute

If you have questions or want to improve the code, please submit an issue. If this was useful, please let us know by submitting an issue as well!

## Acknowledgments

Project team: Emily Fang (emfang@mit.edu), Maksim Pecherskiy and Holly Krambeck. This project was supported by [Development Data Partnership](https://datapartnership.org).

## License

[World Bank Master Community License Agreement](LICENSE.md)
