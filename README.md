Calls Resolved KPI MOM Card CF = 
var _var = [Calls Resolved] - [Calls Resolved last Month]
VAr _prct = DIVIDE( ([Calls Resolved] - [Calls Resolved last Month]),[Calls Resolved last Month])

VAR _color = 
SWITCH(
    TRUE(),
    _var > 0 ,"green",
    _var < 0 ,"red"
)


RETURN
_color

Calls Resolved KPI MOM Card Text = 
var _var = [Calls Resolved] - [Calls Resolved last Month]
VAr _prct = DIVIDE( ([Calls Resolved] - [Calls Resolved last Month]),[Calls Resolved last Month])
VAR _up_Arrow = UNICHAR(9650)
VAR _down_Arrow = UNICHAR(9660)
VAR _arrow = 
SWITCH(
    TRUE(),
    _prct > 0 ,_up_Arrow,
    _prct < 0 ,_down_Arrow
)
var result = 
_var & "|" & FORMAT(_prct, "0.0%") & _arrow & "MOM"

RETURN
result
