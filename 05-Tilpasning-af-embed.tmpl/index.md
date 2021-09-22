# Tilpasning af embed.tmpl

Standard templaten for indlejring hedder embed.tmpl. Dennes udseende kan til at vis grænse styres gennem et eksternt style-sheet. Hvordan eksterne style-sheets anvendes kan ses [her](https://vidi.readthedocs.io/en/latest/pages/standard/91_run_configuration.html#cssfiles). 

Typisk vil man gerne have fjernet visse knapper.

Her fjernes "Find mig", "Baggrundskort" og "Log ind" knapperne:

```css
#find-me-btn,
#base-layers-btn,
#session
{
    display:none !important;
}
```