# Fundstücke
Code-Qualität ist wichtig und siche auch immer eine gewisse Frage des Geschmacks. 
Doch andereseits gibt es Fälle nach der Regel: _es genügt, wenn es compiliert!_.

Im RL findet man Beispiele für Code den man sich nicht ausdenken könnte.

``` C#
// Auzug einer Methode in C#
string Template = "";
string TemplateSpace = @"\" +  @"""";
…
TemplateSpace = TemplateSpace.Remove(0,1);
…
Template = GetTemplateRoot("Deutsch");
…
if (Template.Contains(TemplateSpace))
   Template = Template.Replace(TemplateSpace, "");
```

Kommentiert 
``` C#
// Auzug einer Methode in C#
string Template = "";  // Kleinschreibung von Variablen verletzt 
string TemplateSpace = @"\" +  @"""";  // '+' kann aufgelöst werden = \" kleinschreibung von Variablen verletzt - Irreführende Bezeichnung "Space"
…
TemplateSpace = TemplateSpace.Remove(0,1); // kann initial gemacht werden: …lateSpace = "\""; Hier wird nun erst klar das TemplateSpace ein "Quote" ist.
…
Template = GetTemplateRoot("Deutsch");  // hier wird ein Pfad zum Template zurückggegeben also GetTemplatePath
…
if (Template.Contains(TemplateSpace))  
   Template = Template.Replace(TemplateSpace, ""); "
```
Kurzfassung
``` C#
string templatePath = GetTemplatePath("Deutsch").Trim('"');
// Die Routine zum einlesen sollte stets nur qeneralisierte und geparste Daten zurückgenen. Das Trim'men gehört als in die implementierung von GetTemplatePath
string templatePath = GetTemplatePath("Deutsch");
```
