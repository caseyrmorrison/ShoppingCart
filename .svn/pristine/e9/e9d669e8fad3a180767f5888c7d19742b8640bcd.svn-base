/*
 * TCSS 305 April 14, 2013 
 */

import java.text.NumberFormat;
import java.util.Objects;

/**
 * An Item object stores information about an individual item.
 * It is used in the ShoppingCart class and the ItemOrder class.
 *
 * @author Casey Morrison
 * @version April 14, 2013
 */
public class Item {
  
  // constants (static final fields)
  
  /**
   * A format string for decimal numbers.
   */
  private static final NumberFormat FORMAT = NumberFormat.getCurrencyInstance();
  
  // non constant fields.
  
  /**
   * String that holds the name of the item.
   */
  private final String my_name;
  
  /**
   * A double that holds the price of the item.
   */
  private final double my_price;
  
  /**
   * An int that validates the quantity needed for bulk pricing.
   */
  private final int my_bulk_quantity;
  
  /**
   * A double that holds the price for bulk orders.
   */
  private final double my_bulk_price;
  
  /**
   * Constructor that takes a name and a price as arguments.
   * 
   * @param the_name - String used as the name of the Item.
   * @param the_price - double used as the price of each item.
   */
  public Item(final String the_name, final double the_price) {
    this(the_name, the_price, 0, 0.0);
  }
  
  /**
   * Constructor that takes a name, a single-item price, a bulk quantity,
   * and a bulk price as arguments.
   * 
   * @param the_name - String creating the name of the Item.
   * @param the_price - double valuing the price of the Item.
   * @param the_bulk_quantity - showing the quantity needed to validate the order as bulk.
   * @param the_bulk_price - double valuing the bulk price of the Item.
   */
  public Item(final String the_name, final double the_price, final int the_bulk_quantity,
              final double the_bulk_price) {
    my_name = the_name;
    my_price = the_price;
    my_bulk_quantity = the_bulk_quantity;
    my_bulk_price = the_bulk_price;
  }
  
  /**
   * Returns the price for a given quantity of the item.
   * 
   * @param the_quantity - integer, quantity used for calculations.
   * @return price * quantity - the price for the amount of the item.
   */
  public double calculatePriceFor(final int the_quantity) {
    int ammount_bulk;
    int leftover;
    double total = 0;
    
    // if there is a bulk quantity and price, calculate it this way:
    if (my_bulk_quantity > 0 && my_bulk_price > 0 && the_quantity >= my_bulk_quantity) {
      ammount_bulk = the_quantity / my_bulk_quantity;
      leftover = the_quantity % my_bulk_quantity;
      if (leftover != 0) {
        total = my_price * leftover;
        total += my_bulk_price * ammount_bulk;
      } 
      total = my_bulk_price * ammount_bulk;
    } else {
      total = my_price * the_quantity;
    }
    return total;
  }
  
  /**
   * {@inheritDoc}
   */
  @Override
  public String toString() {
    final String text_price = FORMAT.format(my_price);
    final String text_bulk_price = FORMAT.format(my_bulk_price);
    final StringBuilder sb = new StringBuilder();
    sb.append(my_name);
    sb.append(", ");
    sb.append(text_price);
    if (my_bulk_price > 0 && my_bulk_quantity > 0) {
      sb.append(" (");
      sb.append(my_bulk_quantity);
      sb.append(" for ");
      sb.append(text_bulk_price);
      sb.append(")");
    }
    return sb.toString();
  }
  
  /**
   * {@inheritDoc}
   */
  @Override
  public boolean equals(final Object the_other) {
    
    // return if this happens to be identical to the_other
    if (this == the_other) {
      return true;
    }
    
    // return false if the parameter is null
    if (the_other == null) {
      return false;
    }
    
    // return false if the parameter is not an Item
    if (getClass() != the_other.getClass()) {
      return false;
    }
    
    // cast the object to an Item
    final Item other_item = (Item) the_other;
    
    // now compare fields for equality.
    return Objects.equals(my_name, other_item.my_name)
        && my_price == other_item.my_price;
  }

  /**
   * {@inheritDoc}
   */
  @Override
  public int hashCode() {
    // hash the same fields that the .equals() method uses.
    return Objects.hash(my_name, my_price); 
  }
}
