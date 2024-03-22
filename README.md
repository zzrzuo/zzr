import java.util.Scanner;

public class test3 {
    public static String[] name = new String[1];
    public static String[] number = new String[1];

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        while (true) {
            System.out.println("--------------------Hello--------------------");
            System.out.println("1.登陆功能(login)");
            System.out.println("2.注册功能(register)");
            System.out.println("3.查看(show)");
            System.out.println("0.退出(exit)");
            System.out.println("--------------------Hello--------------------");
            System.out.println("请选择功能：");

        String name0 = "zzr";
        String number0 = "050529";
        name[0] = name0;
        number[0] = number0;
        int c = sc.nextInt();

        switch (c) {
            case 1:
                login();
                break;
            case 2:
                register();
                break;
            case 3:
                show();
                break;
            case 0:
                System.exit(0);
            default:
                System.out.println("错误");
                break;
        }
    }

    }

    public static void login() {
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入用户名：");
        String name1 = sc.next();
        System.out.println("请输入密码：");
        String number1 = sc.next();
        boolean found = false;
        for (int i = 0; i < name.length; i++) {
            if (name[i].equals(name1) && number[i].equals(number1)) {
                System.out.println("登陆成功！");
                found = true;
                break;
            }
        }
        if (!found) {
            System.out.println("用户名或密码错误！");
        }
    }

    public static void register() {
        Scanner sc = new Scanner(System.in);
        String name2;
        boolean p;
        do{
        p=false;
        System.out.println("请输入用户名：");
        name2 = sc.next();
        for (int i = 0; i < name.length; i++) {
            if (name[i].equals(name2) && name[i] != null) {
                System.out.println("用户名重复，请重新输入");
                p=true;
                break;
            }
        }
        }while(p);
        System.out.println("请输入密码：");
        String number2 = sc.next();
        String[] newname = new String[name.length + 1];
        String[] newnumber = new String[number.length + 1];
        System.arraycopy(name, 0, newname, 0, name.length);
        System.arraycopy(number, 0, newnumber, 0, number.length);
        newname[name.length] = name2;
        newnumber[number.length] = number2;
        name = newname;
        number = newnumber;
    }

    public static void show() {
       for (int i = 0; i < name.length; i++) {
            System.out.println("用户名：" + name[i] + "，密码：" + number[i]);
    }
 }
}
