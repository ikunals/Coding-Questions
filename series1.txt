public class Main {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);
        String s = sc.nextLine();
        int key = sc.nextInt();
        StringBuilder result = new StringBuilder();
        for (int i = 0; i < s.length(); i++) {
            char ch = s.charAt(i);
            if (ch >= 'A' && ch <= 'Z') {
                int index = ch - 'A';
                index = (index + key) % 26;
                result.append((char) (index + 'A'));

            } else if (ch >= 'a' && ch <= 'z') {
                int index = ch - 'a';
                index = (key + index) % 26;
                result.append((char) (index + 'a'));
            } else if (Character.isDigit(ch)) {
                int index = ch - '0';
                index = (index + key) % 10; // Corrected modulus operation to 10 for digits
                result.append((char) (index + '0'));
            } else {
                result.append(ch);
            }
        }
        System.out.println(result.toString());
    }
}