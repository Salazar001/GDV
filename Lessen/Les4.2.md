# Les 4.2

### Oefening 4.2 A : Coin Pickup Systeem

#### Dit was mijn Script:
```
    private void OnTriggerEnter(Collider other)
    {
        if (other != null && other.CompareTag("Coin"))
        {
            score++;
            Debug.Log("Munten: " + score);
            Destroy(other.gameObject);
        }
    }
```
Verschil van deze is dat ie elke keer het munt optelt in console.

---

### Oefening 4.2 B : Damage Zone Trigger

![Unity](/GDV/img/Schermafbeelding%202025-11-08%20160431.png)

### Dit was mijn Script :
```
using UnityEngine;

public class DamageZone : MonoBehaviour
{
    public int damagePerSecond = 10;

    private void OnTriggerStay(Collider other)
    {
        HealthStatus healthStatus = other.GetComponent<HealthStatus>();
        if (healthStatus != null)
        {
            healthStatus.health -= damagePerSecond * Time.deltaTime;
            healthStatus.health = Mathf.Max(healthStatus.health, 0); 
        }
    }


}
```
Het zorgt dat ie elke seconde damage krijgt en door ( ``` Public int damagePersecond = 10; ```) kan je het het in Unity bepalen hoeveel damage je krijgt elke seconden.