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

  z4 = z1+z2+z3;


pi=22/7;
vtl=1;
vt2=.3;
vt3=.3;
vt4=.3;
vt5=.3;

fi(1)=pi/30;
fi(2)=pi/15;
fi(3)=pi/10;
fi(4)=pi/5;
fi(5)=pi/1;

xdot=0;
ydot=0;
xpath(1,1)=xdot;
ypath(1,1)=ydot;

xpath(2,1)=xdot;
ypath(2,1)=ydot;

xpath(3,1)=xdot;
ypath(3,1)=ydot;

xpath(4,1)=xdot;
ypath(4,1)=ydot;

xpath(5,1)=xdot;
ypath(5,1)=ydot;

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
    
theta(1)=alpha;
theta(2)=alpha;
theta(3)=alpha;
theta(4)=alpha;
theta(5)=alpha;

i=2;

%leader

while((xpath(1,i-1)<10)||(ypath(1,i-1)<10)||(xpath(2,i-1)<11)||(ypath(2,i-1)<11)||(xpath(3,i-1)<11)||(ypath(3,i-1)<11)||(xpath(4,i-1)<11)||(ypath(4,i-1)<11)||(xpath(5,i-1)<11)||(ypath(5,i-1)<11))
%while(i<=90)
if(xpath(1,i-1)<=9.8)
xpath(1,i)=xpath(1,i-1)+vtl*cos(theta(1))*cos(fi(1));
else
  xpath(1,i) =xpath(1,i-1);
end

if(ypath(1,i-1)<=9.8)
ypath(1,i)=ypath(1,i-1)+vtl*sin(theta(1))*cos(fi(1));
else
  ypath(1,i) =ypath(1,i-1);
end

theta(1)=theta(1)+vtl*sin(fi(1))/2;



    ri=sqrt((xpath(1,i)-10)^2+(ypath(1,i)-10)^2);
    Fxg=kt*(10-xpath(1,i))/ri;
    Fyg=kt*(10-ypath(1,i))/ri;
    
    ri=sqrt((xpath(1,i)-3)^2+(ypath(1,i)-2)^2);
    F1x=-ki*(3-xpath(1,i))/(ri^2);
    F1y=-ki*(2-ypath(1,i))/(ri^2);
    
    ri=sqrt((xpath(1,i)-7)^2+(ypath(1,i)-6)^2);
    F2x=-ki*(7-xpath(1,i))/(ri^2);
    F2y=-ki*(6-ypath(1,i))/(ri^2);
    
    Fx=Fxg+F1x+F2x;
    Fy=Fyg+F1y+F2y;
    alpha=atan(Fy/Fx);

    
if((alpha-theta(1))>0)
ki=1;
else
ki=-1;
end

fi(1)=ki*(alpha-theta(1));



%robot 2

if(xpath(2,i-1)<11)
xpath(2,i)=xpath(2,i-1)+vt2*cos(theta(2))*cos(fi(2));
else
  xpath(2,i) =xpath(2,i-1);
end
if(ypath(2,i-1)<11)
ypath(2,i)=ypath(2,i-1)+vt2*sin(theta(2))*cos(fi(2));
else
  ypath(2,i) =ypath(2,i-1);
end

