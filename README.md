# Device-Agnostic Design Course Project I - 12563757-9152-41de-aa81-953971bc4df1

Name of the application:
QuizApp

Brief description of the application:
QuizApp allows users to choose a topic and get questions from that topic that they can answer to by choosing between the different options that are provided. Once they select the correct answer they can go to the next question. The number of total correct answers and correct answers by topic is saved in the statistics page and persisted by the application. Users can also select the general practice option and be asked questions from the topic where they have the lowest amount of correct answers.

3 key challenges faced during the project:
* The first challenge was to understand how to pass some data to the FutureProvider that was going to be used to fetch the questions from the API. Initially, I had to use a StateProvider to store the topic id and then read it from the FutureProvider, later I discovered about the .family provider modifier and I used that one.
* The second challenge was to cancel the state in the question page. I had to use StateProviders in the question page to store the chosen answer and whether it was correct, however this data remained saved when the user left the page. I had to solve it by using .autoDispose to cancel the state when the user left the page.
* The third challenge was to persist the statistics data. I decided to use a map to store the statistics by topic, but I had to convert the map and order it every time before saving it. I tried to use data structures that would keep the map ordered, but I did not manage to do that. To solve this, I wrote a function that orders the map every time before it is stored.

3 key learning moments from working on the project:
* I learned how to use the .family provider modifier to create FutureProviders that change based on a parameter.
* I learned how to save data in the device using the shared_preferences package and retrieve it correctly.
* I learned how to reset the state when a user leaves a page so that it does not influence the future interactions with the page. 


list of dependencies and their versions:
dependencies:
  flutter:
    sdk: flutter
  cupertino_icons: ^1.0.2
  go_router: ^11.1.2
  flutter_riverpod: ^2.4.4
  shared_preferences: ^2.2.1
  http: ^1.1.0

dev_dependencies:
  flutter_test:
    sdk: flutter
  flutter_lints: ^2.0.0
  test: any
  nock: ^1.2.3
  http_mock_adapter: ^0.4.2