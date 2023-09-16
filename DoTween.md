**Ресурс:** https://assetstore.unity.com/packages/tools/animation/dotween-hotween-v2-27676

**Документация:** http://dotween.demigiant.com/documentation.php

Библиотека для работы с DoTween: **using DG.Tweening**

## Действия - Задаются в Start()

### DoMove
Плавное перемещение объекта на сцене в течение указанного времени.
###
Все 3 строчки идентичны
* **transform.DOMove(new Vector3(0, 4, 0), 3);**
* **transform.DOMove(new Vector3(0, 4, 0), 3).From();**
* **transform.DOMove(new Vector3(0, 4, 0), 3)From(false);**
* **From(false) значит IsRelative = false** - объект начинает движение со своего местоположения, и перемещается в координаты, указанные в DoMove. Координаты в коде - это глобальные координаты.
###
* **transform.DOMove(new Vector3(0, 4, 0), 3).From(true);**
* **From(true) значит IsRelative = true** - объект начинает движение с координаты (текущее положение + DoMove) и двигается к координатам в которых был расположен при запуске игры.
##

### DoRotate
Плавное вращение объекта на сцене в течение указанного времени.
###
**transform.DORotate(new Vector3(0, 360, 0), 2, RotateMode.FastBeyond360).SetLoops(-1, LoopType.Restart).SetEase(Ease.Linear);**
* **RotateMode.FastBeyond360** - отлично подходит для бесконечного вращения объекта вокруг
* **SetLoops(-1, LoopType.Restart)** - (-1) задает бесконечный цикл действий, любая другая цифра будет обозначать количество повторений, LoopType - может быть 3 видов: **Restart**, **Yoyo**, **Incremental**
* **SetEase(Ease.Linear)** - задает характер движения. Если нужно, чтобы движение было равномерным без ускорений, замедлений - выбираем **Linear**. Если не установить данную настройку, то движение будет неравномерным - замедлятся в конце цикла и в начале вновь ускоряться.

##
### DoScale
Плавное изменение размера объекта на сцене в течение указанного времени.
###
**transform.DOScale(0.5f, 1f).SetLoops(-1, LoopType.Yoyo);**
* 0.5f - как изменяется размер относительно начального
* 1f - скорость изменения

##
### DoColor
Плавное изменение цвета материала объекта на сцене в течение указанного времени. В 3D объектах эта функция меняет цвет материала, в 2D - SpriteRenderer
###
3D

**private Material _material;

   private void Start()

   {

      _material = GetComponent<MeshRenderer>().material;

      _material.DOColor(Color.blue, 1).SetLoops(-1, LoopType.Yoyo);

   }**
###
2D

* **[SerializeField] private SpriteRenderer _renderer;
* _renderer.DOColor(Color.red, 2f).SetLoops(-1, LoopType.Yoyo);**
