Painting.java
=============
/*
 * To change this template, choose Tools | Templates
 * and open the template in the editor.
 */

package oglesbyimplementation;

abstract class Painting
{

	private String artistFirstName;
	private String artistLastName;
	private String titleOfWork;
	private String classification;
	//private date dateOfWork;
	private double height;
	private double width;
	private String medium;
	private String subject;
	private double suggestedMaximumPurchasePrice;

	public Painting(String first, String last, String title, String clas, double h, double w, String med, String sub, double max )
	{
		artistFirstName=first;
		artistLastName=last;
		titleOfWork=title;
		classification=clas;
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
   /*     //Return: The date of work for that painting record
    public date getDateofWork()
    {
			return dateOfWork
    }

    //Post: Set date of work to the datetime argument
    public void setDateofWork(date d)
    {
    	dateOfWork=s
    }*/
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
        //Return: The suggested maximum purchase price for that painting record
    public double getSuggestedMaximumPurchasePrice()
    {
			return suggestedMaximumPurchasePrice;
    }

    //Post: Set suggested maximum purchase price to the double argument
    public void setSuggestedMaximumPurchasePrice(double d)
    {
    	suggestedMaximumPurchasePrice=d;
    }
    public void updateArtistsFirstName()
    {
        String str="";
        System.out.println("Old Artist First Name:" + artistFirstName);
        System.out.println("Please enter new Artist First Name and press <ENTER>: \n");
       // UserInterface.getString()
    }
    public void updateArtistsLastName()
    {
        String str="";
        System.out.println("Old Artist First Name:" + artistLastName);
        System.out.println("Please enter new Artist First Name and press <ENTER>: \n");
    }
    public void updateTitleOfWork()
    {
        String str="";
        System.out.println("Old Artist First Name:" + titleOfWork);
        System.out.println("Please enter new Artist First Name and press <ENTER>: \n");
    }
    public void updateClassification()
    {
        String str="";
        System.out.println("Old Artist First Name:" + classification);
        System.out.println("Please enter new Artist First Name and press <ENTER>: \n");
    }
    public void updatHeight()
    {
        String str="";
        System.out.println("Old Artist First Name:" + height);
        System.out.println("Please enter new Artist First Name and press <ENTER>: \n");
    }
    public void updateWidth()
    {
        String str="";
        System.out.println("Old Artist First Name:" + width);
        System.out.println("Please enter new Artist First Name and press <ENTER>: \n");
    }
    public void updateMedium()
    {
        String str="";
        System.out.println("Old Artist First Name:" + Medium);
        System.out.println("Please enter new Artist First Name and press <ENTER>: \n");
    }
    public void updateSubject()
    {
        String str="";
        System.out.println("Old Artist First Name:" + subject);
        System.out.println("Please enter new Artist First Name and press <ENTER>: \n");
    }
    public void updateSuggestedMaximumPurchasePrice()
    {
        String str="";
        System.out.println("Old Artist First Name:" + suggestedMaximumPurchasePrice);
        System.out.println("Please enter new Artist First Name and press <ENTER>: \n");
    }

    public abstract boolean find(String alastname, String title);
    public abstract void read (RandomAccessFile fileName);
    public abstract void print ();
    public abstract void save ();
    public abstract void write (RandomAccessFile fileName);
    public abstract void performDeletion ();

    public static void main(String[] args)
    {
    }
}
