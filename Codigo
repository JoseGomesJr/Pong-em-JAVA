/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */
package pongfisica;

import java.awt.Color;
import java.awt.Graphics;
import java.awt.Graphics2D;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.awt.event.KeyEvent;
import java.awt.event.KeyListener;
import java.awt.geom.Rectangle2D;
import javax.swing.JFrame;
import javax.swing.JPanel;
import javax.swing.Timer;

/**
 *
 * @author josej
 */

public class PongFisica extends JFrame implements ActionListener{
    Grafico gr;
    Timer time;
    int bx=390,by=255,vx=3,vy=3,dir=0;
    int jy=215,pcy=215;
    @Override
    public void actionPerformed(ActionEvent ae) {
        joga();
    }
    
    public void joga(){
        
        bx+=vx;
        by+=vy;
        gr.repaint();
        if(by<20 || by>530)
        {
            vy*=-1;
        }
        if(bx<35 && bx>15 && by+20>jy && by+20< jy+100){
            vx*=-1;
            dir=0;
        }
        if(bx+20>760 && bx+20<780 && by+20>pcy && by < pcy+100 && dir==0){
            vx*=-1;
            dir=1;
        }
        
        if(bx>350 && vx>0){
            if(by>pcy+50 && pcy+100<550)
            {
                pcy+=3;
            }
            else if(vy<0 && pcy>20 && by<pcy+50){
                pcy-=3;
            }
        }
        if(bx<5 || bx>800)
        {
            dir=0;
            bx=390;
            by=255;
            vx=3;
            vy=3;
        }  
    }
    public class Grafico extends JPanel{
        @Override
        public void paintComponent(Graphics g){
            super.paintComponent(g);
            setBackground(Color.BLACK);
            Graphics2D bola= (Graphics2D) g;
            Graphics2D jogador= (Graphics2D) g;
            Graphics2D pc= (Graphics2D) g;
            Graphics2D par1= (Graphics2D) g;
            Graphics2D par2= (Graphics2D) g;
            Graphics2D par3= (Graphics2D) g;
            bola.setColor(Color.white);
            par1.setColor(Color.white);
            par2.setColor(Color.white);
            bola.fill(new Rectangle2D.Double(bx,by,20,20));
            par1.fill(new Rectangle2D.Double(0,10,800,10));
            par2.fill(new Rectangle2D.Double(0,550,800,10));
            par3.fill(new Rectangle2D.Double(395,10,10,550));
            jogador.fill(new Rectangle2D.Double(15,jy,20,100));
            pc.fill(new Rectangle2D.Double(760,pcy,20,100));
            
        }
    }
    public void Janela(){
        setTitle("Pong");
        setSize(800,600);
        setLocationRelativeTo(null);
        setResizable(false);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setVisible(true);
        gr=new Grafico();
        add(gr);
        time = new Timer(2, this);
        time.start();
    }
    public void controle(){
        addKeyListener(new KeyListener() {
            @Override
            public void keyTyped(KeyEvent e) {
              
            }

            @Override
            public void keyPressed(KeyEvent e) {
               if(e.getKeyCode()==38 && jy>20){
                   jy-=10;
               }
               else if(e.getKeyCode()==40 && jy<450)
               {
                   jy+=10;
               }
            }

            @Override
            public void keyReleased(KeyEvent e) {
            
            }
        });
    }

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        // TODO code application logic here
        PongFisica janela= new PongFisica();
        janela.Janela();
        janela.controle();
    }
    
}
