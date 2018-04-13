# Hope

<br> http://hmelnov.icc.ru/stud/Hope/JSHope/



При помощи функции reduce
<br>dec reduce: (alpha#beta -> beta)#beta#list(alpha) -> beta;
<br>--- reduce(_,b,nil) <= b;
<br>--- reduce(F,b,x::l) <= F(x,reduce(F,b,l));
<br>Написать процедуру обращения списка. Например, из "ABCD" должно получиться "DCBA"
<br>
<br>
<br>Решение:
<br>dec reduce: (alpha#beta -> beta)#beta#list(alpha) -> beta;
<br>--- reduce(_,b,nil) <= b;
<br>--- reduce(F,b,x::l) <= F(x,reduce(F,b,l));
<br>dec Func : char#list(char) -> list(char);
<br>---Func(symbol, res) <= res <> [symbol];
<br>dec exec : list(char) -> list(char);
<br>---exec str <= reduce(Func, nil, str);

<br>exec ("ABCD");
