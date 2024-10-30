/**
* Kelas TicketBooking mengelola pemesanan tiket dengan harga tetap,
* serta menerapkan diskon jika jumlah tiket melebihi batas tertentu.
  */
  class TicketBooking {

  String customerName;
  int ticketCount;
  double ticketPrice = 10.0;

  /**
    * Konstruktor untuk membuat objek TicketBooking baru.
    *
    * @param customerName nama pelanggan
    * @param ticketCount  jumlah tiket yang dipesan
      */
      public TicketBooking(String customerName, int ticketCount) {
      this.customerName = customerName;
      this.ticketCount = ticketCount;
      }

  /**
    * Mencetak tanda terima yang menampilkan nama pelanggan, jumlah tiket,
    * dan total harga tanpa diskon.
      */
      public void printReceipt() {
      double totalPrice = ticketCount * ticketPrice;
      System.out.println("Customer: " + customerName);
      System.out.println("Total Tickets: " + ticketCount);
      System.out.println("Total Price: $" + totalPrice);
      }

  /**
    * Menerapkan diskon 10% jika jumlah tiket lebih dari 5
    * dan menampilkan harga setelah diskon.
      */
      public void applyDiscount() {
      if (ticketCount > 5) {
      double discount = 0.1; // Diskon 10%
      double totalPrice = ticketCount * ticketPrice;
      double discountedPrice = totalPrice - (totalPrice * discount);
      System.out.println("Discounted Price: $" + discountedPrice);
      }
      }

  /**
    * Menyatakan bahwa pemesanan telah dikonfirmasi untuk pelanggan.
      */
      public void confirmBooking() {
      System.out.println("Booking confirmed for " + customerName);
      }
      }

/**
* Kelas Main untuk menjalankan aplikasi pemesanan tiket.
  */
  public class Main {
  public static void main(String[] args) {
  // Membuat objek TicketBooking baru
  TicketBooking booking = new TicketBooking("John Doe", 6);

       // Mencetak tanda terima
       booking.printReceipt();

       // Menerapkan diskon jika memenuhi syarat
       booking.applyDiscount();

       // Mengonfirmasi pemesanan
       booking.confirmBooking();
  }
  }
