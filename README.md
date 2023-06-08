public class StringBufferExample {
    private StringBuffer stringBuffer;

    public StringBufferExample() {
        stringBuffer = new StringBuffer();
    }

    public void tambahKata(String huruf) {
        stringBuffer.append(huruf);
    }

    public void ubahKata(char c) {
        for (int i = 0; i < stringBuffer.length(); i++) {
            if (stringBuffer.charAt(i) == ' ') {
                continue;  // Lewati spasi
            }
            if (stringBuffer.charAt(i) == c) {
                stringBuffer.setCharAt(i, '*');
            }
        }
    }

    public void deleteKata(char c) {
        int index = 0;
        while ((index = stringBuffer.indexOf(String.valueOf(c), index)) != -1) {
            stringBuffer.deleteCharAt(index);
        }
    }

    public String toString() {
        return stringBuffer.toString();
    }

    public static void main(String[] args) {
        StringBufferExample example = new StringBufferExample();

        example.tambahKata("saya makan");
        System.out.println("Sebelum perubahan: " + example.toString());

        example.ubahKata('a');
        System.out.println("Setelah ubahKata('a'): " + example.toString());

        example.deleteKata('*');
        System.out.println("Setelah deleteKata('*'): " + example.toString());
    }
}
