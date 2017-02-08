
import java.io.File;

public class ListFilesl 
{
    /** List all the files and folders from a directory */
    public void ListFAndF(String DirectoryName)
    {
        File directory = new File(DirectoryName);
        File[] fileList = directory.listFiles();
        for (File file : fileList)
        {
            System.out.println(file.getName());
        }
    }
    /** List all the folder under a directory */
    public void listFolders(String DirectoryName)
    {
        File directory = new File(DirectoryName);
        File[] fList = directory.listFiles();
        for (File file : fList)
        {
            if (file.isDirectory())
            {
                System.out.println(file.getName());
            }
        }
    }
    /** List all the files under a directory */
    public void listFiles(String DirectoryName)
    {
        File directory = new File(DirectoryName);
        File[] fileList = directory.listFiles();
        for (File file : fileList){
            if (file.isFile()){
                System.out.println(file.getName());
            }
        }
    }
    /** List files from a directory and its sub-directories*/
    public void listFAndFSubDirectories(String DirectoryName){
        File directory = new File(DirectoryName);
        File[] fileList = directory.listFiles();
        for (File file : fileList){
            if (file.isFile())
            {
                System.out.println(file.getAbsolutePath());
            } 
            else if (file.isDirectory())
            {
            	listFAndFSubDirectories(file.getAbsolutePath());
            }
        }
    }
    public static void main (String[] args)
    {
        ListFiles l = new ListFiles();
        String WinDirectory= "C://Program Files";
        l.ListFAndF(WinDirectory);
        l.listFolders(WinDirectory);
        l.listFiles(WinDirectory);
        l.listFAndFSubDirectories(WinDirectory);
        
    }
}
