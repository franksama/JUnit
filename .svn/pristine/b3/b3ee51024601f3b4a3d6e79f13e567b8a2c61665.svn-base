import junit.framework.TestCase;

public class RationalTest extends TestCase {

    protected Rational HALF;

    protected void setUp() {
      HALF = new Rational( 1, 2 );
    }

    // Create new test
    public RationalTest (String name) {
        super(name);
    }

    public void testEquality() {
        assertEquals(new Rational(1,3), new Rational(1,3));
        assertEquals(new Rational(1,3), new Rational(2,6));
        assertEquals(new Rational(3,3), new Rational(1,1));
        assertEquals(new Rational(-1,3), new Rational(-1,3));
        assertEquals(new Rational(0,3), new Rational(0,3));
    }

    // Test for nonequality
    public void testNonEquality() {
        assertFalse(new Rational(2,3).equals(new Rational(1,3)));
        assertFalse(new Rational(-3,5).equals(new Rational(2,3)));
        assertFalse(new Rational(0,3).equals(new Rational(-1,5)));
        assertFalse(new Rational(0,3).equals(null));
        assertFalse(new Rational(1,3).equals(3));
    }

    public void testAccessors() {
    	assertEquals(new Rational(2,3).numerator(), 2);
    	assertEquals(new Rational(2,3).denominator(), 3);
    	assertEquals(new Rational(-2,3).numerator(), -2);
    	assertEquals(new Rational(0,3).numerator(), 0);
    }
    
    public void testNumerator() {
    	assertEquals(new Rational(1,4).numerator(), 1);
    	assertEquals(new Rational(-1,4).numerator(), -1);
    	assertEquals(new Rational(0,4).numerator(), 0);
    }
    
    public void testDenominator() {
    	assertEquals(new Rational(1,4).denominator(), 4);
    	assertEquals(new Rational(1,-4).denominator(), -4);
    	assertEquals(new Rational(0, 4).denominator(), 1);
    }
    
    public void testPlus() {
    	assertEquals(new Rational(1,5).plus(new Rational(2,5)), new Rational(3,5));
    	assertEquals(new Rational(0,5).plus(new Rational(2,5)), new Rational(2,5));
    	assertEquals(new Rational(-1,5).plus(new Rational(2,5)), new Rational(1,5));
    	assertEquals(new Rational(1,3).plus(new Rational(2,3)), new Rational(3,3));
    }
    
    public void testTimes() {
    	assertEquals(new Rational(2,5).times(new Rational(3,6)), new Rational(1,5));
    	assertEquals(new Rational(-1,5).times(new Rational(2,5)), new Rational(-2,25));
    	assertEquals(new Rational(0,5).times(new Rational(3,6)), new Rational(0,10));
    }
    
    public void testMinus() {
    	assertEquals(new Rational(2,5).minus(new Rational(3,6)), new Rational(-1,10));
    	assertEquals(new Rational(4,5).minus(new Rational(3,6)), new Rational(3,10));
    	assertEquals(new Rational(0,5).minus(new Rational(1,5)), new Rational(-1,5));
    }
    
    public void testDivides() {
    	assertEquals(new Rational(4,5).divides(new Rational(3,6)), new Rational(24,15));
    	assertEquals(new Rational(0,5).divides(new Rational(3,6)), new Rational(0,15));
    	assertEquals(new Rational(-1,5).divides(new Rational(1,2)), new Rational(-2,5));
    }
    
    public void testAbs() {
    	assertEquals(new Rational(-4, 5).abs(), new Rational(4,5));
    	assertEquals(new Rational(4, 5).abs(), new Rational(4,5));
    	assertEquals(new Rational(-4, -5).abs(), new Rational(4,5));
    }
    
    public void testToString() {
    	assertEquals(new Rational(-4, 5).toString(), "-4/5");
    	assertEquals(new Rational(0, 5).toString(), "0/1");
    	assertEquals(new Rational(2, 5).toString(), "2/5");
    }
    
    public void testIsLessThan() {
    	assertTrue(new Rational(1,5).isLessThan(new Rational(1,2)));
    	assertTrue(new Rational(-1,2).isLessThan(new Rational(1,5)));
    	assertTrue(new Rational(-1,6).isLessThan(new Rational(0,5)));
    }
    
    public void testRoot2() {
        Rational s = new Rational( 1, 8 );
        Rational sRoot = null;
        try {
            sRoot = s.root();
        } catch (IllegalArgumentToSquareRootException e) {
           e.printStackTrace();
        }
        assertFalse( sRoot.isLessThan( HALF.plus( Rational.getTolerance() ) ) && HALF.minus( Rational.getTolerance() ).isLessThan( sRoot ) ); 
    }
    
    public void testRoot() {
        Rational s = new Rational( -1, 8 );
        Rational sRoot = null;
        try {
            sRoot = s.root();
            fail("Expected IllegalArgumentToSquareRootException");
        } catch (IllegalArgumentToSquareRootException e) {
        }
    }
    
    public void testSetTolerance() {
    	Rational.setTolerance(HALF);
    	assertEquals(Rational.getTolerance(), HALF);
    }

    

    public static void main(String args[]) {
    	
        String[] testCaseName = { RationalTest.class.getName() };
        // junit.swingui.TestRunner.main(testCaseName);
        junit.textui.TestRunner.main(testCaseName);
        
        Rational test = new Rational(0, 4);
        System.out.println("test " + test.denominator());
    }
}
