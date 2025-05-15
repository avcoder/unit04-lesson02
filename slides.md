---
# You can also start simply with 'default'
theme: default
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: /assets/intro.jpg
# some information about your slides (markdown enabled)
title: Software Development | Foundations
info: |
  ## Software Development | Foundations
# apply unocss classes to the current slide
class: text-left
drawings:
  persist: false
transition: slide-left
mdc: true
---

# EJS
Full-Stack Development - part 2/8
- [ ] Continue Full-Stack Setup (MVC)
- [ ] EJS Syntax and Templating
- [ ] Incorporate Bootstrap

<div class="abs-br m-6 text-xl">
  <a href="https://github.com/slidevjs/slidev" target="_blank" class="slidev-icon-btn">
    <carbon:logo-github />
  </a>
</div>

<!--
-->

---
transition: slide-left
---

# Review

- MVC: Recap our folder structure
- EJS website: https://ejs.co/
- Foodtruck template Repo: https://github.com/avcoder/foodtruck-template


---
transition: slide-left
---

# GET all Foodtrucks

- in /controllers/truckController.js:
  ```js
  const getTrucks = async (req, res) => {
    const trucks = await truckHandler.getAllTrucks();
    res.render("trucks", { title: "All Trucks", trucks });
  };
  ```
- in /handlers/truckHandler.js:
  ```js
  const getAllTrucks = async () => {
    return await Truck.find().lean();
  };

  export default {
   getAllTrucks,
   createTruck
  }
  ```
- in /routes/router.js:
  ```js
  router.get("/", truckController.getTrucks);
  router.get("/trucks", truckController.getTrucks);
  ```
- create /views/trucks.ejs and /views/components/truck.ejs


---
transition: slide-left
---

# Add Bootstrap and EJS partials

- in app.js:
  ```js
  app.use(
    "/css",
    express.static(path.join(__dirname, "node_modules/bootswatch/dist/sketchy"))
  );
  app.use(
    "/js",
    express.static(path.join(__dirname, "node_modules/bootstrap/dist/js"))
  );
  ```
- in routes/router.js:
  ```js
  router.get("/", truckController.homePage);
  ```
- create /views/components/truck.ejs, header.ejs, footer.ejs, trucks.ejs

---
transition: slide-left
---

# Exercise

- Modify home.ejs such that it GETs all the foodtruck data (similar to trucks.ejs), but displays the data in the form of a Bootstrap table (columns may include: Truck Name, Description, Tags, Url, Edit, Delete)
- Remember to include any partials and/or components
- Edit button for each table row should be an anchor tag whose href = `/trucks/<_id from mongodb goes here>/edit`
- Delete button for each table row should be an anchor tag whose href = `/truck/<_id from mongodb>/delete`


---
layout: image-right
transition: slide-left
image: /assets/scott.png
backgroundSize: 400px 170px
class: text-left
---

# 10 minute break

🍦 Cool Tips, Trends and Resources:
- 🕑 [The Problem with Time & Timezones](https://www.youtube.com/watch?v=-5wpm-gesOY)
- 😬 [Next.js App Router Migration](https://www.flightcontrol.dev/blog/nextjs-app-router-migration-the-good-bad-and-ugly)
- 💾 [Surf the Web Like It's 1999](https://billsworld.neocities.org/)
- 🌶️ [HTMX](https://htmx.org/)

<br>
<hr>
<br>

- 🧪 [Enter anonymous lab questions](https://docs.google.com/forms/d/e/1FAIpQLSevvGARdHQikso-uLqFCO481MABKE5HofuSrlzEPMNQ2ZLykw/viewform?usp=dialog)
- ℹ️ [Course feedback survey](https://circuitstream.typeform.com/to/ZoyYk7px#course_id=SoftwareAN&instructor=9514)

<!-- 
- take attendance
-->

---
transition: slide-left
---

# GE

asdf

---
transition: slide-left
---

# Ad 

- create /views/components/truck.ejs, header.ejs, footer.ejs, trucks.ejs

---
transition: slide-left
---

# Exercise

asdf

---
transition: slide-left
---

# Homework

- Start working on your midterm note-taking app