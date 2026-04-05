# 抖音网红爱心代码
代码杂货铺
import javax.swing.*;
import java.awt.*;
import java.util.ArrayList;
import java.util.Random;

public class randomtext {
    public static void main(String[] args) {
    
        String[] data = {"1","2","3","4"};

        int w = Toolkit.getDefaultToolkit().getScreenSize().width;
        int h = Toolkit.getDefaultToolkit().getScreenSize().height;
        w -= 300;
        h -= 250;


        ArrayList<JFrame> jfarr = new ArrayList<>();//new一个数组来装窗口
        for (double t = 0; t < 6.28; t += 0.05) {

            Random rd = new Random();
            //随机颜色
            int r = rd.nextInt(256);
            int g = rd.nextInt(256);
            int b = rd.nextInt(256);
            //随机获取字符串
            String s = data[rd.nextInt(data.length)];
            // 爱心数学公式
            int x = (int) (w / 2 + 16 * Math.pow(Math.sin(t), 3) * 40);
            int y = (int) (h / 2 - (13 * Math.cos(t) - 5 * Math.cos(2 * t) - 2 * Math.cos(3 * t) - Math.cos(4 * t)) * 30);
            //爱心窗口运行时间
            try {
                Thread.sleep(100);
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
            //创建窗口
            JFrame jf2 = new JFrame();
            jf2.setBounds(x, y, 300, 150);
            jf2.getContentPane().setBackground(new Color(r, g, b));//设置颜色
            JLabel jl = new JLabel(s,SwingConstants.CENTER);//new文字
            jl.setFont(new Font("正常",Font.PLAIN,50));//设置字体
            jf2.add(jl);
            jf2.setVisible(true);
            jfarr.add(jf2);//将窗口添加到数组中
            jf2.setDefaultCloseOperation(WindowConstants.EXIT_ON_CLOSE);
        }
        //延迟关闭
        try {
            Thread.sleep(500);
        }catch (InterruptedException e) {
            e.printStackTrace();
        }
        //关闭窗口
        for (int ds = 0;ds <jfarr.size();ds++){
            jfarr.get(ds).dispose();
            //关闭时长
            try {
                Thread.sleep(50);
            }catch (InterruptedException e){}
        }


            Random rd = new Random();
            for (int i = 0; i < 50; i++) {
                //延迟线程时间
                try {
                    Thread.sleep(100);
                } catch (InterruptedException e) {
                    e.printStackTrace();
                }
                //随机颜色号
                int r = rd.nextInt(256);
                int g = rd.nextInt(256);
                int d = rd.nextInt(256);
                String s = data[rd.nextInt(data.length)];

                JFrame jf = new JFrame();
                int b = rd.nextInt(2048)-50;//width.随机生成位置
                int c = rd.nextInt(1024)-75;//height，随机生成位置
                jf.setBounds(b,c,300,150);//窗口位置，宽度和高度，
                JLabel jl = new JLabel(s,SwingConstants.CENTER);
                jl.setFont(new Font("正常",Font.PLAIN,50));//设置字体
                jf.add(jl);
                jf.getContentPane().setBackground(new Color(r, g, d));//定义颜色
                jf.setVisible(true);
                jf.setDefaultCloseOperation(WindowConstants.EXIT_ON_CLOSE);
            }
        }

}
