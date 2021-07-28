# JS Snake in 723 bytes
A more optimized recreation of the JavaScript Snake bookmarklet from Cheng Sun (https://chengsun.uk/snake.html).  
  
### Comparison
  
Original:  
```javascript:for(Q=64,m=b=Q*Q,a=[P=l=u=d=p=S=w=0],u=89,f=(h=j=t=(b+Q)/2)-1,(B=(D=document).body).appendChild(x=D.createElement('p')),(X=x.style).position='fixed',X.left=X.top=0,X.background='#FFF',x.innerHTML='<p></p><canvas>',v=(s=x.childNodes)[0],(s=s[1]).width=s.height=Q*5,c=s.getContext('2d'),onkeydown=onblur=F=function(e,z){z?a[f]?(w+=m,f=Math.random(l+=8)*(R=Q-2)*R|(u=0),F(f+=Q+1+(f/R|0)*2,z)):F(f):e<0?(l?--l:(y=t,t=a[t]-2,F(y)),S+=(w*=.8)/4,m=999/(u+++10),a[h+=[-1,-Q,1,Q][d=p]]?B.removeChild(x,alert('Game Over')):(F(h),F(e,j=h),v.innerHTML=P?(setTimeout(F,50,e,0),S|0):'Press P')):-e?(y=(a[e]=e<Q|e>=Q*Q-Q|!(e%Q)|e%Q==Q-1|(e==h)*2)+(e==f),e==h&&(a[j]=2+h),c.fillStyle='hsl('+!a[e]*99+','+m*2+'%,'+y*50+'%)',c.fillRect(e%Q*5,(e/Q|0)*5,5,5)):isNaN(y=e.keyCode-37)|y==43?(P=y&&!P)&&F(-1):p=!P|y&-4|!(y^2^d)?p:y;return!1};--b;F(b));void F(-1)```  
  
New:  
```javascript:((b,Q=64,u=98,j=document,w=0,S=0,l='appendChild',f=2079,P,x=j[b]`a`,X=j.all[0][l](x)[l](j[b]`input`,x.style='position:fixed;top:0;display:grid'),s=x[l](b=j[b]`canvas`).getContext`2d`,t=b.width=b.height=320,p=l=0,h=j=t=f+1,m=b=Q*Q,F=X.onkeydown=X.onblur=(e,z,y=e%Q)=>![z?x[f]?F(f=(f=Math.random(w+=m,l+=8)*3844|0)+Q+(f/31|1),u=9):F(f):e?+e?s.fillRect(y*5,(e>>6)*5,5,5,s.fillStyle=`hsl(${!x[z=x[e]=e<Q|e>4031|!y|y>62|(y=e==h)+y,x[y*j]=2+h,e]*99},${m+m}%,${(z+(e==f))*50}%)`):(e=e.keyCode-37)-43?p=P&4/e>1&&e^2^b?e:p:(P=e&!P)&&F():x[l?l--:t=x[t]-2+F(t),S+=(w*=.8)/4,m=999/++u,h+=[-1,-Q,1,Q][b=p]]?x.remove(alert`Game Over`):X.value=F(e,j=F(h)+h)+P?S|!setTimeout(F,50,e):'Press P'])=>{while(b--)F(b)})`createElement` ```
