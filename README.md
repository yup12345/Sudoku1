program SUDOKUclase1
      implicit none
        integer::matriz(4,4)
        real::F1,F2, F3, F4,C1, C2, C3, C4, S
        integer :: i
        integer::a,b,c,d,e
        integer:: x
        real::u,t,o,q,r
        real::j,l,p,h,m
        real::subm1,subm2,subm3,subm4
        matriz=reshape((/&
        & 0, 4, 0, 2,      &
        & 3, 2, 1, 4,      &
        & 0, 3, 2, 0,      &
        & 2, 1, 0, 3/),    &
        & shape=(/4,4/),&
        & order=(/1,2/))
        write(*,*)'Matriz sin resolver:'
        write(*,*) 'a  4  b  2'
        write(*,*) '3  2  1  4'
        write(*,*) 'c  3  2  d'
        write(*,*) '2  1  e  3'
         do while (S/=40.or.subm1/=10.or.subm2/=10.or.subm3/=10.or.subm4/=10.or.&
         &F1/=10.or.F2/=10.or.F3/=10.or.F4/=10.or.&
         &C1/=10.or.C2/=10.or.C3/=10.or.C4/=10)
         call random_number(u)
         call random_number(t)
         call random_number(o)
         call random_number(q)
         call random_number(r)
         j=FLOOR(5*u)
         l=FLOOR(5*t)
         p=FLOOR(5*o)
         h=FLOOR(5*q)
         m=FLOOR(5*r)
         matriz=reshape((/&
         & int(p),         4,          int(j),          2,      &
         & 3,              2,               1,          4,      &
         & int(m),         3,               2,     int(l),      &
         & 2,              1,          int(h),        3/),      &
         & shape=(/4,4/),&
         & order=(/1,2/))
        F1=matriz(1,1)+matriz(1,2)+matriz(1,3)+matriz(1,4)
        F2=matriz(2,1)+matriz(2,2)+matriz(2,3)+matriz(2,4)
        F3=matriz(3,1)+matriz(3,2)+matriz(3,3)+matriz(3,4)
        F4=matriz(4,1)+matriz(4,2)+matriz(4,3)+matriz(4,4)
        C1=sum(matriz(:,1))
        C2=sum(matriz(:,2))
        C3=sum(matriz(:,3))
        C4=sum(matriz(:,4))
        S=sum(matriz)
        subm1=matriz(1,1)+matriz(1,2)+matriz(2,1)+matriz(2,2)
        subm2=matriz(1,3)+matriz(1,4)+matriz(2,3)+matriz(2,4)
        subm3=matriz(3,1)+matriz(3,2)+matriz(4,1)+matriz(4,2)
        subm4=matriz(3,3)+matriz(3,4)+matriz(4,3)+matriz(4,4)
      end do
      x=1
      do while (x<=3) 
      x=x+1
  
      print *, "Introduce los valores de las incógnitas a, b, c, d, e. Tienes 3 intentos."
  
      read *, a,b,c,d,e
  
      if (a/=p .or. b/=j .or. c/=m .or. d/=l .or. e/=h) then
        print *, "Respuesta incorrecta."
        write(*,*)
      else
        print *, "Respuesta correcta, ¡enhorabuena!"
      end if
      if (a==p .and. b==j .and. c==m .and. d==l .and. e==h) exit
      if (x>3) then
       write(*,*)'Solución:'
       write(*,"(4i3)") matriz
       write(*,*) 'a=', p
       write(*,*) 'b=',j
       write(*,*) 'c=',m
       write(*,*) 'd=',l
       write(*,*) 'e=',h
      exit 
  end if
      end do
        end program
