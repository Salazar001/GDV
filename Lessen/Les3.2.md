# Les 3.2


### Oefening 3.2 A : Muziek Speler 

![Unity](/GDV/img/Schermafbeelding%202025-10-02%20222705.png)

---
### Dit is mijn script :
```
using Unity.VisualScripting;
using UnityEngine;

public class MusicPlayer : MonoBehaviour
{
    public string currentSong = "";
    public bool isPlaying = false;
    public float volume = 1.0f;
    public bool IsMuted = false;

    void Start()
    {
        // Voorbeeld van functies aanroepen
        PlaySong("Minecraft OST - Sweden");
        Debug.Log("Current song: " + GetCurrentSong());

        SetVolume(0.8f);
        Debug.Log("Volume set to: " + volume);

        Debug.Log("Is playing: " + IsPlaying());

        StopSong();
        Debug.Log("Is playing: " + IsPlaying());
    }




    void Update()
    {
        // Toetsen gebruiken om functies aan te roepen
        if (Input.GetKeyDown(KeyCode.P))
        {
            PlaySong("Custom Song");
        }
        if (Input.GetKeyDown(KeyCode.S))
        {
            StopSong();
        }
        if (Input.GetKeyDown(KeyCode.V))
        {
            SetVolume(Random.Range(0f, 1f));
            Debug.Log("Volume set to: " + volume);
        }
    
        if (Input.GetKeyDown(KeyCode.M))
        {
            SetMute(false);
        }
    }
    
 
   
    
    
    
    public void PlaySong(string songName)
    {
        currentSong = songName;
        isPlaying = true;
        Debug.Log("Playing song: " + currentSong);
    }

    // Functie om te stoppen
    public void StopSong()
    {
        Debug.Log("Song stopped.");
        currentSong = "";
        isPlaying = false;
    }

    // Functie om volume te zetten
    public void SetVolume(float newVolume)
    {
        volume = Mathf.Clamp01(newVolume); // Zorgt dat volume altijd tussen 0 en 1 blijft
    }

    // Functie om huidige songnaam terug te geven
    public string GetCurrentSong()
    {
        return currentSong;
    }

    // Functie om te checken of er iets speelt
    public bool IsPlaying()
    {
        return isPlaying;
    }

   public void SetMute(bool muted)
    {
        IsMuted = muted;
        Debug.Log("Mute: " + IsMuted);
    }

}
```