
***

# **LEARNING GUIDE: JAVA (PART 2)**
*(Covers Units 5 & 6 of the Question Bank)*

## **UNIT 5: Input-Output, Files & Networking**

### **Topic 1: File Handling & Serialization**

**Q1. What is Serialization? (The "Save Game" Feature)**
*   **Detailed Concept:**
    Imagine you have a `Student` object in RAM with name "John" and age 20. If you turn off the computer, that data is lost. **Serialization** is the process of converting that live object into a stream of bytes (0s and 1s) so it can be saved to a file (`student.txt`) or sent over a network.
*   **Deserialization:** The reverse process. Reading bytes from a file and reconstructing the `Student` object in RAM.
*   **The `Serializable` Interface:** This is a **Marker Interface** (it has no methods). By implementing it, you tell Java: "I allow this class to be saved."
*   **The `transient` Keyword:** Sometimes you have secret data (like a Password) you *don't* want to save. Labeling a variable `transient` tells Java to skip it during serialization.

**Q2. Detailed Serialization Code.**
*(This is a high-probability exam question. Memorize the flow: Open File -> Wrap in ObjectStream -> Write/Read).*
```java
import java.io.*;

// 1. Must implement Serializable
class Student implements Serializable {
    String name;
    transient int secretPin; // This will NOT be saved
    
    Student(String n, int p) { name = n; secretPin = p; }
}

public class SerializationDemo {
    public static void main(String args[]) {
        try {
            // --- SERIALIZATION (SAVING) ---
            Student s1 = new Student("Alice", 1234);
            // Chain: FileOutputStream -> ObjectOutputStream
            FileOutputStream fos = new FileOutputStream("data.txt");
            ObjectOutputStream oos = new ObjectOutputStream(fos);
            oos.writeObject(s1); // Magic happens here
            oos.close();
            
            // --- DESERIALIZATION (LOADING) ---
            // Chain: FileInputStream -> ObjectInputStream
            FileInputStream fis = new FileInputStream("data.txt");
            ObjectInputStream ois = new ObjectInputStream(fis);
            Student s2 = (Student) ois.readObject(); // Cast back to Student
            ois.close();
            
            System.out.println("Name: " + s2.name);    // Prints "Alice"
            System.out.println("Pin: " + s2.secretPin); // Prints "0" (default) because it was transient
            
        } catch(Exception e) { e.printStackTrace(); }
    }
}
```

### **Topic 2: Networking (Sockets)**

**Q3. The Client-Server Model.**
*   **Concept:**
    *   **Server:** A program running on a specific IP and Port, waiting for requests. It's like a Call Center agent waiting for a call.
    *   **Client:** A program that initiates the connection to the Server. It's like the customer making the call.
*   **Java Classes:**
    *   `ServerSocket`: Used only by the Server to "listen".
    *   `Socket`: Used by both to "talk" once connected.

**Q4. Socket Programming Example (Chat).**
*(Simple logic: Server listens, Client connects, Client sends "Hello").*
```java
// --- SERVER CODE ---
import java.io.*; import java.net.*;
class Server {
    public static void main(String args[]) throws Exception {
        ServerSocket ss = new ServerSocket(9999); // Listen on port 9999
        Socket s = ss.accept(); // Block here until client connects
        
        // Read message from client
        DataInputStream dis = new DataInputStream(s.getInputStream());
        String msg = dis.readUTF();
        System.out.println("Client says: " + msg);
        ss.close();
    }
}

// --- CLIENT CODE ---
import java.io.*; import java.net.*;
class Client {
    public static void main(String args[]) throws Exception {
        Socket s = new Socket("localhost", 9999); // Connect to Server
        
        // Send message to server
        DataOutputStream dout = new DataOutputStream(s.getOutputStream());
        dout.writeUTF("Hello Server!");
        dout.close();
        s.close();
    }
}
```

***

## **UNIT 6: GUI Programming (Applets & Swing)**

### **Topic 3: Applets (Legacy Web Apps)**

**Q5. What is an Applet?**
*   **Definition:** A small Java program designed to be embedded in a webpage (HTML). It runs inside the browser (client-side), not on the server.
*   **Lifecycle Methods (The "Big 5"):**
    1.  `init()`: Called once. Initialize variables here (like Constructor).
    2.  `start()`: Called every time the user visits the page.
    3.  `paint(Graphics g)`: The visual part. Draw shapes/text here.
    4.  `stop()`: Called when user leaves the page (minimizes).
    5.  `destroy()`: Called when browser closes. Cleanup.

