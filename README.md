# VCSharp_Example
C# + Nunit

For a single console app
1. install visual studio
2. create a project -> VC# -> console app with .net framework
3. to install selnium, go to VS -> project -> Manage NuGet package -> selenium
4. Install Geckodriver: download it and set PATH, restart VS

example code    

```using System.Linq;
using System.Text;
using System.Threading.Tasks;
using OpenQA.Selenium;
using OpenQA.Selenium.Chrome;
using OpenQA.Selenium.Firefox;

namespace ConsoleApp1
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
            using (IWebDriver wdriver = new FirefoxDriver())
            {
                wdriver.Navigate().GoToUrl("google.com");
                wdriver.Manage().Window.Maximize();
                wdriver.FindElement(By.Id("xxxxxx")).Click();

               // Assert.AreEqual(wdriver.Url, "google");
                wdriver.Quit();
            }
            // Keep the console window open in debug mode.
           // Console.WriteLine("Press any key to exit.");
           // Console.ReadKey();
        }
    }
}
