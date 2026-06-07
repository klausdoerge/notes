# Overview of spec tool

  

## Purpose

The purpose of the tool is to help planning of technical projects as well as breaking down the project into actionable tasks, which the AI can implement.

The tool is made to ensure that both the user and the AI has a common understanding of the overall project scope, it's architecture, tasks, user-stories as well as security and test-plans for the project.

  

A user will initially provide the tool with the requirements available, and the tool will try to evaluate what needs to be added. This is done both autonomously and by asking the user for clarification if in doubt.

  

The tool mus be able to work with new projects as well as implementing features and extensions to existing projects.

  

The tool must be able to write updates to the documetation in the projects. These files might live inside the project or on an external server, so others can participate in the developmenet of the projects as well as retrieving a status for the development.

  

When working with the flow a history is saved for all tasks and progress, so the end-user can monitor and review how and why the project looks and works.

  

The tool documentation should be made in Markdown. Could be an obsidian project if we integrate visual studio code with obsidian - or just enable ollama to use the MCP server for those tasks.

  

## Structure

There has to be a fixed structure for the documents, so it is possible to track the performance and make scripts. Maybe it should be a online tool, where the user can write or upload documents to use, when developing the skill

  

## Features

The tool is bulid upon several tools and features

  

### Tech-Architecture

This is a document which outlines the requirements for the technical implementation. It contains a list of programming languages, methods, patterns etc to use, as well as some code samples for the AI to understand the structure.

  

Exisiting available projects and their documentation should be available, so the AI can choose to use those as building blocks.

  

:: TODO ::

There should probably be separate projects for frontend and backend development, so we do not overload the context window.

  

### Grill-Me

### To-PRD

### To-Issues

### Issues-To-Tests

### Security review

### Performance review

### Development

### Deployment

:: TODO ::

Deployment should probably always be docker, so it is easier to maintain, and we avoid creating something too locked to the providers of tools.

  

### Improvement ideas

After implementing features, the tool will generate 5-10 ideas for improving the application. They should be segmented into ux, ui, performance, security etc.