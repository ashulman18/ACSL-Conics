# Conics

//Andrea Shulman
//acsl contest 4 practice

public class Conics
{
   private int A,B,C,D,E,F;
   private boolean circle, ellipse, parabola, hyperbola;
   private int xCo, yCo;
   
   public Conics(String str)
   {
      if(!coeffAssign(str))
         return;
      if(A==C)
         Circ();
      else if(((A>0)&&(C>0))||((A<0)&&(C<0)))
         Ellip();
      else if((A==0)||(B==0))
         Parab();
      else if(((A<0)&&(C>0))||((A<0)&&(C>0)))
         Hyperb();
      else{
         System.out.println("Not an easy conic");
         return;
      }

   }
   
   public boolean coeffAssign(String str)
   {
      //Conics hairy1=new Conics("x^2+y^2+4x-6y-3=0");
      if(str.indexOf("x^2")!=-1)
         A=Integer.parseInt(str.substring(0,str.indexOf("x^2")));
      String temp=str.substring(str.indexOf(""+A)+4);
      if(str.indexOf("xy")!=-1){   
         System.out.println("Not an easy conic");
         return false;
      }
      if(str.indexOf("y^2")!=-1){
         C=Integer.parseInt(temp.substring(0,str.indexOf("y^2")));
         temp=temp.substring(str.indexOf(""+C)+4);
      }
      if(str.indexOf("x")!=-1){
         D=Integer.parseInt(temp.substring(0,str.indexOf("x")));
         temp=temp.substring(str.indexOf(""+D)+2);
      }
      if(str.indexOf("y")!=-1){
         E=Integer.parseInt(temp.substring(0,str.indexOf("y")));
         temp=temp.substring(str.indexOf(""+E)+2);
      }
      if(temp.length()>0)
         F=Integer.parseInt(temp);
      System.out.println(A+" "+C+" "+D+" "+E+" "+F);
      return true;
   }
   
   public void Circ()
   {
   
   }
   
   public void Ellip()
   {
   
   }
   
   public void Parab()
   {
   
   }
   
   public void Hyperb()
   {
   
   }
   
   public static void main(String[]args)
   {
      Conics hairy1=new Conics("x^2+y^2+4x-6y-3=0");
      Conics hairy2=new Conics("x^2+4y^2-6x-16y-11=0");
      Conics hairy3=new Conics("2x^2+2y^2+8x-12y-6=0");
   }
}
