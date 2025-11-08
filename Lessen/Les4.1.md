# Les 4.1

### Oefening 4.1 A : Coin Collector

![Unity](/GDV/img/Schermafbeelding%202025-11-08%20153913.png)
---
### Mijn script : Pickup
```
    private void OnTriggerEnter(Collider other)
    {
        if (other != null && other.CompareTag("Coin"))
        {
             Destroy(other.gameObject);
        }
    }
```

### Dit script doe je op Player en het werkt zo:

Wanneer het player in trigger gaat met een object die Tag : Coin heet dan word het die object met Tag : Coin verwijderd.

---