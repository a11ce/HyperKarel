import java.util.Arrays;


public class HyperKarel {

	private int size;
	private int dimensions;
	public int[] location;
	public int[] direction;


	public HyperKarel(int _size, int _dimensions)
	{


		this.size = _size;
		this.dimensions = _dimensions;
		this.location =  new int[this.dimensions];
		this.direction = new int[this.dimensions];
		this.direction[0] = 1;
	}


	public void turnTo(int[] _direction) throws Error{


		int sum = 0;
		for (int i : _direction)
			sum += i;

		if( !(sum==1 || sum==-1)  || _direction.length != dimensions)
		{
			//System.out.println("Invalid direction");
			throw new Error("Invalid direction.");
		}

		this.direction = _direction;
	}

	public void printInfo()
	{
		System.out.println("Location:  " + Arrays.toString(location));
		System.out.println("Direction: " + Arrays.toString(direction) + "\n");

	}


	public void move(int spaces) throws Exception
	{
		for(int i = 0; i < spaces; i++)
		{
			if(!blocked())
			{
				location = addArrays(location, direction);
			}
		}
	}

	private int[] addArrays(int[] firstToAdd, int[] secondToAdd) throws Error
	{

		if(firstToAdd.length != secondToAdd.length)
		{
			throw new Error("Tried to add arrays of different lengths.");
		}

		for(int i = 0; i < firstToAdd.length; i++)
		{
			firstToAdd[i] += secondToAdd[i];
		}

		return firstToAdd;

	}

	public boolean blocked()
	{
		int moveIndex = 0;
		for(int i = 0; i<dimensions;i++)
		{
			if(direction[i] == 1 || direction[i] == -1)
			{
				moveIndex = i;
			}
		}
		int futureMove = location[moveIndex]+direction[moveIndex];
		if(futureMove>=0 && futureMove<size)
		{
			return false;
		}
		else
		{
			return true;
		}
	}
}
