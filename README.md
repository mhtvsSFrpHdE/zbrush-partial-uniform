# zbrush-partial-uniform
**Contact**  
See https://github.com/mhtvsSFrpHdE/contact-me  

**What's this**  
In sometimes using a sequence of brushes will result in a distorted or uneven mesh.  
This is bad for further sculpt, and also bad for some ZBrush features.  
Sometimes may even have bad looking.  
There're various of approach to solving the situation.  
I pick up one of the most reliable and programming-friendly approach to create this script.  

**How to use**  
Set all model as not always show (Turn off the eye icon located at the right of every subtool).  
Use Control+Mouse smear to mask the details on model or square mask,  
the best is to keep the mask edge is smoothed, but not the sharp.  
Reverse the mask selection.  
ZScript -> Load -> (If Run is not activate) Run.  
If Run is already activated, the script should start executing.  
In the end, a dialog appear says "Operation complete".  

**Principle**  
Assume the mask is correct, in ZBrush, an operation should only affect the unmasked area.  
So now the target details should be unmasked and the other part of the model is masked and showing dark.  
Apply the following settings to ZBrush Project feature interface:  
```
    [ISet,Tool:SubTool:Dist,1]
    [ISet,Tool:SubTool:Mean,100]
    [ISet,Tool:SubTool:PA Blur,0]
    [ISet,Tool:SubTool:ProjectionShell,0]
```
Then duplicate the model, Move Up the duplicated one, then Select Down back to source model.  
Now the duplicated one will use as project target.  
Check if the circle located at the right of Tool/Deformation/Relax,  
set it to a "closed circle".  
Hover mouse on it and hold Control can show the hints.  
Drag the slider under Relax to maximum 100, waiting for the operation to complete.  
Goto Tool/Subtool/Project, apply a Project All.  

**Known issue**  
TODO: Shared ZBrush known issue by all scripts.

**Special thanks**  
Grammarly for README.md
