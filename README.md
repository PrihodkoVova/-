 /**
 * Created by Vova on 11.12.2016.
 */
import java.applet.*;
import java.awt.*;
import java.awt.event.*;
import java.net.MalformedURLException;
import java.net.URL;
import java.util.Timer;
import java.util.TimerTask;

public class Main extends Applet implements MouseListener {
    int x, y;
    /*Создаём прослушиватель мыши*/
    public void init() {
        addMouseListener(this);
    }
    /*При нажатии мышки расчитываются координаты нажатия*/
    public void mouseClicked(MouseEvent e) {
        x = e.getX();
        y = e.getY();
        if (x > 880 && x < 1080 && y > 420 && y < 460) {
            Main m = this;
            m.repaint();
            n++;
            TimerTask task = new TimerTask() {
                @Override
                public void run() {
                    if (n < 2)
                    {
                        m.repaint(122, 490,550,280);
                        n++;
                    }
                    else if (n < 12)
                    {
                        m.repaint(122, 490,550,280);
                        n++;
                    }
                }
            };
            Timer timer = new Timer();
            timer.schedule(task, 2*1000, 1000);
        }
    }

    public void mouseEntered(MouseEvent e) {
    }

    public void mouseExited(MouseEvent e) {
    }

    public void mousePressed(MouseEvent e) {
    }

    public void mouseReleased(MouseEvent e) {
    }

    /* Класс для вставки картинок */
    Image img;
    MediaTracker tr;
    int n = 0;

    public void paint(Graphics g) {
        try {
		    /* Выводим рисунок 1 */
            img = getImage(new URL("file", null, "C:\\Users\\Vova\\OOP_Kursova\\src\\Верхняя панель.jpg"));
            g.drawImage(img, 80, 10, this);
             /* Выводим рисунок 2 */
            img = getImage(new URL("file", null, "C:\\Users\\Vova\\OOP_Kursova\\src\\Нижняя панель.jpg"));
            g.drawImage(img, 80, 258, this);
            img = getImage(new URL("file", null, "C:\\Users\\Vova\\OOP_Kursova\\src\\Показания(1).png"));
            g.drawImage(img, 122, 490, this);
		    /* Выводим Табло */
            img = getImage(new URL("file", null, "C:\\Users\\Vova\\OOP_Kursova\\src\\Табло.jpg"));
            g.drawImage(img, 820, 10, this);
            img = getImage(new URL("file", null, "C:\\Users\\Vova\\OOP_Kursova\\src\\Топл сист - неисправна(ВЫКЛ).png"));
            g.drawImage(img, 853, 27, this);
            img = getImage(new URL("file", null, "C:\\Users\\Vova\\OOP_Kursova\\src\\т топл низная.png"));
            g.drawImage(img, 853, 86, this);
            img = getImage(new URL("file", null, "C:\\Users\\Vova\\OOP_Kursova\\src\\Резерв Ост топл.png"));
            g.drawImage(img, 853, 146, this);
            img = getImage(new URL("file", null, "C:\\Users\\Vova\\OOP_Kursova\\src\\Дизб топл.png"));
            g.drawImage(img, 853, 205, this);
            /* Выводим рисунок 3 */
            img = getImage(new URL("file", null, "C:\\Users\\Vova\\OOP_Kursova\\src\\Топливомер.jpg"));
            g.drawImage(img, 815, 350, this);
            /* Выводим рисунок 4 */
            img = getImage(new URL("file", null, "C:\\Users\\Vova\\OOP_Kursova\\src\\Топливомер(Выкл).png"));
            g.drawImage(img, 882, 390, this);
            /* Выводим текст1 */
            img = getImage(new URL("file", null, "C:\\Users\\Vova\\OOP_Kursova\\src\\Текст.png"));
            g.drawImage(img, 745, 270, this);
            img = getImage(new URL("file", null, "C:\\Users\\Vova\\OOP_Kursova\\src\\Текст2.png"));
            g.drawImage(img, 730, 530, this);

                /* Если мышка наводится на эту картинку, то мы изменяем картинку */
            if (n == 1) {
                img = getImage(new URL("file", null, "C:\\Users\\Vova\\OOP_Kursova\\src\\Топливомер(ВКЛ).jpg"));
                g.drawImage(img, 815, 350, this);
                /* Выводим рисунок 2 */
                img = getImage(new URL("file", null, "C:\\Users\\Vova\\OOP_Kursova\\src\\Топл сист - неисправна(ВКЛ).png"));
                g.drawImage(img, 853, 27, this);
                img = getImage(new URL("file", null, "C:\\Users\\Vova\\OOP_Kursova\\src\\Резерв остат топл(ВКЛ).png"));
                g.drawImage(img, 853, 146, this);
            }
            if (n == 2) {
                img = getImage(new URL("file", null, "C:\\Users\\Vova\\OOP_Kursova\\src\\Топл сист - неисправна(ВЫКЛ).png"));
                g.drawImage(img, 853, 27, this);
                img = getImage(new URL("file", null, "C:\\Users\\Vova\\OOP_Kursova\\src\\Резерв Ост топл.png"));
                g.drawImage(img, 853, 146, this);
            }
            if (n == 3) {
                img = getImage(new URL("file", null, "C:\\Users\\Vova\\OOP_Kursova\\src\\Показания(2).png"));
                g.drawImage(img, 122, 490, this);
            }
            if (n == 4) {
                img = getImage(new URL("file", null, "C:\\Users\\Vova\\OOP_Kursova\\src\\Показания(3).png"));
                g.drawImage(img, 122, 490, this);
            }
            if (n == 5) {
                img = getImage(new URL("file", null, "C:\\Users\\Vova\\OOP_Kursova\\src\\Показания(4).png"));
                g.drawImage(img, 122, 490, this);
            }
            if (n == 6) {
                img = getImage(new URL("file", null, "C:\\Users\\Vova\\OOP_Kursova\\src\\Показания(5).png"));
                g.drawImage(img, 122, 490, this);
            }
            if (n == 7) {
                img = getImage(new URL("file", null, "C:\\Users\\Vova\\OOP_Kursova\\src\\Показания(6).png"));
                g.drawImage(img, 122, 490, this);
            }
            if (n == 8) {
                img = getImage(new URL("file", null, "C:\\Users\\Vova\\OOP_Kursova\\src\\Показания(7).png"));
                g.drawImage(img, 122, 490, this);
            }
            if (n == 9) {
                img = getImage(new URL("file", null, "C:\\Users\\Vova\\OOP_Kursova\\src\\Показания(8).png"));
                g.drawImage(img, 122, 490, this);
            }
            if (n == 10) {
                img = getImage(new URL("file", null, "C:\\Users\\Vova\\OOP_Kursova\\src\\Показания(9).png"));
                g.drawImage(img, 122, 490, this);
            }
            if (n == 11) {
                img = getImage(new URL("file", null, "C:\\Users\\Vova\\OOP_Kursova\\src\\Показания(10).png"));
                g.drawImage(img, 122, 490, this);
            }
            if (n == 12) {
                img = getImage(new URL("file", null, "C:\\Users\\Vova\\OOP_Kursova\\src\\Показания(11).png"));
                g.drawImage(img, 122, 490, this);
            }
    } catch (Exception e) {
            e.printStackTrace();
        }

    }
}
