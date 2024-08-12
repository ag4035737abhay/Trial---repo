# Trial---repo
First github program
<br>
author-abhay gupta
Here's a simple Bounce Ball game code in Java using Java Swing:

```
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

public class BounceBall extends JPanel implements ActionListener {
    private int x = 0, y = 0, dx = 2, dy = 2;
    private Timer timer;

    public BounceBall() {
        setBackground(Color.BLACK);
        setPreferredSize(new Dimension(400, 400));
        timer = new Timer(16, this);
        timer.start();
    }

    public void paintComponent(Graphics g) {
        super.paintComponent(g);
        g.setColor(Color.WHITE);
        g.fillOval(x, y, 20, 20);
    }

    public void actionPerformed(ActionEvent e) {
        x += dx;
        y += dy;

        if (x < 0 || x > getWidth() - 20) {
            dx *= -1;
        }
        if (y < 0 || y > getHeight() - 20) {
            dy *= -1;
        }

        repaint();
    }

    public static void main(String[] args) {
        JFrame frame = new JFrame("Bounce Ball");
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.add(new BounceBall());
        frame.pack();
        frame.setLocationRelativeTo(null);
        frame.setVisible(true);
    }
}
```

This code creates a window with a bouncing ball. The ball changes direction when hitting the edges.

Key components:

1. `JPanel` for drawing
2. `Timer` for animation
3. `actionPerformed` for updating ball position
4. `paintComponent` for drawing the ball

Run the code to see the bouncing ball in action!

Want any modifications or enhancements? Feel free to ask!
