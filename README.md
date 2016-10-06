import javax.swing.*;
import java.awt.*;
import java.awt.event.*;


public class BMI2 extends JFrame {
	//定义变量
	JLabel lblPrompt,lblHeight,lblWeight,lblYear,lblBMI,lblChestline,lblWaistline,lblHipline,lblAbdomenline,lblThighline,lblBMR,lblBFR,lblBHR,lblBW,lblResult6,lblResult7,lblReference1,lblReference2,lblReference3,lblReference4,lblReference5,lblReference6,lblReference7,lblReference8;
	JButton btnRun,btnClear;
	JPanel pnlMain;
	JTextField txtHeight,txtWeight,txtYear,txtBMI,txtResult1,txtChestline,txtWaistline,txtHipline,txtAbdomenline,txtThighline,txtBMR,txtBFR,txtBHR,txtBW,txtResult6,txtResult7;
	Dimension dsSize;

	    
	  public BMI2() {
	  	    lblPrompt = new JLabel("请输入您的身高,体重,年龄:");
	    	lblHeight = new JLabel("身高（米/m）");
	    	txtHeight = new JTextField(10);
	    	lblWeight = new JLabel("体重（千克/kg）");
	    	txtWeight = new JTextField(10);
	    	lblYear = new JLabel("年龄（岁/year）");
	    	txtYear = new JTextField(10);
	    	lblReference1 = new JLabel("参考数据:");
	    	lblReference2 = new JLabel("基础代谢标准范围：18～29岁 1210kcal/日；30～49岁1170kcal/日； 50～69岁  1110kcal/日 ；70岁以上  1,010kcal/日。");
	        lblReference3 = new JLabel("BMI标准范围：过轻：低于18.5 ;正常：18.5-24.99;过重：25-28;肥胖：28-32;非常肥胖, 高于32。");
	    	lblReference4 = new JLabel("BMI:Body Mass Index,身体质量指数，简称：体质指数");
	    	lblReference5 = new JLabel("BMR:基础代谢率");
	    	lblReference6 = new JLabel("BFR:体脂态");
	    	lblReference7 = new JLabel("BW:适宜体重");
	    	lblReference8 = new JLabel("BHR:最佳运动心率控制范围");
	    		    	    	
	    	btnRun = new JButton("计算");//绿色的想填监听器，可是出错。。
	    	//btnRun.setToolTipText("请按计算键");//设置计算键
	    	//btnRun.setForeground(Color.RED);//设置字体颜色
            //btnRun.setBackground(Color.YELLOW);//设置背景色
            //btnRun.addActionListener(this);
	    	btnClear = new JButton("清除");
	    	//btnClear.setToolTipText("请按清除键!");//设置清零键
            //btnClear.setForeground(Color.RED);//设置字体颜色
            //btnClear.setBackground(Color.YELLOW);//设置背景色
            //btnClear.addActionListener(this);
	    	
	    	lblChestline = new JLabel("胸围(cm)");
            txtChestline = new JTextField(10);
	    	lblWaistline = new JLabel("腰围(cm)");
	        txtWaistline = new JTextField(10);	        	    	
	        lblHipline = new JLabel("臀围(cm)");
	        txtHipline = new JTextField(10);	        	    	
	        lblAbdomenline = new JLabel("腹围(cm)");
	        txtAbdomenline = new JTextField(10);	       	    	
	        lblThighline = new JLabel("大腿围(cm)");
	        txtThighline = new JTextField(10);	        
	        lblBMI = new JLabel("BMI");
	    	txtBMI = new JTextField(10);
	    	lblResult6 = new JLabel("评估");
	    	txtResult6 = new JTextField(10);
	        lblBMR = new JLabel("BMR");
	        txtBMR = new JTextField(10);
	        lblResult7 = new JLabel("评估");
	    	txtResult7 = new JTextField(10);
	        lblBFR = new JLabel("BFR");
	        txtBFR = new JTextField(10);	        
	        lblBHR = new JLabel("BHR");
	        txtBHR = new JTextField(10);	        
	        lblBW = new JLabel("BW");
	        txtBW = new JTextField(10);
	        	    	    		        
	    	pnlMain = new JPanel();
	    	pnlMain.setLayout(null);
	    	lblPrompt.setBounds(70,20,600,25);
	    	// 给身高体重年龄设置位置
	    	lblHeight.setBounds(200,50,150,25);
	        txtHeight.setBounds(300,50,100,25);
	        lblWeight.setBounds(200,80,150,25);
	        txtWeight.setBounds(300,80,100,25);
	        lblYear.setBounds(200,110,150,25);
	        txtYear.setBounds(300,110,100,25);
	        //给评估按钮设置位置
	        btnRun.setBounds(200,150,70,25);
	        btnClear.setBounds(300,150,70,25);
	        //给10个待测值设置位置
	        lblChestline.setBounds(80,200,80,25);
	        txtChestline.setBounds(150,200,90,25);
	        lblWaistline.setBounds(80,230,80,25);
            txtWaistline.setBounds(150,230,90,25);                       
            lblHipline.setBounds(80,260,80,25);
	        txtHipline.setBounds(150,260,90,25);	        	        	        
	        lblAbdomenline.setBounds(80,290,80,25);
	        txtAbdomenline.setBounds(150,290,90,25);	        
	        lblThighline.setBounds(78,320,80,25);
	        txtThighline.setBounds(150,320,90,25);	        
	        lblBMI.setBounds(330,200,80,25);
	        txtBMI.setBounds(375,200,60,25);
	        lblResult6.setBounds(450,200,80,25);
	        txtResult6.setBounds(490,200,40,25);	        
	        lblBMR.setBounds(330,230,80,25);
	        txtBMR.setBounds(375,230,60,25);
	        lblResult7.setBounds(450,230,80,25);
	        txtResult7.setBounds(490,230,40,25);
	        lblBHR.setBounds(330,260,80,25);
	        txtBHR.setBounds(375,260,90,25);	        
	        lblBFR.setBounds(330,290,80,25);
	        txtBFR.setBounds(375,290,90,25);	        
	        lblBW.setBounds(330,320,80,25);
	        txtBW.setBounds(375,320,90,25);	        
	        lblReference1.setBounds(30,400,100,25);
	        lblReference2.setBounds(15,430,700,25);
	        lblReference3.setBounds(15,460,700,25);
	        lblReference4.setBounds(15,490,700,25);
	        lblReference5.setBounds(15,520,700,25);
	        lblReference6.setBounds(15,550,700,25);
	        lblReference7.setBounds(15,580,700,25);
	        lblReference8.setBounds(15,610,700,25);
	        
	       	//将标签添加到面板上
	       	pnlMain.add(lblPrompt);        
	        pnlMain.add(lblHeight);
	        pnlMain.add(txtHeight);
	        pnlMain.add(lblWeight);
	        pnlMain.add(txtWeight);
	        pnlMain.add(lblYear);
	        pnlMain.add(txtYear);
	        pnlMain.add(btnRun);
	        pnlMain.add(btnClear);
	        pnlMain.add(lblChestline);
	        pnlMain.add(txtChestline);	        
	        pnlMain.add(lblWaistline);
	        pnlMain.add(txtWaistline);
	        pnlMain.add(lblHipline);
	        pnlMain.add(txtHipline);
	        pnlMain.add(lblAbdomenline);
	        pnlMain.add(txtAbdomenline);
	        pnlMain.add(lblThighline);
	        pnlMain.add(txtThighline);
	        pnlMain.add(lblBMI);
	        pnlMain.add(txtBMI);
	        pnlMain.add(lblResult6);
	        pnlMain.add(txtResult6);
	        pnlMain.add(lblBMR);
	        pnlMain.add(txtBMR);
	        pnlMain.add(lblResult7);
	        pnlMain.add(txtResult7);
	        pnlMain.add(lblBFR);
	        pnlMain.add(txtBFR);
	        pnlMain.add(lblBHR);
	        pnlMain.add(txtBHR);
	        pnlMain.add(lblBW);
	        pnlMain.add(txtBW);
	        pnlMain.add(lblReference1);
	        pnlMain.add(lblReference2);
	        pnlMain.add(lblReference4);
	        pnlMain.add(lblReference5);
	        pnlMain.add(lblReference6);
	        pnlMain.add(lblReference7);
	        pnlMain.add(lblReference3);
	        pnlMain.add(lblReference8);
	        
	        this.setContentPane(pnlMain);
	        setSize(730,700);
	        setTitle("Soso身体健康指标计算器");
	        setVisible(true);
	        setResizable(false);
	        this.setDefaultCloseOperation(EXIT_ON_CLOSE);
	        this.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);	     	      	        	      
	    }
        
	  public static void main(String[] args){
	    	new BMI2();
	    }
;}



//基础代谢标准范围：18～29岁 1210kcal/日；30～49岁1170kcal/日； 50～69岁  1110kcal/日 ；70岁以上  1,010kcal/日
//BMI标准范围：过轻：低于18.5 ;正常：18.5-24.99;过重：25-28;肥胖：28-32;非常肥胖, 高于32
//BMI:Body Mass Index,身体质量指数，简称：体质指数
//BMR:基础代谢率
//BFR:体脂态
//BW:适宜体重
//BHR:最佳运动心率控制范围
