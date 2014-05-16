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


public abstract boolean find(String alastname, String title);
public abstract void read (RandomAccessFile fileName);
public abstract void print ();
public abstract void save ();
public abstract void write (RandomAccessFile fileName);
public abstract void performDeletion ();
public abstract void readInRecord();

    //Desc: Constructor for Painting class
    public Painting(String first, String last, String title, String clas, Date dow, double h,
            double w, String med, String sub)
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
        

    }
 
    //Desc: No argument constructor for painting class
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
    public String getArtistLastName()
    {
            return artistLastName;
    }

    //Post: Set artist last name to the string argument
    public void setArtistLastName(String s)
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

    //Desc: Prints the current artist first name and allows the user to update the 
    //	artist first name field
    //Post: the artist first name is updated
    public void updateArtistsFirstName()
    {
        System.out.println("Old Artist First Name: " + artistFirstName);
        System.out.println("Please enter new Artist First Name and press <ENTER>: \n");
        artistFirstName=UserInterface.getString();
    }
    
    //Desc: Prints the current artist last name and allows the user to update the 
    //	artist last name field
    //Post: the artist first last is updated
    public void updateArtistsLastName()
    {
        System.out.println("Old Artist Last Name: " + artistLastName);
        System.out.println("Please enter new Artist Last Name and press <ENTER>: \n");
        artistLastName=UserInterface.getString();
    }
    
    //Desc: Prints the current title of work and allows the user to update the 
    //	title of work field
    //Post: the title of work is updated
    public void updateTitleOfWork()
    {
        System.out.println("Old Title of Work: " + titleOfWork);
        System.out.println("Please enter new Title of Work and press <ENTER>: \n");
        titleOfWork=UserInterface.getString();
    }
    
     //Desc: Prints the current classification and allows the user to update the 
    //	classification field
    //Post: the classification is updated
    public void updateClassification()
    {
        System.out.println("Old Classification: " + classification);
        System.out.println("Please enter new Classification and press <ENTER>: \n");
        classification=UserInterface.getString();
    }

    //Desc: Prints the current date of work and allows the user to update the 
    //	date of work field
    //Post: the date of work is updated
    public void updateDateOfWork()
    {
        System.out.println("Old Date of Work: " + dateOfWork);
        System.out.println("Please enter new Date of Work and press <ENTER>: \n");
        Date tempDate=new Date(UserInterface.getString());
        dateOfWork=tempDate;
    }
    
    //Desc: Prints the current height and allows the user to update the 
    //	height field
    //Post: the height is updated
    public void updateHeight()
    {
        System.out.println("Old Height: " + height);
        System.out.println("Please enter new Height and press <ENTER>: \n");
        double tempheight=new Double(UserInterface.getString());
        height=tempheight;
    }

    //Desc: Prints the current width and allows the user to update the 
    //	width field
    //Post: the width is updated
    public void updateWidth()
    {
        System.out.println("Old Width: " + width);
        System.out.println("Please enter new Width and press <ENTER>: \n");
        double tempwidth=new Double(UserInterface.getString());
        width=tempwidth;
    }
    
    //Desc: Prints the current medium and allows the user to update the 
    //	medium field
    //Post: the medium is updated
    public void updateMedium()
    {
        System.out.println("Old Medium: " + medium);
        System.out.println("Enter painting medium (oil, watercolor, or other): ");
        medium  = UserInterface.getString();
        while (!(medium.equalsIgnoreCase("oil")|medium.equalsIgnoreCase("watercolor")|
                medium.equalsIgnoreCase("other")))
        {
            System.out.println("Medium entered incorrectly. Please enter one of the following mediums: oil, watercolor, or other.");
            medium=UserInterface.getString();
        }
    }
    
    //Desc: Prints the current subject and allows the user to update the 
    //	subject field
    //Post: the subject is updated
    public void updateSubject()
    {
        System.out.println("Old Subject: " + subject);
        System.out.println("Enter painting subject (portrait, still-life, landscape, or other): ");
        subject =UserInterface.getString();
        while (!(subject.equalsIgnoreCase("portrait")|subject.equalsIgnoreCase("still-life")|
        subject.equalsIgnoreCase("landscape")| subject.equalsIgnoreCase("other")))
        {
            System.out.println("Subject entered incorrectly. Please enter one of the following subjects: portrait, still-life, landscape, or other.");
            subject=UserInterface.getString();
        }
    }



  //Desc: Deletes a painting
  //Post: a painting record has been deleted
  public void delete ()
  {
        try
        {
            char c;	// character entered by user
            String  input1;        // buffer for line of characters
            String  input2;
            boolean done = false;// tells when user is done entering information
            boolean  found = false;// tells when an investment has been found
            char choice;   // for storing user's response

            while (!found && !done)
            {
                  System.out.println ("Please enter the last name of the artist to be deleted: ");

                  input1 =  UserInterface.getString();

                  System.out.println ("Please enter the title of work to be deleted: ");

                  input2 =  UserInterface.getString();

                  found = find (input1, input2);

                //  System.out.println(found);

                  if (found)
                      done=true;

                //  System.out.println(done);

                  if (!found)
                  {
                    System.out.println ("Either "+input1.toString () + " or " + input2.toString() +
                                        " was not found.");
                    System.out.println ("Would you like to enter another artist lastname and title of work?");

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
	System.out.println("Press <ENTER> to return to menu");
        UserInterface.pressEnter();
        return;
    }
    catch (Exception e)
    {
	System.out.println ("***** Error: Painting.delete () *****");
	System.out.println ("\t" + e);
    }

  }  // delete

  //Desc: adds a new painting
  //Post: a new painting record has been added
 public void add ()

  {
    try
    {
	int c;	// character entered by user

	//obtainNewData ();
       /* updateFashionabilityValue();
        updateArtistLastName();
        updateArtistsFirstName();*/
        readInRecord();
	save ();
	System.out.println ("\nThe following record was inserted\n");
	print ();
	//UserInterface.pressEnter();

    }
    catch (Exception e)
    {
	System.out.println ("***** Error: Painting.add () *****");
	System.out.println ("\t" + e);
    }

  }  // add



}
