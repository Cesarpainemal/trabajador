# trabajador

import java.util.Scanner;


public class Ejercicio {

   
    static final int N=10;
    public static void main(String[] args) {
      
        Scanner entrada = new Scanner (System.in);
        int [] horas = new int [N];
        int [] horasExtras = new int [N];
        horastrabajadas(horas);
        horasExt(horas,horasExtras);
        salarios(horas,horasExtras);
    }
    public static void horastrabajadas(int []x ){
      
        Scanner entrada =new Scanner (System.in);
        
        for (int i =0;i<N;i++){
            do {
                System.out.println("ingrese horas trabajadas del empleado "+(i+1));
                x[i]= entrada.nextInt();
                if (x[i]>320)
                System.out.println("Numero de horas incorrecta");
            }while (x[i]>320);
        }
    }
    public static void horasExt(int [] x, int []horas){
        
        for (int i =0;i<N;i++){
            if (x[i]>160){
                if(x[i]>160 && x[i]<163){
                    horas [i]= (x[i]-160)*2000;
                }
                else if (x[i]>164 && x[i]<=167){
                    horas[i]= (x[i]-160)*3000;
                }
                else {
                    horas[i]=(x[i]-160)*3500;
                }      
            }
        }
    }
    public static void salarios (int []x, int []horas){
       
    int suel;    
        for(int i=0;i<N;i++){
            
            if (x[i]>= 40){
                suel=200000;
            }
            else{
                suel=x[i]*5000;
            }
         System.out.println("El salario del empleado es "+(i+1)+" :"+(suel+horas[i]));
        }
    }
}
