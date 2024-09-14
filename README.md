# Travel-Tide
Travel Tide is a data-driven project aimed at analyzing user behavior on a travel booking platform, focusing on sessions, flight bookings, hotel stays, and browsing patterns to gain actionable insights.  
#  Objective

The primary goal of this SQL script is to identify and classify user behaviors based on various travel-related metrics, including flight booking patterns, hotel preferences, browsing behavior, and overall usage of discounts and perks. The users are grouped and scaled using these metrics to generate indices and eventually classify users into specific categories like "Bargain Hunter," "Luxury Traveler," etc. The final output combines user demographic data with these behavioral insights.

## 2. Key Steps Involved

Filtering Sessions for 2023 (sessions_2023)
The data is restricted to sessions that started after January 4th, 2023, to focus on recent user activity.
Filtering Frequent Users (filtered_users)
Users with more than 7 sessions during the defined period are selected for further analysis.
### Flight Metrics Calculation (flight_metrics)
**Discount Flight Proportion:** The percentage of flights booked with discounts.
**Average Flight Discount:** The average discount amount per flight.
**ADS (Average Dollars Saved) per KM:** Calculated using the flight discount amount and the distance traveled using the Haversine distance formula.
**Average Checked Bags:** The average number of checked bags.
**Total Free Checked Bags:** Sum of free checked bags.
**Total Distance Traveled:** Total kilometers flown by the user.
**Total Discounted Trips:** Number of trips where a flight discount was applied.
**Total Flights Booked:** The total number of flights booked by the user.
**Average Seats Booked:** The average number of seats booked per flight, useful for identifying family travelers.
### Browsing Metrics Calculation (browsing_metrics)
**Average Session Time:** The average duration of a user session.
**Total Page Clicks:** Sum of the clicks made by the user.
**Conversion Rate:** The percentage of sessions that resulted in a flight being booked.
### Hotel Metrics Calculation (hotel_metrics)
**Total Hotel Spending:** Total expenditure on hotels.
**Average Cost Per Night:** Average cost per hotel room per night.
**Average Rooms Booked:** The average number of hotel rooms booked by the user.
**Total Nights:** The total number of nights stayed in hotels.
### Perks Summary (perks_summary)
**Cancellation Preference:** Counts how often a user prefers cancellations.
**Flight Discount and Hotel Discount Lover:** Determines whether a user frequently books discounted flights or hotels.
**Frequent Traveler:** Flags frequent travelers based on the total distance traveled.
**Family Traveler:** Flags users who consistently book more than one seat.
**Average Rooms Booked:** Tracks the number of rooms per booking for hotel stays.
### Combining Metrics (combined_metrics)
Merges flight, hotel, and browsing metrics into a single comprehensive dataset, ensuring that all relevant features are represented even if a user didn’t engage in one activity (e.g., booked hotels but not flights).
### Scaling the Metrics (scaled_metrics)
All calculated metrics are scaled between 0 and 1 for comparability. This ensures that different metrics are normalized so they can contribute equally to indices.
Key scaled metrics include the discount flight proportion, average flight discount, ADS per KM, average checked bags, session time, page clicks, and conversion rate.
### Final Indices and Classification (final_metrics and combined_final)
**Bargain Hunter Index:** Combines scaled metrics that focus on the user’s tendency to hunt for discounts.
**Flight Index:** A comprehensive score based on flight-related behavior.
**Browsing Index:** Measures engagement based on session time, clicks, and conversions.
**Hotel Index:** Measures hotel-related behavior like average cost per night and rooms booked.
**User Group Classification:** Categorizes users into groups such as Luxury Traveler, Bargain Hunter, Frequent Traveler, Family Traveler, or Comfort Seeker, based on their behavior.
**Preferred Perk:** Determines the user’s most preferred perk, such as free cancellation, exclusive flight/hotel discounts, or free checked bags.
### Final Output
The final output merges the behavioral insights with user demographic data such as birthdate, gender, marital status, home location, etc. This provides a holistic view of the user, both demographically and behaviorally.
## 3. Assumptions

**Session Data:** Only users with more than 7 sessions are considered "frequent users," implying that these users are more engaged.
**Flight and Hotel Discount Behavior:** Users who repeatedly book flights or hotels with discounts are classified as "Discount Lovers."
**Family Travelers:** Users who consistently book more than one seat are assumed to be traveling with family or in groups.
**Free Cancellation:** Users with a significant number of cancellations are assumed to prefer free cancellation options.
**Frequent Travelers:** Users who travel more than 4000 km per discounted trip are flagged as frequent travelers.
## 4. Observations

**Comprehensive Metrics:** The script calculates an extensive set of metrics for flights, hotels, and browsing, allowing for deep behavioral insights.
**User Group Classification:** The classification model provides a user profile that can be used for personalized marketing or tailored perks.
**Scalability:** By normalizing the metrics, the model ensures scalability and comparability between different types of behaviors.
## 5. Recommendations

**Personalized Offers:** Use the output classification to target users with personalized travel offers or loyalty perks based on their preferred behavior (e.g., offering discounted flights to "Bargain Hunters").
**Improved User Engagement:** Based on browsing behavior (clicks, session time), targeted content can improve the conversion rate, especially for those flagged as high-potential converters.
**Family Travel Packages:** Consider offering family travel packages for users classified as "Family Travelers" based on their seat booking patterns.
## 6. Conclusion

This SQL script provides a detailed, data-driven approach to understanding user behavior in a travel context. By combining metrics across multiple dimensions (flights, hotels, and browsing), the model can effectively classify users into distinct groups and identify key behavioral patterns that can be leveraged for marketing, retention, and personalized user experiences.

## Resources:
- [Presentation ](https://www.canva.com/design/DAGQAMlsxF8/fxk64LCzDlq4Fh5RV8yg1Q/edit?utm_content=DAGQAMlsxF8&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton)
- Dashboard [
](https://public.tableau.com/views/BehaviorIndicesClustering/TravilTide?:language=en-GB&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link) in Tableau
