package oglesby;

import java.io.RandomAccessFile;
import java.util.Date;

abstract class Painting {

protected String artistFirstName;
protected String artistLastName;
protected String titleOfWork;
protected String classification;
protected Date dateOfWork;
protected double height;
protected double width;
protected String medium;
protected String subject;
//protected double suggestedMaximumPurchasePrice;

public abstract boolean find(String alastname, String title);
public abstract void read (RandomAccessFile fileName);
public abstract void print ();
public abstract void save ();
public abstract void write (RandomAccessFile fileName);
public abstract void performDeletion ();

    public Painting(String first, String last, String title, String clas, Date dow, double h,
            double w, String med, String sub, double max )
    {
        artistFirstName=first;
        artistLastName=last;
        titleOfWork=title;
        classification=clas;
        dateOfWork=dow;
        height=h;
        width=w;
        medium=med;
        subject=sub;
        suggestedMaximumPurchasePrice=max;

    }

    public Painting()
    {
    }
        //Return: The artist’s first name for that painting record
    public String getArtistsFirstName()
    {
            return artistFirstName;
    }

    //Post: Set artist first name to the string argument
    public void setArtistFirstName(String s)
    {
        artistFirstName=s;
    }
        //Return: The artist’s first name for that painting record
    public String getArtistsLastName()
    {
            return artistLastName;
    }

    //Post: Set artist last name to the string argument
    public void setArtistsLastName(String s)
    {
        artistLastName=s;
    }

    //Return: The date of work for that painting record

    public Date getDateofWork()
    {
        return dateOfWork;
    }

    //Post: Set date of work to the datetime argument
    public void setDateofWork(Date d)
    {
        dateOfWork=d;
    }

        //Return: The title of work for that painting record
    public String getTitleofWork()
    {
           return titleOfWork;
    }

    //Post: The title of work is set to string argument
    public void setTitleofWork(String s)
    {
        titleOfWork=s;
    }

    //Return: The classification for that painting record
    public String getClassification()
    {
            return classification;
    }

    //Post: Set classification to the string argument
    public void setClassification(String s)
    {
        classification=s;
    }
        //Return: The height for that painting record
    public double getHeight()
    {
            return height;
    }

    //Post: Set height to the double argument
    public void setHeight(double d)
    {
        height=d;
    }
        //Return: The width for that painting record
    public double getWidth()
    {
    return width;
    }

    //Post: Set width to the double argument
    public void setWidth(double d)
    {
        width=d;
    }

    //Return: The medium for that painting record
    public String getMedium()
    {
        return medium;
    }

    //Post: Set medium to the string argument
    public void setMedium(String s)
    {
        medium=s;
    }
        //Return: The subject for that painting record
    public String getSubject()
    {
        return subject;
    }

    //Post: Set subject to the string argument
    public void setSubject(String s)
    {
        subject=s;
    }
   /*     //Return: The suggested maximum purchase price for that painting record
    public double getSuggestedMaximumPurchasePrice()
    {
            return suggestedMaximumPurchasePrice;
    }

    //Post: Set suggested maximum purchase price to the double argument
    public void setSuggestedMaximumPurchasePrice(double d)
    {
        suggestedMaximumPurchasePrice=d;
    } */
    public void updateArtistsFirstName()
    {
        System.out.println("Old Artist First Name:" + artistFirstName);
        System.out.println("Please enter new Artist First Name and press <ENTER>: \n");
        artistFirstName=UserInterface.getString();
    }
    public void updateArtistsLastName()
    {
        System.out.println("Old Artist Last Name:" + artistLastName);
        System.out.println("Please enter new Artist Last Name and press <ENTER>: \n");
        artistLastName=UserInterface.getString();
    }
    public void updateTitleOfWork()
    {
        System.out.println("Old Title of Work:" + titleOfWork);
        System.out.println("Please enter new Title of Work and press <ENTER>: \n");
        titleOfWork=UserInterface.getString();
    }
    public void updateClassification()
    {
        System.out.println("Old Classification:" + classification);
        System.out.println("Please enter new Classification and press <ENTER>: \n");
        classification=UserInterface.getString();
    }

