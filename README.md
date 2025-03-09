# Vehicle-Ride-Request-Forecast
Dataset & Business Challenge
Data File: https://drive.google.com/drive/folders/1DLhXd6tN9GHsLonqyDgRh5XXRasgYVCx?usp=sharing
Problem Statement
Ola Bikes is facing difficulties in meeting user ride requests, leading to customer dissatisfaction and business losses. A major challenge is the inefficient allocation of drivers, causing delays and unfulfilled rides. To improve service efficiency, the company aims to forecast ride demand in specific locations and time frames. This will help Ola deploy drivers strategically and enhance user experience.

Objective
The goal is to predict the number of ride requests for a particular latitude and longitude at a given future time window. Accurate demand forecasting will enable better resource management and optimize Ola's ride availability.

Dataset Overview
The dataset includes details about ride bookings, such as user information, timestamps, and geolocation (pickup and drop-off coordinates).

Data Fields
number → Unique user ID
ts → Ride booking timestamp (IST)
pick_lat, pick_lng → Pickup location (latitude & longitude)
drop_lat, drop_lng → Drop-off location (latitude & longitude)
Criteria for Valid Ride Requests
To ensure meaningful predictions, Ola's business team has set specific filtering rules for valid ride requests:

Duplicate Requests Handling:

If multiple bookings originate from the same location within 1 hour, only the first request is considered.
If multiple bookings occur within 8 minutes, only one request is counted, even if locations differ.
Fraud Detection:

Ride requests where the pickup and drop-off points are less than 50 meters apart are flagged as fraudulent.
System Errors:

Rides with pickup/drop-off locations outside India (bounding box: ['6.2325274', '35.6745457', '68.1113787', '97.395561']) are considered system errors.
Service Area Restrictions:

Ola prioritizes operations in Karnataka. Requests beyond 500 km geodesic distance from the state's boundary (['11.5945587', '18.4767308', '74.0543908', '78.588083']) are excluded.
