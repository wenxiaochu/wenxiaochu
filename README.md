import java.util.Random;
import java.util.Scanner;

public class NumberBombGame {
    private static final int MIN_VALUE = 1;
    private static final int MAX_VALUE = 100;
    private static final int MAX_TRIES = 5;

    public static void main(String[] args) {
        Random random = new Random();
        int targetNumber = random.nextInt(MAX_VALUE) + MIN_VALUE;

        Scanner scanner = new Scanner(System.in);
        int tries = 0;
        int guess;

        System.out.println("欢迎来到数字炸弹游戏！我已经选择了一个1到100之间的数字。你有5次机会来猜测它。");

        while (tries < MAX_TRIES) {
            System.out.print("请输入你的猜测：");
            guess = scanner.nextInt();
            tries++;

            if (guess == targetNumber) {
                System.out.println("恭喜你猜对了！数字是 " + targetNumber);
                break;
            } else if (guess < targetNumber) {
                System.out.println("你猜的数字太小了！");
            } else {
                System.out.println("你猜的数字太大了！");
            }
        }

        if (tries == MAX_TRIES) {
            System.out.println("很遗憾，你没有猜对。正确的数字是 " + targetNumber);
        }
    }
}
