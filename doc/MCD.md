# Creation du MCD

## Analyse des entités

- User
  - firstname
  - lastname
  - email
  - password
  - rôle

- Spécialities
  - name

- Workout
  - date
  - content

- Comment
  - content

- Health-check
  - weigh
  - muscular mass
  - fat mass
  - bone mass
  - water mass

- Meeting
  - date
  - start time
  - end time
  
## Analyse des associations entre entité


### User <-> Coaching

Un User(Coach) _dirige_ ou (adhérent) _prend part_ à 0 Meeting au minimum ou N Meeting au maximum : 0N
Un Coaching _est relié_ avec 1 User(Coach) au minimum ou 1 User au max : 11
Un Coaching _est choisi_ par 0 User(adhérent) au minimum ou 1 user au max : 01 

## USer <-> Spéciality

Un User (Coach) _possède_ 0 spécialité au minimum et N spécialités au maximum : 0N
Une spécialité _est possédée_ par 1 User(Coach) au minimum et N Coach au maximum : 0N

## User <-> Comment

Un User(coach) peut _écrire_ 0 commentaire au minimum ou N commentaire au maximum : 01
Un Comment est _écrit_ par 1 User au min ou 1 User au maximum : 11


### User <-> Workout

Un User (adhérent)_effectue_ 0 Workout au minimum et N Workout au maximum : 0N
Un Workout est _écrit_ par 1 Adhérent au minimum ou 1 User(adhérent) au maximum : 11

## Workout <-> Health-check

Un Workout _s'associe_ avec 0 Health-check au minimum et 1 Health-check au Max : 01
Un Health-check est _associé_ avec 1 Workout au minimum et 1 Workout au Maximum: 11

### Workout <-> Comment

Un Workout _contient_ 0 comment au minimum, et 1 commentaire au maximum: 01
Un commentaire _décrit_ 1 Workout au minimum et 1 Workout au maximum: 11

## MCD ( Mocodo)

Match, 11 Comment, 01 Workout
Comment: content
WRITE, 0N User, 11 Comment
TAKE PART IN, 0N User, 01 Coaching
Coaching: date, start time, end time

Workout : date, content
DO, 0N User, 11 Workout
User: firstname, lastname, email, password, role
LEAD, 0N User, 11 Coaching
:

MATCH, 01 Workout, 11 Health-check
Health-check: weight,muscular mass, fat mass, bone mass, water mass
HAVE, 0N User, 0N Speciality
Speciality:name
