# Aproximação de função utilizando série de Fourier contínua R
## Aproximando a função módulo de x no intervalo de -pi a pi usando série de Fourier contínua no R
![1](https://user-images.githubusercontent.com/50224653/71494602-12a72180-2827-11ea-81a2-27f3d93292aa.png)

```R
f=function(x){abs(x)} # = |x|
fx=function(x){x}     # =  x

a0 =-1/(2*pi) *as.numeric(integrate(fx,-pi,0)[1])  +1/(2*pi) * as.numeric(integrate(fx,0,pi)[1])

#ak = 1/pi *integrate(f*cos(k*x),-pi,pi) 
#   = 2/pi *integrate(fx*cos(k*x),0,pi) 
#   = (2/(pi*k^2)) * ((-1)^k-1)   ,k = 1,2,3 

a1=(2/(pi*1^2)) * ((-1)^1-1)# = -4/pi
a2=(2/(pi*2^2)) * ((-1)^2-1)# = 0
a3=(2/(pi*3^2)) * ((-1)^3-1)# = -4/(pi*9)

Sn =function(x){a0+ a1*cos(x) + a2*cos(2*x)+ a3*cos(3*x)}

#polinômio em vermelho e função em azul
plot(1, type="n", xlab="x", ylab="f", xlim=c(-3, 3), ylim=c(0, 3))
abline(v=0, col = "black",lwd=1) ### criando o eixo y
abline(h=0, col = "black",lwd=1) ### criando o eixo X
plot(f,-pi,pi,add=T,col="blue",lwd = 5);plot(Sn,-pi,pi,add=T,col="red",lwd = 5)#;abline(v=0)
```



![2](https://user-images.githubusercontent.com/50224653/71494603-12a72180-2827-11ea-858a-b233dc4f4491.png)