theta(2)=theta(2)+vt2*sin(fi(2))/2;

    ri=sqrt((xpath(2,i)-xpath(1,i))^2+(ypath(2,i)-ypath(1,i)+1)^2);
    Fxg=kt*(xpath(1,i)-xpath(2,i))/ri;
    Fyg=kt*(ypath(1,i)-1-ypath(2,i))/ri;
    
    ri=sqrt((xpath(2,i)-3)^2+(ypath(2,i)-2)^2);
    F1x=-ki*(3-xpath(2,i))/(ri^2);
    F1y=-ki*(2-ypath(2,i))/(ri^2);
    
    ri=sqrt((xpath(2,i)-7)^2+(ypath(2,i)-6)^2);
    F2x=-ki*(7-xpath(2,i))/(ri^2);
    F2y=-ki*(6-ypath(2,i))/(ri^2);
    
    ri=sqrt((xpath(2,i)-xpath(3,i-1))^2+(ypath(2,i)-ypath(3,i-1))^2);
    F3x=-ki*(xpath(3,i-1)-xpath(2,i))/(ri^2);
    F3y=-ki*(ypath(3,i-1)-ypath(2,i))/(ri^2);
    
    ri=sqrt((xpath(2,i)-xpath(4,i-1))^2+(ypath(2,i)-ypath(4,i-1))^2);
    F4x=-ki*(xpath(4,i-1)-xpath(2,i))/(ri^2);
    F4y=-ki*(ypath(4,i-1)-ypath(2,i))/(ri^2);
    
    ri=sqrt((xpath(2,i)-xpath(5,i-1))^2+(ypath(2,i)-ypath(5,i-1))^2);
    F5x=-ki*(xpath(5,i-1)-xpath(2,i))/(ri^2);
    F5y=-ki*(ypath(5,i-1)-ypath(2,i))/(ri^2);
    
    
    Fx=Fxg+F1x+F2x+F3x+F4x+F5x;
    Fy=Fyg+F1y+F2y+F3y+F4y+F5y;
    alpha=atan(Fy/Fx);
    
if((alpha-theta(2))>0)
ki=1;
else
ki=-1;
end

fi(2)=ki*(alpha-theta(2));



%robot 3

if(xpath(3,i-1)<11)
xpath(3,i)=xpath(3,i-1)+vt3*cos(theta(3))*cos(fi(3));
else
  xpath(3,i) =xpath(3,i-1);
end
if(ypath(3,i-1)<11)
ypath(3,i)=ypath(3,i-1)+vt3*sin(theta(3))*cos(fi(3));
else
  ypath(3,i) =ypath(3,i-1);
end

theta(3)=theta(3)+vt3*sin(fi(3))/2;

    ri=sqrt((xpath(3,i)-xpath(1,i))^2+(ypath(3,i)-ypath(1,i)-1)^2);
    Fxg=kt*(xpath(1,i)-xpath(3,i))/ri;
    Fyg=kt*(ypath(1,i)+1-ypath(3,i))/ri;
    
    ri=sqrt((xpath(3,i)-3)^2+(ypath(3,i)-2)^2);
    F1x=-ki*(3-xpath(3,i))/(ri^2);
    F1y=-ki*(2-ypath(3,i))/(ri^2);
    
    ri=sqrt((xpath(3,i)-7)^2+(ypath(3,i)-6)^2);
    F2x=-ki*(7-xpath(3,i))/(ri^2);
    F2y=-ki*(6-ypath(3,i))/(ri^2);
    
    ri=sqrt((xpath(3,i)-xpath(2,i))^2+(ypath(3,i)-ypath(2,i))^2);
    F3x=-ki*(xpath(2,i)-xpath(3,i))/(ri^2);
    F3y=-ki*(ypath(2,i)-ypath(3,i))/(ri^2);
    
    ri=sqrt((xpath(3,i)-xpath(4,i-1))^2+(ypath(3,i)-ypath(4,i-1))^2);
    F4x=-ki*(xpath(4,i-1)-xpath(3,i))/(ri^2);
    F4y=-ki*(ypath(4,i-1)-ypath(3,i))/(ri^2);
    
    ri=sqrt((xpath(3,i)-xpath(5,i-1))^2+(ypath(3,i)-ypath(5,i-1))^2);
    F5x=-ki*(xpath(5,i-1)-xpath(3,i))/(ri^2);
    F5y=-ki*(ypath(5,i-1)-ypath(3,i))/(ri^2);
    
    
    Fx=Fxg+F1x+F2x+F3x+F4x+F5x;
    Fy=Fyg+F1y+F2y+F3y+F4y+F5y;
    alpha=atan(Fy/Fx);
    
if((alpha-theta(3))>0)
ki=1;
else
ki=-1;
end

fi(3)=ki*(alpha-theta(3));


%robot 4

if(xpath(4,i-1)<11)
xpath(4,i)=xpath(4,i-1)+vt4*cos(theta(4))*cos(fi(4));
else
  xpath(4,i) =xpath(4,i-1);
