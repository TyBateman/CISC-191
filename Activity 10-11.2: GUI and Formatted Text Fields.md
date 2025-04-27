Flowchart Link: https://drive.google.com/file/d/1gPW2PN5OzCoiHjvKxXxVMsXxsdeYsqeq/view?usp=sharing

I didn't really have any major complications or challenges in this lab that I didn't have in the previous one. However, thanks to already doing a GUI project before this, I was able to finish this one more efficiently and faster.

Video Link: https://drive.google.com/file/d/1zXwjW4v975ZE4IbozJGHeOSwo_Xc0ukL/view?usp=sharing

```java
import javax.swing.*;
import javax.swing.text.NumberFormatter;
import java.awt.*;
import java.text.NumberFormat;

public class FormatedTextField {
    public static void main(String[] args) {
        SwingUtilities.invokeLater(() -> {
            JFrame frame = new JFrame("Distance Converter");
            frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
            frame.setLayout(new GridLayout(5, 1));

            JLabel promptLabel = new JLabel("Enter Distance: ");
            frame.add(promptLabel);

            NumberFormat format = NumberFormat.getNumberInstance();
            NumberFormatter formatter = new NumberFormatter(format);
            formatter.setValueClass(Double.class);
            formatter.setAllowsInvalid(false);
            formatter.setMinimum(0.0);
            JFormattedTextField milesInput = new JFormattedTextField(formatter);
            milesInput.setColumns(10);
            frame.add(milesInput);

            JButton convertButton = new JButton("Convert");
            frame.add(convertButton);

            JLabel kmLabel = new JLabel("Kilometers: ");
            JLabel mLabel = new JLabel("Meters: ");
            JLabel ftLabel = new JLabel("Feet: ");
            frame.add(kmLabel);
            frame.add(mLabel);
            frame.add(ftLabel);

            convertButton.addActionListener(e -> {
                double miles = ((Number) milesInput.getValue()).doubleValue();
                double kilometers = miles * 1.60934;
                double meters = kilometers * 1000;
                double feet = miles * 5280;

                kmLabel.setText(String.format("Kilometers: %.3f", kilometers));
                mLabel.setText(String.format("Meters: %.3f", meters));
                ftLabel.setText(String.format("Feet: %.3f", feet));
            });

            frame.pack();
            frame.setLocationRelativeTo(null);
            frame.setVisible(true);
        });
    }
}

```