**Q6. Applet Drawing Code.**
*(Draws a smiley face or shapes).*
```java
import java.applet.*; import java.awt.*;
// <applet code="MyApplet" width=200 height=200></applet>

public class MyApplet extends Applet {
    public void paint(Graphics g) {
        g.setColor(Color.BLUE);
        g.drawString("Hello Applet", 20, 20); // Text
        g.fillRect(50, 50, 100, 50);          // Blue Rectangle
        g.setColor(Color.RED);
        g.fillOval(50, 50, 100, 50);          // Red Oval
    }
}
```

### **Topic 4: Swing (Modern Desktop GUI)**

**Q7. Swing vs AWT.**
*   **AWT (Abstract Window Toolkit):** The old way. "Heavyweight" components. It uses the OS's native buttons (so a button looks like Windows 95 on Windows, and Mac on Mac).
*   **Swing:** The new way. "Lightweight" components. Written entirely in Java. It draws its own buttons so they look the same on ALL platforms.
*   **Naming:** Swing components start with 'J' (`JButton`, `JFrame`). AWT do not (`Button`, `Frame`).

**Q8. Swing Calculator (Event Handling).**
*(This demonstrates `ActionListener` - making buttons do things).*
```java
import javax.swing.*; 
import java.awt.event.*;

// Class must implement ActionListener to handle clicks
class Calculator implements ActionListener {
    JTextField t1, t2, result;
    JButton btnAdd;

    Calculator() {
        JFrame f = new JFrame("Calc");
        
        // Input Fields
        t1 = new JTextField(); t1.setBounds(50,50,150,20);
        t2 = new JTextField(); t2.setBounds(50,80,150,20);
        
        // Result Field (Read-only)
        result = new JTextField(); result.setBounds(50,110,150,20);
        result.setEditable(false);
        
        // Button
        btnAdd = new JButton("Add"); btnAdd.setBounds(50,150,100,30);
        btnAdd.addActionListener(this); // Tell button to call 'actionPerformed'
        
        f.add(t1); f.add(t2); f.add(result); f.add(btnAdd);
        f.setSize(300,300); 
        f.setLayout(null); 
        f.setVisible(true);
    }

    // This runs when button is clicked
    public void actionPerformed(ActionEvent e) {
        try {
            int a = Integer.parseInt(t1.getText()); // Get Text -> Convert to Int
            int b = Integer.parseInt(t2.getText());
            int sum = a + b;
            result.setText(String.valueOf(sum));    // Convert Int -> Set Text
        } catch(Exception ex) {
            result.setText("Error");
        }
    }

    public static void main(String[] args) {
        new Calculator();
    }
}
```

***

### **SECTION 3: Extra Unit 5 – Serialization & Networking**

**1. Serialization with `serialVersionUID`.**

```java
import java.io.*;

class Student implements Serializable {
    private static final long serialVersionUID = 1L;

    String name;
    transient int pin; // will not be saved

    Student(String n, int p) { name = n; pin = p; }

    @Override
    public String toString() {
        return name + " (" + pin + ")";
    }
}

public class SerUIDDemo {
    public static void main(String[] args) throws Exception {
        Student s1 = new Student("Bob", 9999);

        ObjectOutputStream out =
            new ObjectOutputStream(new FileOutputStream("stud.dat"));
        out.writeObject(s1);
        out.close();

        ObjectInputStream in =
            new ObjectInputStream(new FileInputStream("stud.dat"));
        Student s2 = (Student) in.readObject();
        in.close();

        System.out.println(s2.name); // "Bob"
        System.out.println(s2.pin);  // 0 (transient)
    }
}
```

- `serialVersionUID` is used to verify that a loaded class and the serialized object are **compatible** (same version). If they differ, `InvalidClassException` may be thrown.

***

**2. Client-server model with server response (echo).**

```java
// Server
import java.io.*;
import java.net.*;

class EchoServer {
    public static void main(String[] args) throws Exception {
        ServerSocket ss = new ServerSocket(9999);
        Socket s = ss.accept();

        DataInputStream dis = new DataInputStream(s.getInputStream());
        DataOutputStream dos = new DataOutputStream(s.getOutputStream());

        String msg = dis.readUTF();
        System.out.println("Client: " + msg);

        dos.writeUTF("Server received: " + msg);
        dis.close(); dos.close(); ss.close();
    }
}
```

```java
// Client
import java.io.*;
import java.net.*;

class EchoClient {
    public static void main(String[] args) throws Exception {
        Socket s = new Socket("localhost", 9999);

        DataOutputStream dout = new DataOutputStream(s.getOutputStream());
        DataInputStream din = new DataInputStream(s.getInputStream());

        dout.writeUTF("Hello Server");
        String reply = din.readUTF();
        System.out.println(reply);

        dout.close(); din.close(); s.close();
    }
}
```

***

### **SECTION 4: Extra Unit 6 – Applets & Swing**

**3. Basic “Hello User” applet.**

