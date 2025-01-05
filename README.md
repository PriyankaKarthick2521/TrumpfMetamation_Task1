# TrumpfMetamation_Task1

class Program
{
    static void Main()
    {
        // Create the folder TrumpfMetamation in C:\
        string folderPath = @"C:\TrumpfMetamation";
        
        // Check if the folder exists, if not, create it
        if (!Directory.Exists(folderPath))
        {
            Directory.CreateDirectory(folderPath);
            Console.WriteLine("Folder created: " + folderPath);
        }

        // Create a text file named Welcome.txt inside the folder
        string filePath = Path.Combine(folderPath, "Welcome.txt");

        // Write "Welcome to Trumpf Metamation!" inside the file
        File.WriteAllText(filePath, "Welcome to Trumpf Metamation!");
        Console.WriteLine("File created and content written: " + filePath);

        // Verify that the file contains the correct content
        string fileContent = File.ReadAllText(filePath);
        if (fileContent == "Welcome to Trumpf Metamation!")
        {
            Console.WriteLine("File contains the correct content.");
        }
        else
        {
            Console.WriteLine("File content is incorrect.");
        }

        // Delete the file
        if (File.Exists(filePath))
        {
            File.Delete(filePath);
            Console.WriteLine("File deleted: " + filePath);
        }

        // Delete the folder
        if (Directory.Exists(folderPath))
        {
            Directory.Delete(folderPath);
            Console.WriteLine("Folder deleted: " + folderPath);
        }

        // Confirm deletion
        if (!File.Exists(filePath) && !Directory.Exists(folderPath))
        {
            Console.WriteLine("File and folder have been deleted successfully.");
        }
        else
        {
            Console.WriteLine("File and/or folder deletion failed.");
        }
    }
}
