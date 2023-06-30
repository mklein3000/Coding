# Fundstücke
Code-Qualität ist wichtig und siche auch immer eine gewisse Frage des Geschmacks. 
Doch andereseits gibt es Fälle nach der Regel: _es genügt, wenn es compiliert!_.

Im RL findet man Beispiele für Code den man sich nicht ausdenken könnte.

``` C#
tring Template = "";
string TemplateSpace = @"\" +  @"""";
…
TemplateSpace = TemplateSpace.Remove(0,1);
…
Template = GetTemplateRoot("Deutsch");
…
if (Template.Contains(TemplateSpace))
   Template = Template.Replace(TemplateSpace, "");
```