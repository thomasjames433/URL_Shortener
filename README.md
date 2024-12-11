# Library System

This is a project that shortens long URLs and redirects short URLs to their corresponding long URL. It also tracks the number of times the site has been requested. Made using Django and Django REST Framework.

## Features:

- Gets hit count of each URL.
- Every 10th hit count redirects to an advertisement page (for now Google).
- A URL cannot be accessed more than 20 times a day.  

  - This project resets the daily hit count of a URL only when the redirect function is called the next day.  
  - Another repository of mine, **URL_Shortener_Celery**, uses Django-Celery and Redis to ensure that the daily-hit-count of every URL resets to 0 at midnight automatically. Deploying background workers (Celery) or a Cron-job would require a premium subscription; hence, I have not deployed it. The link to this project is given below:  
    - [URL_Shortener_Celery](https://github.com/thomasjames433/URL_Shortener_Celery)


## Functionality

#### shorten
 POST- The given long url is converted to a short one

#### redirect/:<shortUrl
  GET- Redirects the short url (6 character code) to its corresponding long url

#### details/:?url= <enter the url>
  GET- Auto identifies and gets the detail of the long/short url. Note(give "?url=" after "details/:")

#### top/:<int:number>
  GET- Returns a json with the rank of top number times urls based on their hitcounts


## Backend Hosted URL
The backend is hosted on render at 
#### https://url-shortener-sko8.onrender.com/


## To run the library system:

#### 1. Clone the repository:
   `git clone "https://github.com/thomasjames433/Library-system.git](https://github.com/thomasjames433/URL_Shortener.git"`
#### 2. Navigate into the project directory:
   `cd URL_Shortener`
#### 3. Install dependencies:
   - `pip freeze > requirements.txt`
   - `python manage.py makemigrations`
   - `python manage.py migrate`  
   - `To createsuperuser: python manage.py createsuperuser`
#### 4. Run the system:
   `python manage.py runserver`

## Technologies Used
- Django
- Django-Rest-Framework


## LICENSE
[MIT License](LICENSE)
