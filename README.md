
# Aplikasi Penghitung Kata

# Deskripsi
    "Aplikasi Penghitung Kata". 

Judul Aplikasi: "Aplikasi Penghitung Kata" ditampilkan dengan teks tebal di bagian atas jendela.

Area Teks: Sebuah area teks (TextArea) besar di tengah, tempat pengguna dapat mengetikkan teks.

Label Informasi:
"Jumlah Kata: 0"
"Jumlah Karakter: 0"
"Jumlah Kalimat: 0" Ketiga label ini menampilkan jumlah kata, karakter, dan kalimat berdasarkan teks yang dimasukkan.

Tombol:
"Hitung": Untuk menghitung jumlah kata, karakter, dan kalimat.
"Simpan": Untuk menyimpan hasil perhitungan ke dalam file.

Tata Letak:
Elemen-elemen tersusun secara rapi dengan orientasi vertikal di dalam jendela aplikasi.












# coding

## coding Java Aplikasi Penghitung Kata
```java

import javax.swing.*; // Untuk JLabel, JTextArea, JScrollPane, JButton, dll.
import java.awt.event.ActionEvent; // Untuk event action
import java.awt.event.ActionListener; // Untuk ActionListener
import javax.swing.JFileChooser;
import java.io.File;
import java.io.PrintWriter;
import java.io.FileNotFoundException;



public class PenghitungKata extends javax.swing.JFrame {

    /**
     * Creates new form PenghitungKata
     */
    public PenghitungKata() {
        initComponents();
    TextAreaInput.getDocument().addDocumentListener(new javax.swing.event.DocumentListener() {
    @Override
    public void insertUpdate(javax.swing.event.DocumentEvent e) {
        hitungOtomatis();
    }

    @Override
    public void removeUpdate(javax.swing.event.DocumentEvent e) {
        hitungOtomatis();
    }

    @Override
    public void changedUpdate(javax.swing.event.DocumentEvent e) {
        hitungOtomatis();
    }

    // Method untuk melakukan perhitungan otomatis
    private void hitungOtomatis() {
        String teks = TextAreaInput.getText();
        
        // Menghitung jumlah karakter
        int jumlahKarakter = teks.length();

        // Menghitung jumlah kata
        String[] kataArray = teks.trim().split("\\s+");
        int jumlahKata = (teks.isEmpty()) ? 0 : kataArray.length;

        // Menghitung jumlah kalimat
        String[] kalimatArray = teks.split("[.!?]");
        int jumlahKalimat = (teks.isEmpty()) ? 0 : kalimatArray.length;

        // Menampilkan hasil pada JLabel
        LabelJumlahKata.setText("Jumlah Kata: " + jumlahKata);
        LabelJumlahKarakter.setText("Jumlah Karakter: " + jumlahKarakter);
        LabelJumlahKalimat.setText("Jumlah Kalimat: " + jumlahKalimat);
    }
});

    }

    /**
     * This method is called from within the constructor to initialize the form.
     * WARNING: Do NOT modify this code. The content of this method is always
     * regenerated by the Form Editor.
     */
    @SuppressWarnings("unchecked")
    // <editor-fold defaultstate="collapsed" desc="Generated Code">                          
    private void initComponents() {

        jPanel1 = new javax.swing.JPanel();
        jScrollPane2 = new javax.swing.JScrollPane();
        TextAreaInput = new javax.swing.JTextArea();
        ButtonHitung = new javax.swing.JButton();
        LabelJumlahKata = new javax.swing.JLabel();
        LabelJumlahKarakter = new javax.swing.JLabel();
        LabelJumlahKalimat = new javax.swing.JLabel();
        ButtonSimpan = new javax.swing.JButton();
        jLabel1 = new javax.swing.JLabel();

        setDefaultCloseOperation(javax.swing.WindowConstants.EXIT_ON_CLOSE);

        TextAreaInput.setColumns(20);
        TextAreaInput.setRows(5);
        jScrollPane2.setViewportView(TextAreaInput);

        ButtonHitung.setText("Hitung");
        ButtonHitung.addActionListener(new java.awt.event.ActionListener() {
            public void actionPerformed(java.awt.event.ActionEvent evt) {
                ButtonHitungActionPerformed(evt);
            }
        });

        LabelJumlahKata.setText("Jumlah Kata");

        LabelJumlahKarakter.setText("Jumlah Karakter");

        LabelJumlahKalimat.setText("Jumlah Kalimat");

        ButtonSimpan.setText("Simpan");
        ButtonSimpan.addActionListener(new java.awt.event.ActionListener() {
            public void actionPerformed(java.awt.event.ActionEvent evt) {
                ButtonSimpanActionPerformed(evt);
            }
        });

        jLabel1.setFont(new java.awt.Font("Tahoma", 1, 24)); // NOI18N
        jLabel1.setText("Aplikasi Penghitung Kata");

        javax.swing.GroupLayout jPanel1Layout = new javax.swing.GroupLayout(jPanel1);
        jPanel1.setLayout(jPanel1Layout);
        jPanel1Layout.setHorizontalGroup(
            jPanel1Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
            .addGroup(jPanel1Layout.createSequentialGroup()
                .addGroup(jPanel1Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                    .addGroup(jPanel1Layout.createSequentialGroup()
                        .addGap(23, 23, 23)
                        .addGroup(jPanel1Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                            .addComponent(LabelJumlahKarakter, javax.swing.GroupLayout.PREFERRED_SIZE, 132, javax.swing.GroupLayout.PREFERRED_SIZE)
                            .addComponent(LabelJumlahKalimat, javax.swing.GroupLayout.PREFERRED_SIZE, 132, javax.swing.GroupLayout.PREFERRED_SIZE)
                            .addComponent(LabelJumlahKata, javax.swing.GroupLayout.PREFERRED_SIZE, 132, javax.swing.GroupLayout.PREFERRED_SIZE)))
                    .addGroup(jPanel1Layout.createSequentialGroup()
                        .addGap(113, 113, 113)
                        .addGroup(jPanel1Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                            .addComponent(jScrollPane2, javax.swing.GroupLayout.PREFERRED_SIZE, 524, javax.swing.GroupLayout.PREFERRED_SIZE)
                            .addGroup(jPanel1Layout.createSequentialGroup()
                                .addGap(107, 107, 107)
                                .addComponent(jLabel1)))))
                .addGap(0, 179, Short.MAX_VALUE))
            .addGroup(jPanel1Layout.createSequentialGroup()
                .addGap(170, 170, 170)
                .addComponent(ButtonHitung, javax.swing.GroupLayout.PREFERRED_SIZE, 112, javax.swing.GroupLayout.PREFERRED_SIZE)
                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED, javax.swing.GroupLayout.DEFAULT_SIZE, Short.MAX_VALUE)
                .addComponent(ButtonSimpan, javax.swing.GroupLayout.PREFERRED_SIZE, 112, javax.swing.GroupLayout.PREFERRED_SIZE)
                .addGap(201, 201, 201))
        );
        jPanel1Layout.setVerticalGroup(
            jPanel1Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
            .addGroup(jPanel1Layout.createSequentialGroup()
                .addContainerGap(47, Short.MAX_VALUE)
                .addComponent(jLabel1)
                .addGap(30, 30, 30)
                .addComponent(jScrollPane2, javax.swing.GroupLayout.PREFERRED_SIZE, 157, javax.swing.GroupLayout.PREFERRED_SIZE)
                .addGap(38, 38, 38)
                .addComponent(LabelJumlahKata, javax.swing.GroupLayout.PREFERRED_SIZE, 36, javax.swing.GroupLayout.PREFERRED_SIZE)
                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.UNRELATED)
                .addComponent(LabelJumlahKarakter, javax.swing.GroupLayout.PREFERRED_SIZE, 36, javax.swing.GroupLayout.PREFERRED_SIZE)
                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.UNRELATED)
                .addComponent(LabelJumlahKalimat, javax.swing.GroupLayout.PREFERRED_SIZE, 29, javax.swing.GroupLayout.PREFERRED_SIZE)
                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                .addGroup(jPanel1Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.BASELINE)
                    .addComponent(ButtonHitung, javax.swing.GroupLayout.PREFERRED_SIZE, 42, javax.swing.GroupLayout.PREFERRED_SIZE)
                    .addComponent(ButtonSimpan, javax.swing.GroupLayout.PREFERRED_SIZE, 42, javax.swing.GroupLayout.PREFERRED_SIZE))
                .addGap(31, 31, 31))
        );

        javax.swing.GroupLayout layout = new javax.swing.GroupLayout(getContentPane());
        getContentPane().setLayout(layout);
        layout.setHorizontalGroup(
            layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
            .addComponent(jPanel1, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, Short.MAX_VALUE)
        );
        layout.setVerticalGroup(
            layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
            .addComponent(jPanel1, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, Short.MAX_VALUE)
        );

        pack();
    }// </editor-fold>                        

    private void ButtonHitungActionPerformed(java.awt.event.ActionEvent evt) {                                             
        String teks = TextAreaInput.getText();
    
    // Menghitung jumlah karakter
    int jumlahKarakter = teks.length();

    // Menghitung jumlah kata (berdasarkan spasi atau pemisah kata)
    String[] kataArray = teks.trim().split("\\s+");
    int jumlahKata = (teks.isEmpty()) ? 0 : kataArray.length;

    // Menghitung jumlah kalimat (berdasarkan tanda titik, seru, atau tanya)
    String[] kalimatArray = teks.split("[.!?]");
    int jumlahKalimat = (teks.isEmpty()) ? 0 : kalimatArray.length;
    

    // Menampilkan hasil pada JLabel
    LabelJumlahKata.setText("Jumlah Kata: " + jumlahKata);
    LabelJumlahKarakter.setText("Jumlah Karakter: " + jumlahKarakter);
    LabelJumlahKalimat.setText("Jumlah Kalimat: " + jumlahKalimat);
    }                                            

    private void ButtonSimpanActionPerformed(java.awt.event.ActionEvent evt) {                                             
        JFileChooser fileChooser = new JFileChooser();
    if (fileChooser.showSaveDialog(this) == JFileChooser.APPROVE_OPTION) {
        File file = fileChooser.getSelectedFile();
        try (PrintWriter writer = new PrintWriter(file)) {
            writer.println("Teks:");
            writer.println(TextAreaInput.getText());
            writer.println("\nHasil Perhitungan:");
            writer.println("Jumlah Kata: " + LabelJumlahKata.getText());
            writer.println("Jumlah Karakter: " + LabelJumlahKarakter.getText());
            writer.println("Jumlah Kalimat: " + LabelJumlahKalimat.getText());
            JOptionPane.showMessageDialog(this, "File berhasil disimpan.");
        } catch (FileNotFoundException e) {
            e.printStackTrace();
            JOptionPane.showMessageDialog(this, "Terjadi kesalahan saat menyimpan file.");
        }
    }
    

    }                                            

    /**
     * @param args the command line arguments
     */
    public static void main(String args[]) {
        /* Set the Nimbus look and feel */
        //<editor-fold defaultstate="collapsed" desc=" Look and feel setting code (optional) ">
        /* If Nimbus (introduced in Java SE 6) is not available, stay with the default look and feel.
         * For details see http://download.oracle.com/javase/tutorial/uiswing/lookandfeel/plaf.html 
         */
        try {
            for (javax.swing.UIManager.LookAndFeelInfo info : javax.swing.UIManager.getInstalledLookAndFeels()) {
                if ("Nimbus".equals(info.getName())) {
                    javax.swing.UIManager.setLookAndFeel(info.getClassName());
                    break;
                }
            }
        } catch (ClassNotFoundException ex) {
            java.util.logging.Logger.getLogger(PenghitungKata.class.getName()).log(java.util.logging.Level.SEVERE, null, ex);
        } catch (InstantiationException ex) {
            java.util.logging.Logger.getLogger(PenghitungKata.class.getName()).log(java.util.logging.Level.SEVERE, null, ex);
        } catch (IllegalAccessException ex) {
            java.util.logging.Logger.getLogger(PenghitungKata.class.getName()).log(java.util.logging.Level.SEVERE, null, ex);
        } catch (javax.swing.UnsupportedLookAndFeelException ex) {
            java.util.logging.Logger.getLogger(PenghitungKata.class.getName()).log(java.util.logging.Level.SEVERE, null, ex);
        }
        //</editor-fold>

        /* Create and display the form */
        java.awt.EventQueue.invokeLater(new Runnable() {
            public void run() {
                new PenghitungKata().setVisible(true);
            }
        });
    }

    // Variables declaration - do not modify                     
    private javax.swing.JButton ButtonHitung;
    private javax.swing.JButton ButtonSimpan;
    private javax.swing.JLabel LabelJumlahKalimat;
    private javax.swing.JLabel LabelJumlahKarakter;
    private javax.swing.JLabel LabelJumlahKata;
    private javax.swing.JTextArea TextAreaInput;
    private javax.swing.JLabel jLabel1;
    private javax.swing.JPanel jPanel1;
    private javax.swing.JScrollPane jScrollPane2;
    // End of variables declaration                   
}




```
## PEMBUAT
Ahmad Said 
2210010264 5B