    public void updateDateOfWork()
    {
        System.out.println("Old Date of Work:" + dateOfWork);
        System.out.println("Please enter new Date of Work and press <ENTER>: \n");
        Date tempDate=new Date(UserInterface.getString());
        dateOfWork=tempDate;
    }
    public void updateHeight()
    {
        System.out.println("Old Height:" + height);
        System.out.println("Please enter new Height and press <ENTER>: \n");
        double tempheight=new Double(UserInterface.getString());
        height=tempheight;
    }
    public void updateWidth()
    {
        System.out.println("Old Width:" + width);
        System.out.println("Please enter new Width and press <ENTER>: \n");
        double tempwidth=new Double(UserInterface.getString());
        width=tempwidth;
    }
    public void updateMedium()
    {
        System.out.println("Old Medium:" + medium);
        System.out.println("Please enter new Medium and press <ENTER>: \n");
        medium=UserInterface.getString();
    }
    public void updateSubject()
    {
        System.out.println("Old Subject:" + subject);
        System.out.println("Please enter new Subject and press <ENTER>: \n");
        subject=UserInterface.getString();
    }
  /*  public void updateSuggestedMaximumPurchasePrice()
    {
        System.out.println("Old Suggested Max Purchase Price:" + suggestedMaximumPurchasePrice);
        System.out.println("Please enter new Suggested Max Purchase Price and press <ENTER>: \n");
        double tempmax=new Double(UserInterface.getString());
        suggestedMaximumPurchasePrice=tempmax;
    }*/
    
    //delete a painting
     public void delete ()
  {
    try
    {
	char	      c;			    // character entered by user
	String        input1;                        // buffer for line of characters
	String        input2;
        boolean	      done = false;	            // tells when user is done entering information
	boolean       found = false;	            // tells when an investment has been found
	char          choice;           	    // for storing user's response

	while (!found && !done)
	{
	  System.out.println ("Please enter the name of the Artist's last name for the painting to be deleted ");

          input1 = UserInterface.getString();

          System.out.println ("Please enter the Title of Work for the painting to be deleted ");

          input2 = UserInterface.getString();

	  found = find (input1, input2);

	  if (!found)
	  {
	    System.out.println (artistLastName + " and " + titleOfWork
				" was not found.");
            System.out.println ("Would you like to enter another " + getClass ().getName ()+ " number?");

            choice = UserInterface.getChar();

	    if (choice == 'n')
	    {
	      done = true;
	    }
	  }
	}

	if (!found)
	{
          return;
	}

	performDeletion ();
	System.out.println ("\nThe record has been deleted.");
	//UserInterface.pressEnter();
    }
    catch (Exception e)
    {
	System.out.println ("***** Error: Asset.delete () *****");
	System.out.println ("\t" + e);
    }

  }  // delete
  
  
  public void add ()
  //
  // adds a new investment/mortgage.
  //
  {
    try
    {
	int c;	// character entered by user

	obtainNewData(); //not sure if this is the method i want
	save ();
	System.out.println ("\nThe following record was inserted\n");
	print ();
	//UserInterface.pressEnter();

    }
    catch (Exception e)
    {
	System.out.println ("***** Error: Asset.add () *****");
	System.out.println ("\t" + e);
    }

  }  // add
       public void obtainNewData()
  //
  // readInvestmentData obtains input data for all fields of an investment record.
  //
  {
    try
    {
	char	      c;				// character entered by user
	String        input;                      	// buffer for line of characters
	boolean	      valid = false;      		// used to validate length of ID

	while (!valid)
        {
	    System.out.println ("Enter artist last name (12 digits): ");
            artistLastName = UserInterface.getString();
            valid = (artistLastName.length () <= 12);

            if (!valid)
		System.out.println ("\n\nThe investment number must be 12 digits long.");
	 }
         /*
	 System.out.println ("Enter investment name: ");
	 investmentName = UserInterface.getString();

         System.out.println ("Enter expected annual return: ");
	 input = UserInterface.getString();
	 Float newFloat = new Float (input);
	 expectedAnnualReturn = newFloat.floatValue ();

        System.out.println ("Enter today's date (mm/dd/yy):");
        expectedAnnualReturnUpdated = UserInterface.getString(); */

      }
      catch (Exception e)
      {
	System.out.println ("***** Error: Investment.readInvestmentData () *****");
	System.out.println ("\t" + e);
      }

  } 
}
