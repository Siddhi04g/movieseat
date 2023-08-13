# A Completed Functional Flutter App - FindSeat (BLoC + Json API + Unit Test + Firebase Auth)

## II. Showcase
#### 2.1. Home
In Home screen, it just simply load then show data to UI
 2.1.1. Screen: Home 1
 2.1.2. Screen: Home 2
 2.2. All Shows
 ##2.2.1. Screen: All Shows 1
- (1) click to open search field. Basically support search by name
- (2) click to open sort option. Basically support sort by rating and name
- (3) there’re 3 tabs: Now showing, Coming soon and Exclusive. You can swipe left/right to view content of each tab
- (4) Display list show in gridview
###### 2.2.2. Screen: All Shows 2
- Sort options dialog
###### 2.2.3. Screen: All Shows 3
- App will perform search after stop typing for 400 milliseconds, technically it’s debounce technique.
Try to click on item, app will open Show details screen
#### 2.3. Show info
### 2.3.1. Screen: Show Info 1
- (1) is trailer of show from Youtube link
- (2) show’s description
- (3) is offer section. This is not static content, it can be changed in mock API
###### 2.3.2. Screen: Show Info 2

- (4) is user’s review section. Basically write review function is not available yet
- (5) is casts section. It’s horizontal listview, you can swipe to reach more content.
- (6) Click Book seats then app will open Book Time Slot screen
#### 2.4. Book Time Slot
###### 2.4.1. Screen: Book Time Slot 1
- (1) Click to open search field. Basically support search by Cine’s name
- (2) List cine with time slots. Gray item is time slot that is not available.
###### 2.4.2. Screen: Book Time Slot 2

- App will perform search after stop typing for 400 milliseconds, technically it’s debounce technique.
Click on item time slot, app will open Book Seat Type screen.
#### 2.5. Book Seat Type

- (1) choose number of seats
- (2) choose seat type
#### 2.6. Book Seat Slot

- (1) is count of number booked seats
- (2) Booked seats. You can click to select then click again to deselect seat.
- Validate: For example in screen Book Seat Type you chosen 3 seats, type is Jack that mean
  - You cannot select Queen or King seat
  - You cannot book more than 3 seats
#### 2.7. Make payment
###### 2.7.1. Screen: Make payment 1

- App integrated with Stripe SDK, currently for testing when you click on any method Debit/UDI/Net banking, app only show option pay by input card to the form.

###### 2.7.2. Screen: Make payment 2
- For testing, please use following information:
  - Card number: 4242 4242 4242 4242
  - Expiration date: 04/24
  - CVC: 424 or 242
###### 2.7.3. Screen: Make payment 3
- After Stripe verified the payment information, app will show your booking information.
#### 2.8. Login
- Basically app provide login by user’s email and password. Login by Google and Facebook will be available soon.
- Test account: khoaha+dev2@mailinator.com / 123456
#### 2.9. Register
- I did validation in this form using Bloc pattern, you can look at this to study how to do form validation in Bloc.

## III. Mock API
https://integer.sgp1.digitaloceanspaces.com/findseat

API | Usage
------------ | -------------
/home.json | Return data for Home screen
/all_shows_by_type.json | Return data for All Shows screen
/booking_time_slot_by_cine.json | Return data for Book Time Slot screen
/book_seat_slot_by_time_slot.json | Return data for Book Seat Slot screen

## IV. Plugins
Plugin | Usage
------------ | -------------
[retrofit](https://pub.dev/packages/retrofit#-readme-tab-) | For working with restful API, generated model
[json_annotation](https://pub.dev/packages/json_annotation#-readme-tab-) | Same as above (SAA)
[dio](https://pub.dev/packages/dio) | SAA
[build_runner](http://build_runner) | SAA
[flutter_bloc](https://pub.dev/packages/flutter_bloc) | For build app architecture
[carousel_slider](https://pub.dev/packages/carousel_slider#-readme-tab-) | Use for section banner in Home screen
[freezed](https://pub.dev/packages/freezed) | Working with State of bloc
[equatable](https://pub.dev/packages/equatable) | SAA
[meta](https://pub.dev/packages/meta) | SAA
[intl](https://pub.dev/packages/intl) | Format date time and other formats
[youtube_player_flutter](https://pub.dev/packages/youtube_player_flutter) | Display trailer from Youtube link
[shared_preferences](https://pub.dev/packages/shared_preferences) | For caching user’s session
[flutter_svg](https://pub.dev/packages/shared_preferences) | Display svg icon
[google_maps_flutter](https://pub.dev/packages/google_maps_flutter) | Display address of cine
[dotted_border](https://pub.dev/packages/dotted_border) | Display dot border of offer ticket in Show details screen
[shimmer](https://pub.dev/packages/shimmer) | Animate image place holder
[stripe_payment](https://pub.dev/packages/stripe_payment) | Use in booking feature
[firebase_core](https://pub.dev/packages/firebase_core) | For register account and login using Firebase
[google_sign_in](https://pub.dev/packages/google_sign_in) | SAA
[firebase_auth](https://pub.dev/packages/firebase_auth) | SAA
[test](https://pub.dev/packages/test) | Try to use unit testing, most of the cases come from Bloc
[bloc_test](https://pub.dev/packages/bloc_test) | SAA


Before run project, execute commands:
- `flutter clean`
- `flutter pub get`
- `flutter pub run build_runner build` or `flutter pub run build_runner build --delete-conflicting-outputs`
- `flutter run` (if needed)