end
if(ypath(4,i-1)<11)
ypath(4,i)=ypath(4,i-1)+vt4*sin(theta(4))*cos(fi(4));
else
  ypath(4,i) =ypath(4,i-1);
end

theta(4)=theta(4)+vt4*sin(fi(4))/2;

    ri=sqrt((xpath(4,i)-xpath(1,i)+1)^2+(ypath(4,i)-ypath(1,i))^2);
    Fxg=kt*(xpath(1,i)-1-xpath(4,i))/ri;
    Fyg=kt*(ypath(1,i)-ypath(4,i))/ri;
    
    ri=sqrt((xpath(4,i)-3)^2+(ypath(4,i)-2)^2);
    F1x=-ki*(3-xpath(4,i))/(ri^2);
    F1y=-ki*(2-ypath(4,i))/(ri^2);
    
    ri=sqrt((xpath(4,i)-7)^2+(ypath(4,i)-6)^2);
    F2x=-ki*(7-xpath(4,i))/(ri^2);
    F2y=-ki*(6-ypath(4,i))/(ri^2);
    
    ri=sqrt((xpath(4,i)-xpath(2,i))^2+(ypath(4,i)-ypath(2,i))^2);
    F3x=-ki*(xpath(2,i)-xpath(4,i))/(ri^2);
    F3y=-ki*(ypath(2,i)-ypath(4,i))/(ri^2);
    
    ri=sqrt((xpath(4,i)-xpath(3,i))^2+(ypath(4,i)-ypath(3,i))^2);
    F4x=-ki*(xpath(3,i)-xpath(4,i))/(ri^2);
    F4y=-ki*(ypath(3,i)-ypath(4,i))/(ri^2);
    
    ri=sqrt((xpath(4,i)-xpath(5,i-1))^2+(ypath(4,i)-ypath(5,i-1))^2);
    F5x=-ki*(xpath(5,i-1)-xpath(4,i))/(ri^2);
    F5y=-ki*(ypath(5,i-1)-ypath(4,i))/(ri^2);
    
    
    Fx=Fxg+F1x+F2x+F3x+F4x+F5x;
    Fy=Fyg+F1y+F2y+F3y+F4y+F5y;
    alpha=atan(Fy/Fx);
    
if((alpha-theta(4))>0)
ki=1;
else
ki=-1;
end

fi(4)=ki*(alpha-theta(4));



%robot 5

if(xpath(5,i-1)<11)
xpath(5,i)=xpath(5,i-1)+vt5*cos(theta(5))*cos(fi(5));
else
  xpath(5,i) =xpath(5,i-1);
end
if(ypath(5,i-1)<11)
ypath(5,i)=ypath(5,i-1)+vt5*sin(theta(5))*cos(fi(5));
else
  ypath(5,i) =ypath(5,i-1);
end

theta(5)=theta(5)+vt5*sin(fi(5))/2;

    ri=sqrt((xpath(5,i)-xpath(1,i)-1)^2+(ypath(5,i)-ypath(1,i))^2);
    Fxg=kt*(xpath(1,i)+1-xpath(5,i))/ri;
    Fyg=kt*(ypath(1,i)-ypath(5,i))/ri;
    
    ri=sqrt((xpath(5,i)-3)^2+(ypath(5,i)-2)^2);
    F1x=-ki*(3-xpath(5,i))/(ri^2);
    F1y=-ki*(2-ypath(5,i))/(ri^2);
    
    ri=sqrt((xpath(5,i)-7)^2+(ypath(5,i)-6)^2);
    F2x=-ki*(7-xpath(5,i))/(ri^2);
    F2y=-ki*(6-ypath(5,i))/(ri^2);
    
    ri=sqrt((xpath(5,i)-xpath(2,i))^2+(ypath(5,i)-ypath(2,i))^2);
    F3x=-ki*(xpath(2,i)-xpath(5,i))/(ri^2);
    F3y=-ki*(ypath(2,i)-ypath(5,i))/(ri^2);
    
    ri=sqrt((xpath(5,i)-xpath(3,i))^2+(ypath(5,i)-ypath(3,i))^2);
    F4x=-ki*(xpath(3,i)-xpath(5,i))/(ri^2);
    F4y=-ki*(ypath(3,i)-ypath(5,i))/(ri^2);
    
    ri=sqrt((xpath(5,i)-xpath(4,i))^2+(ypath(5,i)-ypath(4,i))^2);
    F5x=-ki*(xpath(4,1)-xpath(5,i))/(ri^2);
    F5y=-ki*(ypath(4,i)-ypath(5,i))/(ri^2);
    
    
    Fx=Fxg+F1x+F2x+F3x+F4x+F5x;
    Fy=Fyg+F1y+F2y+F3y+F4y+F5y;
    alpha=atan(Fy/Fx);
    
