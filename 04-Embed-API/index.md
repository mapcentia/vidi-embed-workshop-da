# Embed API

Embed scriptet udstiller et API, så det er muligt at ændre Vidi’s tilstand og definere callback funtioner fra den hjemmeside det er indlejret på.  

For at anvende API'et skal den indlejrede Vidi navngives, så det er muligt at henvise til den (der kan jo være flere indlejrede kort på samme side). Det gøres med data-attributten `data-vidi-frame-name`. 

Pt. er der to funktioner udstillet gennem API’et:

* `embedApi.switchLayer` Tænder/slukker et lag
* `embedApi.allOff` Slukker alle tændte lag

Disse kan bruges til at indsætte knapper på hjemmesiden, som tænder og slukker region-laget. Samt en knap, som slukker alle lag.


    ```html
    <button onclick='javascript: embedApi.switchLayer("public.region", true, "workshop")'>Tænd Regioner</button>
    <button onclick='javascript: embedApi.switchLayer("public.region", false, "workshop")'>Sluk Regioner</button>
    <button onclick='javascript: embedApi.switchAllOff("workshop")'>Sluk alle lag</button>
    ```
   
## Callbacks
Callbacks kan anvendes til automatisk at kalde API metoder, efter Vidi og lag er færdig-loaded. Fx: Hvis hjemmesiden i visse tilfælde automatisk skal tænde for et lag, kan dette først gøres efter Vidi er indlejret og klar.  

Det muligt at definere callback funktioner for:

1. Når Vidi er loaded og klar.
2. Når aktive lag fra projektet er loaded. (Et projekts aktive lag loades først efter Vidi har meldt loaded og klar.)   

Dette gøres således:

    ```javascript
    embedApi.vidiReady["workshop"] = () => {
        Alert("Vidi er klar")
    }

    embedApi.activeLayersReady["workshop"] = () => {
        alert("Aktive lag er klar")
    }
    ```

