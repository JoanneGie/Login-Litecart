# Login-Litecart

using OpenQA.Selenium;
using OpenQA.Selenium.Chrome;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace selenium
{
    class Program
    {
        static void Main(string[] args)
        {
            IWebDriver driver = new ChromeDriver();
            driver.Manage().Timeouts().ImplicitWait = TimeSpan.FromSeconds(10);

            driver.Url = "http://localhost/litecart/admin/login.php";

            var userName = driver.FindElement(By.Name("username"));
            userName.Click();
            userName.SendKeys("admin");

            var password = driver.FindElement(By.Name("password"));
            password.SendKeys("admin");

            driver.FindElement(By.Name("login")).Click();

            driver.Close();


        }
    }
}
