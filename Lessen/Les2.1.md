# Les 2.1

### Oefening 2.1 A : Draaiend muntje 

![Unity](/GDV/img/Schermafbeelding%202025-11-08%20143534.png)
---
### Dit was mijn script :
```
using JetBrains.Annotations;
using UnityEngine;
using UnityEngine.InputSystem.Controls;

public class TransformRotate1 : MonoBehaviour
{
    // Start is called once before the first execution of Update after the MonoBehaviour is created
    void Start()
    { }
         
       public float rotateSpeed = 100f;

    // Update is called once per frame
    void Update()
    {

        transform.Rotate(0,0,rotateSpeed * Time.deltaTime);

    }
    }
```
 Met (``` public float rotateSpeed; ```) Kan je het snelheid van muntje bewerken in
 Unity.

 En Time.deltaTime zorgt dat het snelheid op alle computers zelfde blijft dus niet bij trage computer langzaam en snelle computer snel.
 
 ---

### Oefening 2.1 B : Goomba

![Unity](/GDV/img/Schermafbeelding%202025-11-08%20145003.png)
---
### Dit was mijn script :
```
using UnityEngine;

public class GoombaMovement : MonoBehaviour
{
    public float moveSpeed = 2f; 
    public float moveDistance = 3f; 

    private Vector3 startPosition;

    public Transform pointA;    
    public Transform pointB;

    void Start()
    {
        startPosition = transform.position;
    }

    void Update()
    {
        float t = Mathf.PingPong(Time.time * moveSpeed, 1f);

        transform.position = Vector3.Lerp(pointA.position,pointB.position, t);
        //new Vector3(startPosition.x + offset, startPosition.y, startPosition.z);
    }
}
```
Ik heb 2 onzichtbare gameObjecten gemaakt pointA en pointB en allebei op 2 veschillende positions gezet zodat het goomba steeds van pointA naar pointB gaat en van pointB naar pointA. En Mathf.PingPong laat een getal op en neer gaan tussen twee waarden.

---
