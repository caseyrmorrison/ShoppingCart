/*
 * TCSS 305 April 14, 2013 
 */

/**
 * An ItemOrder object stores information about a purchase order for a particular item:
 * namely, a reference to the item itself and the quantity desired.
 *
 * @author Casey Morrison
 * @version April 14, 2013
 */
public class ItemOrder {
  
  /**
   * The item object used for the order.
   */
  private final Item my_item;
  
  /**
   * The quantity of the item used for the order.
   */
  private final int my_quantity;
  
  /**
   * Constructor that creates an item order for the given quantity of the
   * given Item.
   * 
   * @param the_item - item used to create an ItemOrder.
   * @param the_quantity - number of items wanted.
   */
  public ItemOrder(final Item the_item, final int the_quantity) {
    my_item = the_item;
    my_quantity = the_quantity;
  }
  
  /**
   * Returns the cost for this item order.
   * 
   * @return the price returned from the item.calculatePriceFor() method.
   */
  public double calculatePrice() {
    return my_item.calculatePriceFor(my_quantity);
  }
  
  /**
   * Returns a reference to the item in this order.
   * 
   * @return the item used in the order.
   */
  public Item getItem() {
    return my_item;
  }
}
