//monitor

package com.Laborator1;

public class Monitor {

    public String color;
    public int dimension;
    public String resolution;

    public Monitor(String color, int dimension, String resolution) {
        this.color = color;
        this.dimension = dimension;
        this.resolution = resolution;
    }

    String showData() {
        return "Informații despre primul monitor:" +
                "\ncolor: " + color +
                "\n" + "dimensions: " + dimension + " inch" +
                "\n" + "resolution: " + resolution + "\n";
    }

    String showData1() {
        return "Informații despre al doilea monitor:" +
                "\ncolor: " + color +
                "\n" + "dimensions: " + dimension + " inch" +
                "\n" + "resolution: " + resolution + "\n";
    }
}

//student

package com.Laborator1;

public class Student {
    public String name;
    public int age;
    public double mark;

    public Student(String name, int age, double mark){
        this.name = name;
        this.age = age;
        this.mark = mark;
    }

    public double show() {

        return mark;
    }
}

//university

package com.Laborator1;

public class University {

    public Student[] student;
    public String  name;
    public int  foundationYear;

    public University(Student[] student , String name , int foundationYear) {
        this.student = student;
        this.name = name;
        this.foundationYear = foundationYear;
    }

    public double getAverage() {
        double sum = 0 ;
        //average will have decimal point
        for (int i = 0 ; i < student.length; i++) {
            //parse string to double
            sum += student[i].show();
        }
        return sum/student.length;
    }
}

//main

package com.Laborator1;

public class Main {
    public static void main(String[] args){

        System.out.println("Nivel de bază:\n");

        Monitor monitor = new Monitor("yellow", 10, "1980 x 720");
        System.out.println(monitor.showData());

        Monitor monitor1 = new Monitor("green", 11, "1980 x 1080");
        System.out.println(monitor1.showData1());

        if (monitor.color.equals(monitor1.color)){
            System.out.println("Monitoarele au aceeași culoare.");
        }
        else {
            System.out.println("Monitoarele au culori diferite. Primul are culoarea: " + monitor.color + " , al doilea are culoarea " + monitor1.color);
        }

        if (monitor.resolution.equals(monitor1.resolution)){
            System.out.println("Monitoarele au aceeași rezoluție.");
        }
        else {
            System.out.println("Monitoarele au rezoluții diferite. Primul are " + monitor.resolution + " rezoluție, al doilea are " + monitor1.resolution + " rezolutie.");
        }

        if(monitor.dimension > monitor1.dimension) {
            System.out.println("Primul monitor are dimensiuni mai mari.");
        } else if(monitor.dimension < monitor1.dimension) {
            System.out.println("Al doilea monitor are dimensiuni mai mari.");
        } else if(monitor.dimension == monitor1.dimension){
            System.out.println("Dimensiunile sunt egale.");
        }

        System.out.println("\nNivel avansat:\n");

        Student st1 = new Student("Glen Perkins", 19, 8.69);
        Student st2 = new Student("Lorelei Allman", 20, 9.41);
        Student st3 = new Student("Melissa Sawyer", 19, 8.01);
        Student st4 = new Student("Kingsley Short", 21, 9.21);
        Student st5 = new Student("Casey Vang", 22, 7.35);
        Student st6 = new Student("Ria Shields", 21, 9.16);
        Student st7 = new Student("Alana Bailey", 19, 9.27);
        Student st8 = new Student("Shuaib Paine", 20, 8.14);
        Student st9 = new Student("Mike Stamp", 23, 7.65);

        Student[] UTM  = {st1,st2,st3};
        Student[] USM = {st4,st5,st6};
        Student[] USMF = {st7,st8,st9};

        University u1 = new University(UTM, "Universitatea Tehnica a Moldovei", 1964);
        University u2 = new University(USM," Universitatea de stat din Moldova", 1946);
        University u3 = new University(USMF,"Universitatea Liberă Internațională din Moldova", 1992);

        System.out.println("Nota medie a studenților UTM: " + st1.name + ", " + st2.name + ", " + st3.name + " este: " + u1.getAverage());
        System.out.println("Nota medie a studenților USM: " + st4.name + ", " + st5.name + ", " + st6.name + " este: " + u2.getAverage());
        System.out.println("Nota medie a studenților ULIM: " + st7.name + ", " + st8.name + ", " + st9.name + " este: " + u3.getAverage());

        double Avg, a = u1.getAverage(), b = u2.getAverage(), c = u3.getAverage();
        Avg = (a + b + c)/3;

        System.out.println("Nota medie a UTM, USM și ULIM este: " + Avg);
    }
}
