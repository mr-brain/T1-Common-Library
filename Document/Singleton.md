Singleton
===

Ensure a class has only one instance and provide a global point of access to it.

Structural code in C#

	using T1.Common;

	public class YourClass
	{
		public static YourClass Instance
		{
			get
			{
				return Singleton.Instance<YourClass>();
			}
		}
		public void Test(){}
	}
	

You can use above code in C#

	YourClass.Instance.Test();

If your class contractor need input parameters, you can

	public class YourClass
	{
		public static YourClass Instance
		{
			get
			{
				return Singleton.Instance<YourClass>(()=>{
					var c = new YourClass("name");
					return c;
				});
			}
		}

		string _name;
		private YourClass(string name)
		{	
			_name = name;
		}
		public void Test(){}
	}