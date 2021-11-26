# JS Snake in 713 bytes
A more optimized recreation of the JavaScript Snake bookmarklet from Cheng Sun (https://chengsun.uk/snake.html).  
  
### Comparison
  
Original:  
```javascript:for(Q=64,m=b=Q*Q,a=[P=l=u=d=p=S=w=0],u=89,f=(h=j=t=(b+Q)/2)-1,(B=(D=document).body).appendChild(x=D.createElement('p')),(X=x.style).position='fixed',X.left=X.top=0,X.background='#FFF',x.innerHTML='<p></p><canvas>',v=(s=x.childNodes)[0],(s=s[1]).width=s.height=Q*5,c=s.getContext('2d'),onkeydown=onblur=F=function(e,z){z?a[f]?(w+=m,f=Math.random(l+=8)*(R=Q-2)*R|(u=0),F(f+=Q+1+(f/R|0)*2,z)):F(f):e<0?(l?--l:(y=t,t=a[t]-2,F(y)),S+=(w*=.8)/4,m=999/(u+++10),a[h+=[-1,-Q,1,Q][d=p]]?B.removeChild(x,alert('Game Over')):(F(h),F(e,j=h),v.innerHTML=P?(setTimeout(F,50,e,0),S|0):'Press P')):-e?(y=(a[e]=e<Q|e>=Q*Q-Q|!(e%Q)|e%Q==Q-1|(e==h)*2)+(e==f),e==h&&(a[j]=2+h),c.fillStyle='hsl('+!a[e]*99+','+m*2+'%,'+y*50+'%)',c.fillRect(e%Q*5,(e/Q|0)*5,5,5)):isNaN(y=e.keyCode-37)|y==43?(P=y&&!P)&&F(-1):p=!P|y&-4|!(y^2^d)?p:y;return!1};--b;F(b));void F(-1)```  
  
New:  
```javascript:((b,P,Q=64,u=98,j=document,w=0,S=0,l='appendChild',f=2079,t=f+1,x=j[b]`a`,X=j.all[0][l](x)[l](j[b]`input`),s=x[l](b=j[b]`canvas`).getContext`2d`,p=l&=b.width=b.height=320,h=j=t,m=b=Q*Q,F=X.onkeydown=X.onblur=(e,z,y=e==h)=>![z?F[f]?F(f=(f=Math.random(w+=m,l+=8)*3844|0)+Q+(f/31|1),u=9):F(f):e?+e?s.fillRect(e%Q*5,(z=e>>6)*5,5,5,s.fillStyle=`hsl(${!F[z=F[e]=!(e%Q%63&&z%63)|y*2,F[y*j]=2+h,e]*99},${m+m}%,${(z+=e==f)*50}%)`):(e=e.keyCode-37)-43?p=P&4/e>1&&e^2^b?e:p:(P=e&!P)&&F():F[l?l--:t=F[t]-2+F(t),S+=(w*=.8)/4,m=999/++u,h+=[-1,-Q,1,Q][b=p]]?x.remove(alert`Game Over`):X.value=F(F(h),j=h)+P?S|!setTimeout(F,50):'Press P'])=>{for(x.style='position:fixed;top:0;display:grid';b--;)F(b)})`createElement` ```
