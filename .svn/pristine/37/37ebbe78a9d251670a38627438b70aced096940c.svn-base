import static org.junit.Assert.*;

import org.junit.Before;
import org.junit.Test;

/*
 * TCSS 305 April 16, 2013 
 */

/**
 *
 *
 * @author Casey Morrison
 * @version April 16, 2013
 */
public class ItemTest {

  /** A tolerance used when testing double values for equality. */
  private static final double TOLERANCE = .00001;
  
  // The test fixture. The Item objects I will use in the tests.
  
  /** An Item to use in tests. */
  private Item my_item;
  
  /** Another Item to use in tests. */
  private Item my_other_item;
  
  /**
   * Sets up the test fixture. 
   */
  @Before
  public void setUp() {
    my_item = new Item("Item1", 5.0); // no bulk values
    my_other_item = new Item("Item2", 6.0, 10, 20.0); // setting the bulk values
  }

  /**
   * Test method for HashCode.
   */
  @Test
  public void testHashCode() {
    // equal objects should have equal hashCode values.
    final Item item1 = my_item;
    
    assertEquals("These are not equal!", item1.hashCode(), my_item.hashCode());
  }

  /**
   * Test of the overloaded Item constructor.
   * Test method for Item(String, double).
   */
  @Test
  public void testItemStringDouble() {
    // test to see if the fields were set correctly
    assertEquals("They are not equal.", "Item1, $5.00", my_item.toString());
    assertNotSame(my_item, my_other_item);
  }

  /**
   * Test of the default Item constructor.
   * Test method for Item(String, double, int, double).
   */
  @Test
  public void testItemStringDoubleIntDouble() {
    assertEquals("They are not equal.", "Item2, $6.00 (10 for $20.00)",
                 my_other_item.toString());
    assertNotSame(my_item, my_other_item);
  }

  /**
   * Test method for calculatePriceFor(int).
   */
  @Test
  public void testCalculatePriceFor() {
    assertEquals(10.0, my_item.calculatePriceFor(2), TOLERANCE);
    assertEquals(20.0, my_other_item.calculatePriceFor(10), TOLERANCE);
  }

  /**
   * Test method for toString().
   */
  @Test
  public void testToString() {
    assertEquals("toString() returns an incorrect result!", "Item2, $6.00 (10 for $20.00)",
                 my_other_item.toString());
    
    assertEquals("toString() returns an incorrect result!",
                 "Item1, $5.00", my_item.toString());
  }

  /**
   * Test method for equals(java.lang.Object).
   */
  @Test
  public void testEqualsObject() {
    // an object is equal to itself - reflexive property
    assertEquals("The Items aren't the same.", my_item, my_item);
    
    // an object compared with a different type of object should return false
    assertFalse("The types aren't the same.", my_item.equals(new ShoppingCart()));
    
    // the symmetric property should hold
    assertEquals("Not equal", my_other_item, new Item("item3", 8));
    assertEquals("Note equal", new Item("item3", 8), my_other_item);
    
    assertFalse("Not equal.", my_other_item.equals(new Item("item8", 10)));
  }

}
