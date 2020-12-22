# NumberOfDaysInAMonthChallenge
public class SwitchChallengeDaysMonth {
    public static void main(String[] args) {
        System.out.println(isLeapYear(-1600));
        System.out.println(isLeapYear(1600));
        System.out.println(isLeapYear(2017));
        System.out.println(isLeapYear(2000));
        System.out.println(isLeapYear(1924));
 
        // 2nd method
        System.out.println(getDaysInMonth(2, 1999));
        System.out.println(getDaysInMonth(2, 1600));
        System.out.println(getDaysInMonth(2, 2000));
        System.out.println(getDaysInMonth(4, 2000));
        System.out.println(getDaysInMonth(1, 2000));
        System.out.println(getDaysInMonth(-3, 2000));
        System.out.println(getDaysInMonth(14, 2000));
    }
 
    // challenge 3
    public static boolean isLeapYear(int year) {
        if (year < 1 || year > 9999) {
            return false;
        } else {
            if ((year % 4 == 0 && year % 100 != 0) || year % 400 == 0) {
                return true;
            } else {
                return false;
            }
        }
    }
 
    public static int getDaysInMonth(int month, int year) {
        int days = 0;
        if ((month < 1 || month > 12) || (year < 1 || year > 9999)) {
            return -1;
        }
 
        switch (month) {
            case 1:
            case 3:
            case 5:
            case 7:
            case 8:
            case 10:
            case 12:
                days = 31;
 
                break;
            case 4:
            case 6:
            case 9:
            case 11:
                days = 30;
                break;
 
            case 2:
                days = isLeapYear(year) ? 29 : 28;
                break;
 
        }
        return days;
    }
}
