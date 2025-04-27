Flowchart Link: 

The main challenges I had in completing this lab were figuring out how to properly work with what I learned in the GUI lecture/lesson and apply it to this lab. As this is somewhat different to what we had previously done so far, it was a bit tricky to figure out but it overall wasn't that difficult.

Video Link: 

```java
import javax.swing.*;
import java.awt.event.*;

public class GUI {
    public static void main(String[] args) {
        JFrame frame = new JFrame("Yearly Salary Calculator ");
        frame.setSize(300, 200);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setLayout(null);

        JLabel wageLabel = new JLabel("Hourly Wage: ");
        wageLabel.setBounds(10, 20, 100, 25);
        frame.add(wageLabel);

        JTextField wageField = new JTextField();
        wageField.setBounds(120, 20, 150, 25);
        frame.add(wageField);

        JLabel hoursLabel = new JLabel("Hours/Week: ");
        hoursLabel.setBounds(10, 60, 100, 25);
        frame.add(hoursLabel);

        JTextField hoursField = new JTextField();
        hoursField.setBounds(120, 60, 150, 25);
        frame.add(hoursField);

        JButton calculateButton = new JButton("Calculate ");
        calculateButton.setBounds(90, 100, 120, 25);
        frame.add(calculateButton);

        JLabel resultLabel = new JLabel("Yearly Salary: ");
        resultLabel.setBounds(10, 140, 260, 25);
        frame.add(resultLabel);

        calculateButton.addActionListener(new ActionListener() 
        {
            public void actionPerformed(ActionEvent e) {
                try {
                    double hourlyWage = Double.parseDouble(wageField.getText());
                    double hoursPerWeek = Double.parseDouble(hoursField.getText());
                    double yearlySalary = hourlyWage * hoursPerWeek * 52;
                    resultLabel.setText(String.format("Yearly Salary: $%.2f", yearlySalary));
                } catch (NumberFormatException ex) {
                    resultLabel.setText("Error");
                }
            }
        }
        );

        frame.setVisible(true);
    }
}
```
