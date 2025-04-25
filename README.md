# Random Restaurant Picker Nearby

## ✅ Required Features

The following **required** functionality is completed:

- [ ] App fetches a list of nearby restaurants using the Yelp API  
- [x] Restaurants are displayed in a `UITableView` with name, category, and distance  
- [x] App uses tab navigation to switch between the restaurant list and random picker  
- [x] Clicking a table cell expands to show full restaurant information (multiline label)  
- [x] A "Pick Random" tab button selects a restaurant and displays its name  
- [ ] Yelp data is fetched and displayed using HTTPS with an API key  
- [ ] Basic error handling and API failure cases are accounted for  


## Table of Contents

1. [Overview](#overview)
2. [Product Spec](#product-spec)
3. [Wireframes](#wireframes)
4. [Schema](#schema)

## Overview

### Description

**Random Restaurant Picker Nearby** is a mobile app that helps users quickly decide where to eat by using their location to fetch nearby restaurants and letting them either scroll through the list or press a button to get a random suggestion. It’s a playful tool to solve the common “where should we eat?” dilemma.

### App Evaluation

- **Category:** Food & Drink, Lifestyle  
- **Mobile:** ✅ Leverages GPS/location, possibly map view, and can use device sensors (e.g., shake to randomize)  
- **Story:** ✅ Everyone struggles with food indecision—this app makes that decision process quick, fun, and social  
- **Market:** ✅ Large user base (anyone who eats out), with potential niche targeting (e.g., local college students, budget foodies)  
- **Habit:** ➖ Medium. Likely used occasionally, but repeatedly in group settings or when in a rush  
- **Scope:** ✅ Core features are manageable for MVP; scalable with more filters, integrations, or social elements  

## Product Spec

### 1. User Stories (Required and Optional)

**Required Must-have Stories**
- User can grant location permission and see a list of nearby restaurants
- User can tap a button to receive a random nearby restaurant suggestion
- User can view basic restaurant info (name, distance, category)
- User can refresh the list

**Optional Nice-to-have Stories**
- User can shake the phone to pick a random restaurant
- User can filter restaurants (e.g., distance, cuisine, rating)
- User can view restaurant on a map
- User can share a restaurant suggestion with a friend
- User can "favorite" restaurants

### 2. Screen Archetypes

- **Restaurant List Screen**
  - User sees a scrollable list of nearby restaurants
  - User can refresh list manually

- **Random Pick Screen**
  - User taps a button to generate a random restaurant from the list
  - Restaurant info is shown with a fun animation

- **Restaurant Detail Screen**
  - User can view details like address, category, distance
  - (Optional) Tap to open in Maps

### 3. Navigation

**Tab Navigation**
- Nearby (list of restaurants)
- Random (random picker)
- Favorites (optional)

**Flow Navigation**
- Nearby List Screen  
  → Random Picker  
  → Restaurant Detail  

- Random Pick Screen  
  → Restaurant Detail  

- Restaurant Detail Screen  
  → External Maps app (e.g., Apple Maps)

## Wireframes

*(Add picture of your hand sketched wireframes in this section)*  
`<img src="YOUR_WIREFRAME_IMAGE_URL" width=600>`

### [BONUS] Digital Wireframes & Mockups

*(Add if you're doing Figma or SwiftUI previews)*

### [BONUS] Interactive Prototype

*(Optional - e.g., link to a Figma prototype)*

## Schema

*(This section will be completed in Unit 9)*

### Models

**Restaurant**
| Property   | Type   | Description                 |
|------------|--------|-----------------------------|
| id         | String | Unique identifier           |
| name       | String | Name of restaurant          |
| location   | String | Address or coordinates      |
| category   | String | Type of cuisine             |
| distance   | Float  | Distance from user          |
| isFavorite | Bool   | Optional flag if favorited  |

### Networking

- **Nearby List Screen**
  - `GET` request to fetch restaurants near user's location (e.g., via Yelp API)

- **Random Pick Screen**
  - Uses local array of fetched restaurants to randomly select one

- **Restaurant Detail Screen**
  - Uses selected restaurant info; no additional requests needed

**Yelp API Examples:**
- `GET /businesses/search?term=food&latitude=...&longitude=...`
- `GET /businesses/{id}`
  
