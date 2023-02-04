# Guru99
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

public class AutoLogin {

  public static void main(String[] args) {
    System.setProperty("webdriver.chrome.driver", "D:\\\\Selenium Drivers\\\\Chrome Driver\\\\chromedriver.exe");
    WebDriver driver = new ChromeDriver();

    // Navigate to the website
    driver.get("https://demo.guru99.com/V4/");

    // Enter the username and password
    driver.findElement(By.name("uid")).sendKeys("username");
    driver.findElement(By.name("password")).sendKeys("password");

    // Submit the login form
    driver.findElement(By.name("btnLogin")).click();

    // Verify that you have successfully logged in
    if (driver.getTitle().equals("Guru99 Bank Manager HomePage")) {
      System.out.println("Login successful");
    } else {
      System.out.println("Login failed");
    }

    // Close the browser
    driver.quit();
  }
}
