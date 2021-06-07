# DogPoundDatabase
The creation of database of a list of dogs that are seen by a examiner, with a second database created for keeping track of dogs' visits.

DROP TABLE IF EXISTS visits, dogs;

CREATE TABLE dogs (dogID int PRIMARY KEY AUTO_INCREMENT, breed char(10), name char(10));

INSERT into dogs values(1,'male','Wolf');
INSERT into dogs (breed, name) values('female','Isabelle');
INSERT into dogs (breed, name) values('male','Pit');
INSERT into dogs (breed, name) values('female','Virginia');
INSERT into dogs (breed, name) values('male', 'By-Tor');

DESCRIBE dogs;

SELECT * FROM dogs;

CREATE TABLE visits (visitID int PRIMARY KEY AUTO_INCREMENT, dogID int, d DATE,  FOREIGN KEY (dogID) REFERENCES dogs(dogID));

INSERT into visits values(1, 1, '2019-03-19');
INSERT into visits (dogID, d) values(2, '2019-03-20');
INSERT into visits (dogID, d) values(3, '2019-03-21');
INSERT into visits (dogID, d) values(4, '2019-03-22');
INSERT into visits (dogID, d) values(5, '2019-03-23');
INSERT into visits (dogID, d) values(1, '2019-03-24');
INSERT into visits (dogID, d) values(3, '2019-03-25');
INSERT into visits (dogID, d) values(5, '2019-03-26');

DESCRIBE visits;

SELECT * FROM visits;

ALTER TABLE visits add (t TIME);

UPDATE visits SET t = '10:00' WHERE visitID = 1;
UPDATE visits SET t = '11:00' WHERE visitID = 2;
UPDATE visits SET t = '2:00' WHERE visitID = 3;
UPDATE visits SET t = '3:15' WHERE visitID = 4;
UPDATE visits SET t = '11:00' WHERE visitID = 5;
UPDATE visits SET t = '10:00' WHERE visitID = 6;
UPDATE visits SET t = '2:00' WHERE visitID = 7;
UPDATE visits SET t = '11:00' WHERE visitID = 8;

SELECT * FROM visits;
