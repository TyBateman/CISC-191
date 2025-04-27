Flowchart Link: 

The major challenge I had in this lab was figuring out how the JSpinner works. However, I was eventually able to find some way to make it work through looking up methods on how to fix my code as well as tinkering with it for a while.

Video Link: 

```java
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

public class MilesToKilometersConverter {

    public static void main(String[] args) {
        JFrame frame = new JFrame("Miles to Kilometers Converter");
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setSize(300, 150);
        frame.setLayout(new FlowLayout());

        JLabel label = new JLabel("Distance in Miles:");

        SpinnerNumberModel model = new SpinnerNumberModel(1, 0, 1000, 1);
        JSpinner spinner = new JSpinner(model);

        JButton button = new JButton("Convert");
        JLabel resultLabel = new JLabel("Distance in Kilometers: ");

        button.addActionListener(new ActionListener() {
            public void actionPerformed(ActionEvent e) {
                int miles = (int) spinner.getValue();
                double kilometers = miles * 1.60934;
                resultLabel.setText(String.format("Result (km): %.2f", kilometers));
            }
        });

        frame.add(label);
        frame.add(spinner);
        frame.add(button);
        frame.add(resultLabel);

        frame.setVisible(true);
    }
}

```
