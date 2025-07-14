# Test Project Outline – Module D – Interactive Frontend using an API

## Competition time

Competitors will have **4 hours** to complete module D.

## Introduction

Module D will focus on the implementation of a frontend for a REST API.

## General Description of Project and Tasks

The competitors will be asked to create a frontend for a REST API. First, users of that frontend will need to log in. Using the authentication mechanism of the API, the frontend will then be able to access the API and send as well as retrieve data from it. The functionality created by competitors in this module, builds on top of the functionality created in module B and C. Competitors will be given a working solution of Module C at the start of Module D, which they must use. Competitors are not allowed to build on top of their own Module C solution.

The users of the frontend will be able to discover the available AI services that the API provides. Each service is then represented on a separate page which exhibits several interactive elements, each custom to the service. There will be complex data inputs and outputs, some of them are asynchronous. The goal of the frontend is to hide this complexity from the user. The frontend must also handle errors and display them to the user in a comprehensible way.

Initially the input elements are disabled. When a user wants to start using the service, they are prompted to enter an API token, which can be generated with the solution from module B. The API token must then be sent to the server with every request. The API token shall also be stored in the current browser instance, so that the user does not have to enter it again, even if they reload the page or navigate to another AI service.

You must implement the frontend using a framework. It is possible to use additional libraries. The application must be a Single Page Application (SPA). The routing must be handled by the framework. Page reloads must present the same content to the user as previously visible, except unsaved user driven inputs or temporary outputs.

## Requirements

The goal of this frontend is to provide users with an intuitive interface to interact with AI services through a REST API. Users must be able to authenticate, access multiple AI services, and handle various data types and interactions seamlessly.

The frontend must implement the following functional requirements:

- Single Page Application (SPA) architecture using a modern JavaScript framework
- Authentication system using API tokens from Module B solution  
- Integration with provided Module C API solution
- Error handling for various HTTP status codes (400, 401, 403, 503)
- Local storage for API token persistence
- Interactive elements specific to each AI service
- Responsive design for optimal user experience

### Error Handling

The API can sometimes return errors or the billing quota could be used up. The frontend must handle these errors and display them to the user in a comprehensible way. The following errors must be handled:

- `400 Bad Request` – The request was malformed. The user must be notified that they have entered invalid data.
- `401 Unauthorized` – The API token is invalid. The user must be prompted to enter a new API token.
- `403 Forbidden` – The billing quota has been used up. The user must be notified that they have to wait until the next month to use the service again or increase their quota.
- `503 Service Unavailable` – The service is temporarily unavailable. The user must be notified that the service is currently unavailable and to try again later.

### Pages

The following pages must be implemented:

#### Home

The home page must display a list of all available AI services. Each service must be represented by a link to the corresponding page. The list must be sorted alphabetically by the name of the service.

#### Service ChatterBlast

The ChatterBlast service is a chatbot. The user can enter a message and the chatbot will respond with a message.

The page must contain the following elements:

- A text input field for the user to enter a message.
- A button to clear the text input.
- A button to send the message to the chatbot for the current conversation or create a new conversation if it's the first one.
- An area to display the response from the chatbot.
- A button to start a new conversation with the chatbot.

The responses from the chatbot must be shown as they become available, even if they are only partially complete. The response text must be animated in a typewriter style. The animation must contain a blinking cursor and each character must be rendered individually with a random delay between 2ms and 20ms. You must poll the backend to get the current response. The polling interval must be 1 second.

While the response is incomplete, the button to send a new message must be disabled.

#### Service DreamWeaver

The DreamWeaver service is an image generator. The user can enter a text and the service will generate a new image.

The page must contain the following elements:

- A text input field for the user to enter a text.
- A button to clear the text input.
- A button to generate a new image.
- An area to display the generated image.
- A button to save the image to the local file system.
- A button to upscale the image.
- A button to zoom in and out of the image.

A loading indicator with progress in percentage must be displayed while the image is being generated, and the preliminary images must be animated with a fade-in effect until the final image is available. You must poll the backend to check if the job progress and to retrieve the preliminary image. The polling interval must be 2 seconds.

While the image is being generated, the button to generate a new image must be disabled.

#### Service MindReader

The MindReader service is a mind reader. The user can upload an image and the service will recognize the objects in the image.

The page must contain the following elements:

- A file input field for the user to upload an image.
- A button to upload the image to the service.
- Once objects are recognized:
  - A message that indicates how many objects have been recognized.
  - The recognized objects are shown with a transparent rectangle with a red border on top of the image alongside a label in the upper left corner of the rectangle.

While the image is being uploaded and the objects recognized, the button to upload a new image must be disabled and a loading indicator must be shown.

## Assessment

Evaluation will be conducted using **Google Chrome (latest stable version)**. The assessment will include:

- **Functional Testing**: All required features must work as specified
- **User Experience**: Intuitive interface design and smooth interactions
- **Code Quality**: Clean, maintainable JavaScript/TypeScript code
- **Framework Implementation**: Proper use of chosen frontend framework
- **Error Handling**: Comprehensive handling of API errors and edge cases
- **Accessibility**: Basic accessibility principles using browser tools

**Important**: Any modifications to the provided Module C backend solution, including database changes, will not be considered during assessment. Use only the provided API as-is.

## Mark distribution

The table below outlines how marks are broken down and how they align with the WorldSkills Occupation Standards (WSOS).
Please read the Technical Description for a full explanation of the WorldSkills Occupation Standards.

| WSOS SECTION | Description                            | Points |
| ------------ | -------------------------------------- | ------ |
| 1            | Work organisation and self-management  | 0      |
| 2            | Communication and interpersonal skills | 0      |
| 3            | Design Implementation                  | 5      |
| 4            | Front-End Development                  | 17     |
| 5            | Back-End Development                   | 0      |
|              |                                        |        |
| **Total**    |                                        | 22     |
