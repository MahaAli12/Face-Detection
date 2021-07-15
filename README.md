# Face-Detection

Task3:part1
<b> Code</b>
import cv2

face_cascade = cv2.CascadeClassifier('haarcascade_frontalface_default.xml')

img = cv2.imread('m.jpeg')

gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)

faces = face_cascade.detectMultiScale(gray, 1.1, 4)

for (x, y, w, h) in faces:
    cv2.rectangle(img, (x, y), (x+w, y+h), (255, 0, 0), 2)

cv2.imshow('img', img)
cv2.waitKey()

![image](https://user-images.githubusercontent.com/85821857/125852607-4152b403-b55e-434f-a1f0-5927c6409173.png)

<b>Result</b>

![image](https://user-images.githubusercontent.com/85821857/125853011-be64694f-af08-4051-9195-47b8ac96afb1.png)

![image](https://user-images.githubusercontent.com/85821857/125853191-e38dac93-2f88-4352-ba30-d9d8347d34d4.png)


<b>Part2: Video</b>
<b>Code</b>

import cv2

face_cascade = cv2.CascadeClassifier('haarcascade_frontalface_default.xml')

cap = cv2.VideoCapture(0)

while True:

    _, img = cap.read()

    gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)

    faces = face_cascade.detectMultiScale(gray, 1.1, 4)

    for (x, y, w, h) in faces:
        cv2.rectangle(img, (x, y), (x+w, y+h), (255, 0, 0), 2)
    cv2.imshow('img', img)
    k = cv2.waitKey(30) & 0xff
    if k==27:
        break

cap.release()
<b>Result</b>
![image](https://user-images.githubusercontent.com/85821857/125854965-204f9728-2f1b-4455-a6dc-339f6e44d801.png)


![image](https://user-images.githubusercontent.com/85821857/125855481-cf27f92d-72a3-4e86-8980-fe17accf1d41.png)


