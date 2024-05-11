---
layout: project
type: project
image: img/lost-items-database-square.png
title: "UHM Lost and Found"
date: 2024
published: true
labels:
  - JavaScript
  - React
  - Bootstrap
  - MongoDB
summary: "A web application dedicated to posting lost and found items for the University of Hawaii Manoa campus."
---
<p align="center">
  <img src="../img/lost-items-database-full.png" width="700" />
</p>

## Overview

  UHM Lost and Found is a web application dedicated to posting lost and found items for the University of Hawaii (UH) Manoa campus. Departments can post about lost items within their offices, enabling students to recognize their belongings and know exactly where they may find them. Currently, UH Manoa does not have a designated office or platform for lost and found items. Instead, they require students to remember where they lost their item and contact the associated department. This project aims to solve this issue by providing a centralized platform for posting and retrieving lost items.

**The website implements a variety of useful features, including:**
* A comprehensive database of lost items from various UH Manoa departments
* Multiple fields (name, date found, location found, current location, image URL, owner) for each lost item
* A simple Edit function to edit item fields or remove items for departmental and admin accounts
* Certain pages are public (Home, Lost Items), while others require departmental and/or admin accounts (Add Item, Edit Item, Departments, Add Department)
* Responsive design for mobile devices

## Contributions

**In this project, my contributions were primarily:**
* Implementing add and edit functionalities for the lost items database
* Writing acceptance tests for each page
* Deploying the website and refreshing the database with each update
* Setting up and maintaining the domain name and HTTPS
* Creating documentation
* Collecting community feedback

  Other minor contributions included creating the footer and fixing several bugs here and there. Regarding the add and edit functionalities, I ensured that each department would only be able to add and edit items from their department and that the admin account would have edit access to items from all departments. I also wrote the acceptance tests such that they would test the various functionalities of each page, from verifying that the read more button displays item descriptions to checking that attempts to add a duplicate department would result in the appropriate error message. Subsequently, I wrote the developer guide on the GitHub home page to provide a step-by-step process for running acceptance tests.

Below is an acceptance test I wrote to test the add function for departmental accounts:

```
// Test that ADD ITEM page appears after signing in with a departmental account and items can be added
test('Test that ADD ITEM page appears after signing in with a departmental account and items can be added', async (testController) => {
  // Sign in with departmental credentials
  await navBar.gotoSignInPage(testController);
  await signinPage.signin(testController, departmentCredentials.username, departmentCredentials.password);

  // Click the "ADD ITEM" link
  await testController.click(Selector('a').withText('ADD ITEM'));

  // Fill out the form to add an item
  await testController.typeText('input[name="name"]', 'Test Item');
  await testController.typeText('input[name="dateFound"]', '01/01/2024');
  await testController.typeText('input[name="locationFound"]', 'Test Location');
  await testController.typeText('input[name="currentDepartment"]', 'Test Department');
  await testController.typeText('input[name="image"]', 'https://www.picpedia.org/highway-signs/images/testing.jpg');

  // Submit the form by clicking the submit button
  await testController.click('input[type="submit"].btn.btn-primary');

  // Ensure success message is displayed
  const successMessage = Selector('div.swal-title').withText('Success');
  await testController.expect(successMessage.exists).ok();
});
```

## Lessons Learned

  Through working on this project, I gained a deeper understanding of the importance of meticulous testing in ensuring the reliability of software systems. Often, when one functionality fails, the entire system becomes impacted—inevitable considering the interconnected nature of software. By being tasked with addressing potential issues before they escalate, I was able to deepen both my quality assurance skills and my knowledge of the system itself. Aside from technical skills, I also honed my ability to collaborate effectively within a team and communicate technical concepts to everyday users. This project provided me with ample opportunities to practice interpersonal skills, such as active listening, constructive feedback, and conflict resolution—all crucial for successful teamwork. Additionally, I learned to adapt my communication style to suit different team members' preferences and expertise levels, fostering a more productive working environment.

  You can learn more about the UHM Lost and Found website at the [GitHub organization page](https://github.com/uhm-lost-and-found).
