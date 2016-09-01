# matlab_iteration
function iteration_method(Xin,Yin,Tol)

F=@(x,y) x^2-y^2-4
Fx=@(x,y) 2x
Fy=@(x,y) -2y
G=@(x,y) x^2-y^2-16
Fx=@(x,y) 2x
Fy=@(x,y) 2y

X0=Xin;
Y0=Yin;
itr=0;
error=1;
D=[Fx(X0,Y0) Gx(X0,Y0) 0 0;Fy(X0,Y0) Gy(X0,Y0) 0 0;0 0 Fx(X0,Y0) Gx(X0,Y0);Fy(X0,Y0) Gy(X0,Y0)]
b=[-1;0;0;-1]
A=[a;b;g;d]
A(1)=a;
A(2)=b;
A(3)=g;
A(4)=d;
if det(D)==
    disp('change the initial approximation')
else
    A=inv(d)*b;
end
F(x,y)=@ (x,y) x+(A(1))*F(x,y)+(A(2))*G(x,y);
G(x,y)=@ (x,y) y+(A(3))*F(x,y)+(A(4))*G(x,y);
while error>Tol
    itr=itr+1;
    x1=F(X0,Y0);
    y1=G(X0,Y0);
    valueini=[x0;y0];
    valuefin=[x1;y1]
    error=norm(valueini-valuefin);
    X0=x1;
    Y0=yi;
end
fprintf('Maximum iteration=%d\n,itr')
fprintf('Required solution is x=%f and y=%f\n',x1,y1)