if((alpha-theta(5))>0)
ki=1;
else
ki=-1;
end

fi(5)=ki*(alpha-theta(5));






i=i+1;



if((xpath(1,i-1)>9.8&&xpath(1,i-1)<12)&&(ypath(1,i-1)>9.8&&ypath(1,i-1)<12)&&(xpath(2,i-1)>8&&xpath(2,i-1)<12)&&(ypath(2,i-1)>8&&ypath(2,i-1)<12)&&(xpath(3,i-1)>8&&xpath(3,i-1)<12)&&(ypath(3,i-1)>8&&ypath(3,i-1)<12)&&(xpath(4,i-1)>8&&xpath(4,i-1)<12)&&(ypath(4,i-1)>8&&ypath(4,i-1)<12)&&(xpath(5,i-1)>8&&xpath(5,i-1)<12)&&(ypath(5,i-1)>8&&ypath(5,i-1)<12))
break;
end
if(i>500)
    break;
end
end

%figure;
contour(x,y,z4);

hold on;
plot(xpath(1,:),ypath(1,:),'linewidth',2,'color','blue');
axis([0 12 0 12]);
plot(xpath(2,:),ypath(2,:),'linewidth',2,'color','red');
axis([0 12 0 12]);
plot(xpath(3,:),ypath(3,:),'linewidth',2,'color','green');
axis([0 12 0 12]);
plot(xpath(4,:),ypath(4,:),'linewidth',2,'color','black');
axis([0 12 0 12]);
plot(xpath(5,:),ypath(5,:),'linewidth',2,'color','yellow');
axis([0 12 0 12]);

hold off;

% EXTRA CREDIT - COMMENT THIS TO GET THE ABOVE PLOT 
figure(1)
filename='C:\Users\Administrator\Desktop\ICS\test1.gif';
for j=1:i-1
    
    contour(x,y,z4);
    hold on;
    plot(xpath(1,j),ypath(1,j),'Marker','o','color','blue');
    axis([0 12 0 12]);
    hold on;
    plot(xpath(2,j),ypath(2,j),'Marker','o','color','red');
    axis([0 12 0 12]);
%      hold on;
%     plot(xpath(3,j),ypath(3,j),'Marker','o','color','green');
%     axis([0 12 0 12]);
%      hold on;
%     plot(xpath(4,j),ypath(4,j),'Marker','o','color','black');
%     axis([0 12 0 12]);
%      hold on;
%     plot(xpath(5,j),ypath(5,j),'Marker','o','color','yellow');
%     axis([0 12 0 12]);
    hold off;
   F=getframe(1);       % marker circles overlap but the points doesnt overlap
   im=frame2im(F);
   [imind,cm] = rgb2ind(im,256);
      if j == 1;
          imwrite(imind,cm,filename,'gif', 'Loopcount',inf);
      else
          imwrite(imind,cm,filename,'gif','WriteMode','append');
      end
end


% x = 0:0.01:1;
% figure(1)
% filename = 'C:\Users\Administrator\Desktop\ICS\testnew51.gif';
% for n = 1:0.5:5
%       y = x.^n;
%       plot(x,y)
%       drawnow
%       frame = getframe(1);
%       im = frame2im(frame);
%       [imind,cm] = rgb2ind(im,256);
%       if n == 1;
%           imwrite(imind,cm,filename,'gif', 'Loopcount',inf);
%       else
%           imwrite(imind,cm,filename,'gif','WriteMode','append');
%       end
% end

%movie(F,1,3);          %uncomment to play movie 1 time with 3 frames per second
