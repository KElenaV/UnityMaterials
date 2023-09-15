**Ресурс:** https://assetstore.unity.com/packages/tools/animation/dotween-hotween-v2-27676

**Документация:** http://dotween.demigiant.com/documentation.php

Библиотека для работы с DoTween: **using DG.Tweening**

## Действия
### DoMove
Плавное перемещение объекта из текущего положения на сцене в определенную точку (заданную координатами) в течение указанного времени.
##
Все 3 строчки идентичны
* **transform.DOMove(new Vector3(0, 4, 0), 3);**
* **transform.DOMove(new Vector3(0, 4, 0), 3).From();**
* **transform.DOMove(new Vector3(0, 4, 0), 3)From(false);**
* **From(false) значит IsRelative = false** - объект начинает движение со своего местоположения, и перемещается в координаты, указанные в DoMove. Координаты в коде - это глобальные координаты.
##
* **transform.DOMove(new Vector3(0, 4, 0), 3).From(true);**
* **From(true) значит IsRelative = true** - объект начинает движение с координаты (текущее положение + DoMove) и двигается к координатам в которых был расположен при запуске игры.