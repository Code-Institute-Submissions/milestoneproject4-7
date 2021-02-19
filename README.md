## Existing Features

1. The Navbar - The navbar is a fully responsive navigational element. It will be seen on all pages. It contains links to the login, the Bicycles page and the shopping cart. There is a search bar on it.

2. The Home Page - The Home page is the opening page.

3. The Bicycles Page - There you see a number of images which display either a bicycle rental, a Bicycle group tour, Bicycle services or Bicycle gear. Each image comes with a brief description of itself and the price. 

4. Bicycles Details Page - Each image on the Bicycles Page can be tapped on to reveal a full page with the image and a more detailed text about what comes with that image.

5. Login - A place where the user can log in.

6. Cart Page - A page which adds up the cost of rentals and purchases and charges the customer. 

## Technology Used

1. HTML - the standard markup language for documents designed for display on a web browser.
2. CSS - a style sheet language used for the presentation of a markup language.
3. JavaScript - a programming language.
4. Python - a general purpose programming language.
5. Django - a Python-based free and open-source web framework.
6. JQuery - a JavaScript library.
9. AWS S3 - a service that provides object storage through a web-service interface.
10. Heroku - a cloud platform as a service supporting several probgramming languages.
11. Unsplash & Pixabay - two services that provide free jpeg images.

## Testing

### Responsiveness on different Browsers and Mobiles

The program was tested on a HP Laptop 15-db1xxxx and on a Android Version 9 smartphone. 

The program looks fine and is responsive only on the Google Chrome browser.

The github page was not fully functional on the Microsoft Edge or the Firefox browser.

## Deployment

### Local Deployment

Requirements: 
1. Installed Python on your environment 
2. An AWS account with S3 bucket setup
3. An Stripe account

Environment variables:

    * SECRET_KEY = secret key for django app
    * DEVELOPMENT = "True" variable to set Debug to True, also will use console.EmailBackend
    * EMAIL_HOST_USER = User for live emails
    * EMAIL_HOST_PASS = Password for live emails
    * DATABASE_URL = with youre link to databse if not setup local sqlite3 will be used
    * STRIPE_PUBLIC_KEY = Public key from Stripe
    * STRIPE_SECRET_KEY = Secret key from Stripe
    * STRIPE_WH_SECRET  = Webhook secret key from Stripe
    * USE_AWS  = True to use static and media files from S3 account
    * AWS_ACCESS_KEY_ID = AWS Access Key Id
    * AWS_SECRET_ACCESS_KEY = AWS Secret Access Key

1. Open Console navigate to directory project will be created.
2. Get a local copy : "git clone https://github.com/xz3t/milestone-4.git"
3. Install the requirements: "pip3 install -r requirements.txt"
4. Create a superuser: python3 manage.py create superuser
5. Set up database: "python3 manage.py makemigrations" , "python3 manage.py migrate"
6. For a copy of products: "python3 manage.py loaddata products"
7. For a copy of events: "python3 manage.py loaddata events"
8. For a copy of about: "python3 manage.py loaddata about"
9. If using AWS set up all variables and copy media/ folder to your S3 bucket
10. Run locally: python3 manage.py runserver

### Deployment to Heroku

1. Login to Heroku.
2. Click on New button.
3. Click on Create New App and name it.
4. Choose geographical region.
5. Go to Github Terminal and create a requirements.txt by running the command pip3 freeze --local > requirements.txt.
6. Create Procfile by running the command echo web: python app.py > Procfile.
7. Push each file to the staging area.
8. Go back to Heroku and click on Deploy.
9. Go to Deployment Method and click on Connect to Github.
10. Add the repository name and click on Search.
11. Once it finds the repository click on Connect.
12. Click on Settings and then Reveal Config Vars.
13. Go back to Deploy and click on Enable Automatic Deploys.
14. Click on Deploy Branch and wait for the message that the app was deployed.
15. Click on View to launch the Deployed app. 
16. In Config Vars enter:
        a. from Heroku, the Postgres url   e. USE_AWS
        b. my own SECRET_KEY               f. the STRIPE_PUBLIC_KEY
        c. the AWS_ACCESS_KEY              g. STRIPE_WH_SECRET
        d. the AWS_SECRET_ACCESS_KEY
