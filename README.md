import javax.swing.*;
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

public class GirlfriendProposal extends JFrame {
    private JButton yesButton, noButton;

    public GirlfriendProposal() {
        // Set the title of the window
        setTitle("Proposal");
        
        // Set the layout of the window
        setLayout(null);
        
        // Initialize the buttons
        yesButton = new JButton("Yes");
        noButton = new JButton("No");

        // Set the initial position of the buttons
        yesButton.setBounds(100, 100, 100, 50);
        noButton.setBounds(300, 100, 100, 50);

        // Add action listener to the "Yes" button
        yesButton.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                JOptionPane.showMessageDialog(null, "Yay! She said yes!");
                System.exit(0);  // Close the program after acceptance
            }
        });

        // Add action listener to the "No" button
        noButton.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                // Randomize new position for "No" button when clicked
                int x = (int) (Math.random() * (getWidth() - noButton.getWidth()));
                int y = (int) (Math.random() * (getHeight() - noButton.getHeight()));

                // Set new position for the "No" button
                noButton.setBounds(x, y, 100, 50);
            }
        });

        // Add buttons to the frame
        add(yesButton);
        add(noButton);

        // Set the window size and make it visible
        setSize(500, 400);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setLocationRelativeTo(null); // Center the window on screen
        setVisible(true);
    }

    public static void main(String[] args) {
        new GirlfriendProposal();
    }
}
