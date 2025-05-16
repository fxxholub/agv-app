# AGV App

This repository consolidates a microservice applications into one.

It is a part of athor's diploma thesis at FEE CTU Prague.

## Thesis assignment

__Title:__

Development of control system and handling interface for automated guided vehicle

__Assignment:__

The aim of the work is the design and implementation of a control system and interface for a robotic vehicle
supplied by an external contractor, the purpose of which will be to test and demonstrate the use of laser
measuring devices.

- Study in detail the automated guided vehicle platform, control modes and integration of ROS nodes and PLC
system.
- Evaluate and select technologies suitable for backend system and web interface development with respect
to real-time communication capabilities, security, and ease of integration with ROS.
- Design a lifecycle management module for ROS nodes for each control mode and an intuitive web-based
control interface that allows operators to easily control the vehicle, including entering motion commands and
visualizing real-time status.
- Test the developed system in a real-world environment, verify its functionality, reliability and user-friendliness,
and suggest improvements, if any.

## About

The application is an interface to the AGV robotic systems build on ROS.

This repository does not contain any UI. The frontend application is confidential, although the UI components, also being part of the thesis, are shared through the [Ros2DotnetUI](https://github.com/fxxholub/Ros2DotnetUI) RCL library.

### Microservices

1) Handling service

    Runs and manages a ROS Docker containers based on selected handling mode. Routes messages from and to ROS with SignalR API. Handles user connection based session and connection based authorization.

2) Map store service

    A store (database) of generated maps with REST API.

3) Auth Service

    Handles authentication and authorization of users in the app. Acts as auth gateway for the other services.

## Local usage

1) Init and update the submodules: `git submodule update --init --recursive`
2) Setup `ProcessConfig/config.json`, read more in [Handling Service README](https://github.com/fxxholub/agv-app-handling-service.git)
3) Setup a common `.env` file with environment variables based on each service
4) Build and run the application: `docker compose up --build -d`
