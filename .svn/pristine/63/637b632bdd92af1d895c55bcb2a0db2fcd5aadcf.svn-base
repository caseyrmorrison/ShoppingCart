
/*
 * TCSS 305 April 14, 2013 
 */

import java.util.HashMap;
import java.util.Map;

/**
 *
 * @author Casey Morrison
 * @version April 14, 2013
 */
public class ShoppingCart {
  
  /**
   * The shopping cart total has to reach this price to get a discount.
   */
  private static final double MEMBERSHIP_START_PRICE = 20.00;
  
  /**
   * The membership discount when you reach a $20.00 shopping cart.
   */
  private static final double MEMBERSHIP_DISCOUNT = 0.10;
  
  /**
   * Map used to hold the item and the price of the order.
   */
  private final Map<Item, Double> my_cart;
  
  /**
   * Boolean used to tell if the customer has a membership or not.
   */
  private boolean my_membership;
  
  /**
   * Constructor that creates an empty shopping cart.
   */
  public ShoppingCart() {
    my_cart = new HashMap<Item, Double>();
    my_membership = false;
  }
  
  /**
   * Adds an order to the shopping cart.
   * Replaces any previous order for an equivalent item with the new order.
   * 
   * @param the_order - an ItemOrder object to add to the shopping cart.
   */
  public void add(final ItemOrder the_order) {
    final Item item = the_order.getItem();
    final Double price = the_order.calculatePrice();
    
    my_cart.put(item, price);
  }
  
  /**
   * Sets whether or not the customer for this shopping cart has a store
   * membership (true if the customer does, false if the customer doesn't).
   * 
   * @param the_value - true = has membership card, false = no membership card.
   */
  public void setMembership(final Boolean the_value) {
    my_membership = the_value;
  }
  
  /**
   * Returns the total cost of this shopping cart.
   * 
   * @return the total value of all the items checked for purchase.
   */
  public double calculateTotal() {
    double total = 0.00;
    
    for (Map.Entry<Item, Double> entry : my_cart.entrySet()) {
      final Double value = entry.getValue();
      total += value;
    }
    
    if (my_membership && total > MEMBERSHIP_START_PRICE) {
      total = total - (total * MEMBERSHIP_DISCOUNT);
    }
    
    return total;
  }
}
