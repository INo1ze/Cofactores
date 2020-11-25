# Cofactores
import java.util.Scanner;
/**
 *
 * @author Angel Campos, Dario Enriquez, Diego Lienzo.  
 */
public class Matriz {
    public static void main(String [] args){
        Scanner enter = new Scanner(System.in);
        System.out.println("Tamaño de la matriz: ");
        int tam = enter.nextInt();
        
        MMat matrizOne = new MMat(tam);
        
        matrizOne.llenarM();
        matrizOne.impM();
        matrizOne.det();
    }
}

public class MMat{
    int val, tam, matriz[][];
    int vec [];
    Scanner enter = new Scanner(System.in);
    
    MMat(int tam){
    this.tam = tam;
    matriz = new int [tam][tam];
}
    public void llenarM(){
        for(int i = 0; i < tam; i+=1){
            for(int j = 0; j < tam; j+=1){
                System.out.println("Posición "+"("+(i+1)+"), ("+(j+1)+")");
                matriz[i][j] = enter.nextInt();
            }
        }
    }
  public void det(){
    double deter;
    deter = 0.0;
    if(tam==2){
        for(int i = 0; i < tam; i +=1){
            for(int j = 0; j < tam; j+=1){
                deter = (matriz[0][0]*matriz[1][1])-(matriz[1][0]*matriz[0][1]);
            }
        }
    }
    if(tam==3){
        for(int i = 0; i < tam; i +=1){
            for(int j = 0; j < tam; j+=1){
                deter = (matriz[0][0]*((matriz[1][1]*matriz[2][2])-(matriz[2][1])*(matriz[1][2])))-(matriz[0][1]*((matriz[1][0]*matriz[2][2])-(matriz[2][0])*(matriz[1][2])))+(matriz[0][2]*((matriz[1][0]*matriz[2][1])-(matriz[2][0])*(matriz[1][1])));
            }
        }
    }
    System.out.println("El Determinante de la Matriz es: "+ deter);
}
    public void impM(){
        for(int i = 0; i < tam; i +=1){
            for(int j = 0; j < tam; j +=1){
                System.out.print(matriz[i][j] + " ");
            }
            System.out.println("");
        }
        System.out.println("Campos M. Angel, Lienzo G. Diego, Enriquez B. Dario");
}

}
