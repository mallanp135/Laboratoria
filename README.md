# Laboratoria
Sprawozdania

Klasa punktmaterialny


public class punktmaterialny {
    private int m;            //masa
    public punktmaterialny(){ //konstruktor domyślny
        this.m=1; //parametr niejawny
    }
    public punktmaterialny(int a){ //konstruktor z parametrem
        if(a>0){
            this.m=a;
        }
        else{
            System.out.println("Masa musi byc dodatnia!");
        }
    }
    public int getMasa()     //akcesor
        return this.m;
    }
    public int zmienMase(int c){ //akcesor
        this.m = c;
        return this.m;
    }
    public int moment(){   //obliczanie momentu bezwładności, zwraca "i"
        int i=0;
        return i;
    }
    public int twsteinera(int d){ //obliczanie momentu bezwładości z twierdzenia Steinera
        int MB;
        MB=moment()+this.m*d*d;
        return MB;
    }
    public void nazwa(){       //klasa zwracająca nazwe
        System.out.println("Punkt materialny");
    }
}

Funckja main

public static void main(String[] args) {

    punktmaterialny pkt1 = new punktmaterialny();

    punktmaterialny pkt2 = new punktmaterialny(10);

        pkt1.nazwa();
        System.out.println("Masa: "+ pkt1.getMasa() + " Glowny moment bezwladnosci: " + pkt1.moment() + ". Moment wzgledem wybranej osi " + pkt1.twsteinera(2));

        pkt2.nazwa();
        System.out.println("Masa: "+ pkt2.getMasa() + " Glowny moment bezwladnosci: " + pkt2.moment() + ". Moment wzgledem wybranej osi: " + pkt2.twsteinera(2));

        pkt1.nazwa();
        pkt1.zmienMase(100);
        System.out.println("Masa: "+ pkt1.getMasa() + " Glowny moment bezwladnosci: " + pkt1.moment() + ". Moment wzgledem wybranej osi: " + pkt1.twsteinera(2));

        punktmaterialny[] tab = new punktmaterialny[10];

            for (int i=0; i<10; i++){
                    punktmaterialny punkt = new punktmaterialny(i+1);
                    tab[i]=punkt;
            }

            for(punktmaterialny pkt : tab){
                    pkt.nazwa();

                    System.out.println("Masa: "+ pkt.getMasa() + ". Glowny moment bezwladnosci: " + pkt.moment() + ". Moment wzgledem wybranej osi: " + pkt.twsteinera(2));

        }
        }
}
