package orneksinav;
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;


public class sinavKGA extends JFrame implements ActionListener{
 private double vizeNotu = 0;
 private double finalNotu = 0;
 private double sonuc ,a,b;

 private JLabel vizeEtiketi = new JLabel("Vize Notunuzu Giriniz: ");
 private JTextField vizeAlani = new JTextField(5);

 private JLabel finalEtiketi = new JLabel("Final Notunuzu Giriniz: ");
 private JTextField finalAlani = new JTextField(5);


 private JButton hesaplamaDugmesi = new JButton("Hesapla");
 private JTextArea yazdirmaAlani = new JTextArea(5, 20);

 public sinavKGA(){
 setTitle("Fonksiyon Köklerini Hesaplama");
 setLayout(new FlowLayout());
 setSize(280,220);
 setLocation(600, 300);
 add(vizeEtiketi);
 add(vizeAlani);
 add(finalEtiketi);
 add(finalAlani);
 add(hesaplamaDugmesi);
 add(yazdirmaAlani);
 hesaplamaDugmesi.addActionListener(this);
 setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
 setVisible(true);
 }
 public void actionPerformed(ActionEvent olay){
     
 String girilenVizeDegeri = vizeAlani.getText();
 String girilenFinalDegeri = finalAlani.getText();
 
 if(girilenVizeDegeri.length() == 0 || girilenFinalDegeri.length() == 0){
 yazdirmaAlani.setText("TextBox'ları Boş Bırakamzsınız !!");
 }
 else
 {
 a = Double.parseDouble(girilenVizeDegeri);
 b = Double.parseDouble(girilenFinalDegeri);
 if ((a<0 || a>100)&&(b<0 || b>100))
 {
 yazdirmaAlani.setText("Lütfen 0 ile 100 arasında bir değer giriniz !!");
 }
 else if(a<0 || a>100)
 {
 yazdirmaAlani.setText("Lütfen 0 ile 100 arasında bir Vize Notu giriniz !!");    
 }
 else if(b<0 || b>100)
 {
 yazdirmaAlani.setText("Lütfen 0 ile 100 arasında bir Final Notu giriniz !!");    
 }
 else{
 sonuc = (((a*40)/100)+((b*60)/100));
 if(sonuc<60)
 {
 yazdirmaAlani.setText("~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~\n Notunuz : "+sonuc+"\n~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~\n"+" SINIFTA KALDINIZ [!] \n~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~");
 }   
 else if(sonuc>60)
 {
 yazdirmaAlani.setText("~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~\n Notunuz : "+sonuc+"\n~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~\n"+" SINIFI GEÇTİNİZ [!] \n~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~");
 }
 else
 {
 yazdirmaAlani.setText("~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~\n Notunuz : "+sonuc+"\n~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~\n"+" HOCANIN İNSAFIYLA GEÇTİNİZ [!] \n~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~");
 }
 }
 } 
 }
 }
