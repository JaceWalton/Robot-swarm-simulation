clc;
clear all;
x=0:0.25:10;
y=0:0.25:10;
z1=ones(11,11);
z2=ones(11,11);
z3=ones(11,11);
ki=23;
kt=5;
for i=1:41;
for j=1:41;
    ri=sqrt((x(i)-3)^2+(y(j)-2)^2);
    if(ri==0)
        ri=1;
    end
    z1(i,j)=ki/ri;
end
end

for i=1:41;
for j=1:41;
    ri=sqrt((x(i)-7)^2+(y(j)-6)^2);
    if(ri==0)
        ri=1;
    end
    z2(i,j)=ki/ri;
end
end

for i=1:41;
for j=1:41;
    ri=sqrt((x(i)-10)^2+(y(j)-10)^2);
    z3(i,j)=kt*ri;
end
end
% mesh(x,y,z1);
% figure;
% mesh(x,y,z2);
% figure;
% mesh(x,y,z3);
% 
  z4 = z1+z2+z3;
% figure;
% mesh(x,y,z4);
% % figure;
% % surf(z4);
% figure;
% contour(z4);



% for i=1:41;
%     ri=sqrt((x(i)-10)^2+(y(j)-10)^2);
%     Fxg(i)=kt*(10-x(i))/ri;
%     Fyg(i)=kt*(10-y(i))/ri;
%     
%     ri=sqrt((x(i)-3)^2+(y(j)-2)^2);
%     F1x(i)=-ki*(3-x(i))/(ri^2);
%     F1y(i)=-ki*(2-y(i))/(ri^2);
%     
%     ri=sqrt((x(i)-7)^2+(y(j)-6)^2);
%     F2x(i)=-ki*(7-x(i))/(ri^2);
%     F2y(i)=-ki*(6-y(i))/(ri^2);
%     
% end
% 
% Fx=Fxg+F1x+F2x;
% Fy=Fyg+F1y+F2y;
% 
% for i=1:41;
% for j=1:41;
%    
%     alpha(i,j)=atan(Fy(j)/Fx(i)); 
% 
% end
% end

pi=22/7;
vt=.23;
fi=pi/4;
xdot=0;
ydot=0;
xpath(1)=xdot;
ypath(1)=ydot;
 ri=sqrt((xdot-10)^2+(ydot-10)^2);
    Fxg=kt*(10-xdot)/ri;
    Fyg=kt*(10-ydot)/ri;
    
    ri=sqrt((xdot-3)^2+(ydot-2)^2);
    F1x=-ki*(3-xdot)/(ri^2);
    F1y=-ki*(2-ydot)/(ri^2);
    
    ri=sqrt((xdot-7)^2+(ydot-6)^2);
    F2x=-ki*(7-xdot)/(ri^2);
    F2y=-ki*(6-ydot)/(ri^2);
    
    Fx=Fxg+F1x+F2x;
    Fy=Fyg+F1y+F2y;
    alpha=atan(Fy/Fx);
    
theta=alpha

i=1;
while((xdot<10)||(ydot<10))
%while(i<=40)
if(xdot<9.8)
xdot=xdot+vt*cos(theta)*cos(fi);

end
if(ydot<9.8)
ydot=ydot+vt*sin(theta)*cos(fi);
end

theta=theta+vt*sin(fi)/2;

    ri=sqrt((xdot-10)^2+(ydot-10)^2);
    Fxg=kt*(10-xdot)/ri;
    Fyg=kt*(10-ydot)/ri;
    
    ri=sqrt((xdot-3)^2+(ydot-2)^2);
    F1x=-ki*(3-xdot)/(ri^2);
    F1y=-ki*(2-ydot)/(ri^2);
    
    ri=sqrt((xdot-7)^2+(ydot-6)^2);
    F2x=-ki*(7-xdot)/(ri^2);
    F2y=-ki*(6-ydot)/(ri^2);
    
    Fx=Fxg+F1x+F2x;
    Fy=Fyg+F1y+F2y;
    alpha=atan(Fy/Fx);
    
if((alpha-theta)>0)
ki=1;
else
ki=-1;
end

fi=ki*(alpha-theta);

%theta=alpha;
i=i+1;

xpath(i)=xdot;
ypath(i)=ydot;
if((xdot>9.8&&xdot<10)||(ydot>9.8&&ydot<10))
break;
end
end
figure;
intersec=1:i;
intersec=fliplr(intersec);
intersec=intersec*11;

for j=1:i
    m=1;
   while(xpath(j)>=x(m)) 
      m=m+1; 
      if(m==41)
          break;
      end
   end
   n=1;
    while(ypath(j)>=y(n)) 
      n=n+1;
      if(n==41)
          break;
      end
    end
   
    intersec(j)=z4(m-1,n-1);
    
    if(j>1)
     if(intersec(j)>intersec(j-1))
        intersec(j)=z4(m+3,n-4);
     
     end
    end
end


% hold on;
% hidden off;
% mesh(x,y,z4);
% plot3(xpath,ypath,intersec,'linewidth',2,'color','red');
% figure;
% contour(x,y,z4);
% 
% hold on;
% plot(xpath,ypath,'linewidth',2,'color','red');
%axis([0 12 0 12]);
for p=1:i
   xqueue(1,p+2) = xpath(p);
   yqueue(1,p+2) = ypath(p);
   
    xqueue(2,p+4) = xpath(p);
   yqueue(2,p+4) = ypath(p);
   
    xqueue(3,p+6) = xpath(p);
   yqueue(3,p+6) = ypath(p);
   
    xqueue(4,p+8) = xpath(p);
   yqueue(4,p+8) = ypath(p);
   
    xqueue(5,p+10) = xpath(p);
   yqueue(5,p+10) = ypath(p);
end


% %figure;
contour(x,y,z4);
hold on;
plot(xpath,ypath,'linewidth',.1,'color','blue');
axis([0 12 0 12]);
for j=1:i-1

hold on;
plot(xqueue(1,j),yqueue(1,j),'Marker','o','color','red');
axis([0 12 0 12]);
hold on;
plot(xqueue(2,j),yqueue(2,j),'Marker','+','color','green');
axis([0 12 0 12]);
hold on;
plot(xqueue(3,j),yqueue(3,j),'Marker','*','color','black');
axis([0 12 0 12]);
hold on;
plot(xqueue(4,j),yqueue(4,j),'Marker','x','color','yellow');
axis([0 12 0 12]);

end
hold off;



% EXTRA CREDIT - COMMENT THIS TO GET THE ABOVE PLOT 


for j=1:i-1
    
    contour(x,y,z4);
    hold on;
    plot(xpath(j),ypath(j),'Marker','o','color','blue');
    axis([0 12 0 12]);
    hold on;
    plot(xqueue(1,j),yqueue(1,j),'Marker','o','color','red');
    axis([0 12 0 12]);
     hold on;
    plot(xqueue(2,j),yqueue(2,j),'Marker','o','color','green');
    axis([0 12 0 12]);
     hold on;
    plot(xqueue(3,j),yqueue(3,j),'Marker','o','color','black');
    axis([0 12 0 12]);
     hold on;
    plot(xqueue(4,j),yqueue(4,j),'Marker','o','color','yellow');
    axis([0 12 0 12]);
    hold off;
   F(j)=getframe;        % marker circles overlap but the points doesnt overlap
    
end
%movie(F,1,3);          %uncomment to play movie 1 time with 3 frames per second