```java
import java.applet.Applet;
import java.awt.Graphics;

// <applet code="HelloUser" width=200 height=100></applet>
public class HelloUser extends Applet {
    public void paint(Graphics g) {
        g.drawString("Hello User", 50, 50);
    }
}
```

***

**4. Applet with button + text field + event handling.**

```java
import java.applet.Applet;
import java.awt.*;
import java.awt.event.*;

// <applet code="ButtonApplet" width=300 height=150></applet>
public class ButtonApplet extends Applet implements ActionListener {
    TextField tf;
    Button b;

    public void init() {
        tf = new TextField(20);
        b  = new Button("Click");
        add(tf);
        add(b);
        b.addActionListener(this);
    }

    public void actionPerformed(ActionEvent e) {
        tf.setText("Button Clicked");
    }
}
```

***

**5. Applet using multiple Graphics functions.**

```java
import java.applet.Applet;
import java.awt.*;

// <applet code="GraphicsDemo" width=300 height=300></applet>
public class GraphicsDemo extends Applet {
    public void paint(Graphics g) {
        g.setColor(Color.RED);
        g.drawLine(10, 10, 100, 10);

        g.setColor(Color.BLUE);
        g.drawRect(20, 30, 80, 40);

        g.setColor(Color.GREEN);
        g.fillRect(120, 30, 80, 40);

        g.setColor(Color.MAGENTA);
        g.drawOval(50, 100, 80, 50);
    }
}
```

Uses: `drawLine`, `drawRect`, `fillRect`, `drawOval`, `setColor`.

***

**6. Swing vs Servlets (conceptual).**

- **Swing:**
  - GUI framework for **desktop** Java applications.
  - Runs on client machine, interacts with user via windows, buttons, etc.
  - Uses `JFrame`, `JPanel`, `JButton`, etc.
  - Does not handle HTTP or web requests.

- **Servlets:**
  - Server-side components running inside a **web server** / servlet container (Tomcat, etc.).
  - Process HTTP requests and generate responses (HTML/JSON).
  - No direct GUI; interact with browsers via HTTP.

Use **Swing** for desktop tools; **Servlets** for web backends.

***

**7. Full Swing calculator (+, -, *, /, Clear, =).**

```java
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

public class FullCalc extends JFrame implements ActionListener {
    JTextField tf;
    JButton[] num = new JButton[10];
    JButton add, sub, mul, div, eq, clr;
    double op1 = 0, op2 = 0;
    char op = ' ';

    public FullCalc() {
        tf = new JTextField();
        tf.setEditable(false);
        setLayout(new BorderLayout());
        add(tf, BorderLayout.NORTH);

        JPanel p = new JPanel(new GridLayout(4, 4));
        for (int i = 0; i < 10; i++) {
            num[i] = new JButton(String.valueOf(i));
            num[i].addActionListener(this);
        }
        add = new JButton("+");
        sub = new JButton("-");
        mul = new JButton("*");
        div = new JButton("/");
        eq  = new JButton("=");
        clr = new JButton("C");

        JButton[] ops = { add, sub, mul, div, eq, clr };
        for (JButton b : ops) b.addActionListener(this);

        // simple layout: numbers 7-9, 4-6, 1-3, 0 and ops
        p.add(num[7]); p.add(num[8]); p.add(num[9]); p.add(add);
        p.add(num[4]); p.add(num[5]); p.add(num[6]); p.add(sub);
        p.add(num); p.add(num); p.add(num[3]); p.add(mul);
        p.add(num[0]); p.add(clr);    p.add(eq);     p.add(div);

        add(p, BorderLayout.CENTER);

        setSize(300, 300);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setVisible(true);
    }

    public void actionPerformed(ActionEvent e) {
        Object src = e.getSource();
        for (int i = 0; i < 10; i++) {
            if (src == num[i]) {
                tf.setText(tf.getText() + i);
                return;
            }
        }
        if (src == clr) {
            tf.setText("");
            op1 = op2 = 0; op = ' ';
        } else if (src == add || src == sub || src == mul || src == div) {
            op1 = Double.parseDouble(tf.getText());
            tf.setText("");
            if (src == add) op = '+';
            if (src == sub) op = '-';
            if (src == mul) op = '*';
            if (src == div) op = '/';
        } else if (src == eq) {
            op2 = Double.parseDouble(tf.getText());
            double res = 0;
            switch (op) {
                case '+': res = op1 + op2; break;
                case '-': res = op1 - op2; break;
                case '*': res = op1 * op2; break;
                case '/': res = op2 != 0 ? op1 / op2 : 0; break;
            }
            tf.setText(String.valueOf(res));
        }
    }

    public static void main(String[] args) {
        new FullCalc();
    }
}
```


***
