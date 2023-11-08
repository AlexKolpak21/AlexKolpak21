import java.io.BufferedWriter;
import java.io.FileWriter;
import java.io.IOException;
import java.util.Scanner;

public class UserDataApp {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Enter data (Last Name First Name Patronymic DateOfBirth PhoneNumber Gender):");
        String input = scanner.nextLine();

        String[] data = input.split(" ");
        if (data.length != 6) {
            System.err.println("Error: insufficient or too much data entered.");
            return;
        }

        try {
            String lastName = data[0];
            String firstName = data[1];
            String patronymic = data[2];
            String dateOfBirth = data[3];
            long phoneNumber = Long.parseLong(data[4]);
            char gender = data[5].charAt(0);

            if (!dateOfBirth.matches("\\d{2}\\.\\d{2}\\.\\d{4}")) {
                throw new IllegalArgumentException("Error: invalid date of birth format.");
            }

            if (gender != 'f' && gender != 'm') {
                throw new IllegalArgumentException("Error: invalid gender. Use 'f' or 'm'.");
            }

            String fileName = lastName + ".txt";
            BufferedWriter writer = new BufferedWriter(new FileWriter(fileName, true));
            writer.write(lastName + " " + firstName + " " + patronymic + " " + dateOfBirth + " " + phoneNumber + " " + gender);
            writer.newLine();
            writer.close();
            System.out.println("Data has been successfully written to the file " + fileName);
        } catch (NumberFormatException e) {
            System.err.println("Error: invalid phone number format.");
        } catch (IllegalArgumentException e) {
            System.err.println(e.getMessage());
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
