package org.example;


import org.RomanNumbers;

import java.util.ArrayList;
import java.util.Collections;
import java.util.Scanner;

class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String input = scanner.nextLine();
        System.out.println(calc(input));
    }

    public static String calc(String input) {
        var list = new ArrayList();
        Collections.addAll(list, input.split(" "));
        int numberArabic0 = 0;
        int numberArabic2 = 0;
        int numberArabic = 0;
        int numberRoman = 0;
        String getListNumber0;
        String getListNumber1 = null;
        String getListNumber2;

        if (list.size() <= 3) {
            try {
                getListNumber0 = String.valueOf(list.get(0));
                getListNumber1 = String.valueOf(list.get(1));
                getListNumber2 = String.valueOf(list.get(2));
                for (RomanNumbers number : RomanNumbers.values()) {
                    String getNumberRoman = String.valueOf(number);
                    String getNumberArabic = String.valueOf(number.getArabicNumbers());
                    int x = Integer.parseInt(getNumberArabic);
                    if (getListNumber0.equals(getNumberRoman)) {
                        numberArabic0 = x;
                        numberRoman++;
                    }
                    if (getListNumber0.equals(getNumberArabic)) {
                        numberArabic0 = x;
                        numberArabic++;
                    }
                    if (getListNumber2.equals(getNumberRoman)) {
                        numberArabic2 = x;
                        numberRoman++;
                    }
                    if (getListNumber2.equals(getNumberArabic)) {
                        numberArabic2 = x;
                        numberArabic++;
                    }
                }
            } catch (Exception exception) {
                System.err.println("throws Exception //т.к. строка не является математической операцией");
            }
        } else {
            try {
                throw new Exception();
            } catch (Exception exception) {
                System.err.println("throws Exception //т.к. формат математической операции не удовлетворяет заданию - два операнда и один оператор (+, -, /, *)");
            }
        }

        String returned = "";
        int arabic;
        if (numberArabic == 1 && numberRoman == 1) {
            try {
                throw new Exception();
            } catch (Exception exception) {
                System.err.println("throws Exception //т.к. используются одновременно разные системы счисления");
            }
        } else if (numberArabic == 2) {
            returned = String.valueOf(switching(getListNumber1, numberArabic0, numberArabic2));
        } else if (numberArabic > 2) {
            try {
                throw new Exception();
            } catch (Exception exception) {
                System.err.println("throws Exception //т.к. формат математической операции не удовлетворяет заданию - два операнда и один оператор (+, -, /, *)");
            }
        } else if (numberArabic == 1) {
            try {
                throw new Exception();
            } catch (Exception exception) {
                System.err.println("throws Exception //т.к. строка не является математической операцией");
            }
        } else if (numberRoman == 2) {
            arabic = switching(getListNumber1, numberArabic0, numberArabic2);
            if (arabic < 0) {
                try {
                    throw new Exception();
                } catch (Exception exception) {
                    System.err.println("throws Exception //т.к. в римской системе нет отрицательных чисел");
                }
            }
            for (RomanNumbers number : RomanNumbers.values()) {
                String getNumberRoman = String.valueOf(number);
                int x = Integer.parseInt(String.valueOf(number.getArabicNumbers()));
                if (arabic == x) {
                    returned = getNumberRoman;

                }
            }
        } else if (numberRoman > 2) {
            try {
                throw new Exception();
            } catch (Exception exception) {
                System.err.println("throws Exception //т.к. формат математической операции не удовлетворяет заданию - два операнда и один оператор (+, -, /, *)");
            }
        }
        return returned;
    }

    static int switching(String getListNumber1, int numberArabic0, int numberArabic2) {
        int b = 0;
        switch (getListNumber1) {
            case "-" -> b = numberArabic0 - numberArabic2;
            case "+" -> b = numberArabic0 + numberArabic2;
            case "*" -> b = numberArabic0 * numberArabic2;
            case "/" -> b = numberArabic0 / numberArabic2;
        }
        return b;
    }
}
