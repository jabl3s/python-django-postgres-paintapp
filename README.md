=== Creation / edits have been made by jabl3s here ===  
  
Note, when serving static content like images or gif django is less prefered, ideally use s3 bucket or whatever like in my aws project, then simply link to with href...  
  
/django/app/app/forms.py  
/django/app/app/urls.py  
/django/app/app/models.py  
/django/app/app/settings.py ==> only tweaks have been made here, further tweaks need to be made to hide .envs for this .py file.  
/django/app/app/veiws.py  
/django/app/app/static/gif/room.gif  
/django/app/app/templates/((home, index, roomsview, roomview, roomsadd)).html  
/django/app/app/migrations/((0001...,0002...0003...,)).py ==> can simply run django migrations to interact with postgres database, in past ive manually had to update entries in postgres production environments for sentry users to get them access at old workspace.  

=== THE TASK ===  
  
Django + postgres  ==> Ive configured django with postgres in such a way that any room created by the app is stored in the postgres databse just as width, height, depth and slug. This allows for my django model to operate freely on this information to get volume etc etc. This url-slug is also all the information that is needed in store to dynamically create the page to view/update individual rooms width, height, depth information in the database. 
  
This django app creates and stores as many rooms as the slug randomness or database size constraints for width height depth slug allows, so quite a lot knowing postgres with such minimal info.     
  
=== USEFUL COMMANDS ===  
DOCKER_BUILDKIT=1 docker build . -t jabl3s/paintapp-django-armv8  
docker build . -t jabl3s/paintapp-django-armv8 --platform linux/arm64/v8  
docker push jabl3s/paintapp-django-armv8  

  
