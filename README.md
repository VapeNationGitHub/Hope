# Hope

<br> http://hmelnov.icc.ru/stud/Hope/JSHope/

-------

При помощи функции reduce
<br>dec reduce: (alpha#beta -> beta)#beta#list(alpha) -> beta;
<br>--- reduce(_,b,nil) <= b;
<br>--- reduce(F,b,x::l) <= F(x,reduce(F,b,l));
<br>Написать процедуру обращения списка. Например, из "ABCD" должно получиться "DCBA"
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

-------

<br>Не пользуясь операторами сравнения строк целиком определить функцию 
<br>strCmp: list(char)# list(char)-> num; которая возвращает 0, 
<br>если строки совпадают; число <0, если первая строка меньше второй; 
<br>число >0, если первая строка больше второй. 
<br>Например, strCmp("AB","CDE") =-10, strCmp("AB","AB") =0, strCmp("AB","A") =1.
<br>
<br>Решение:
<br>dec strCmp : list(char)#list(char) -> num; 
<br>--- strCmp(nil, nil) <= 0; 
<br>--- strCmp(_, nil) <= 1; 
<br>--- strCmp(nil, _) <= 0-1; 
<br>--- strCmp(str1_0 :: str1_rest, str2_0 :: str2_rest) <=let d==ord(str1_0)-ord(str2_0) in if d/=0 then d
<br>else
<br>strCmp("AB","CDE")
<br>strCmp("AB","AB")
<br>strCmp("AB","A")
