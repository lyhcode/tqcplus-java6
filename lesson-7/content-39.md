# do while 迴圈

do while 迴圈的語法結構如下：

    do {
      statements;
    } while (boolean_expression);

範例（1）：猜數字遊戲

    Scanner scanner = new Scanner(System.in);
    
    int input = 0;
    
    do {
        System.out.print("輸入數字：");
        input = scanner.nextInt();
    } while (input != 30);
    
    System.out.println("恭喜你猜對了！");
