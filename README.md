# Selenium-testng
Testng code for facebook testing

package testNGpack;

import org.testng.annotations.Test;
import org.testng.annotations.BeforeMethod;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.testng.Assert;
import org.testng.annotations.AfterMethod;
import org.testng.annotations.BeforeTest;
import org.testng.annotations.AfterTest;

public class testNGclass {
	public String baseUrl = "https://www.facebook.com/";
	WebDriver driver;
	public String expected = null;
    public String actual = null;


    @BeforeTest
    public void beforeTest() {
  	  System.out.println("launching Facebook");
  	  System.setProperty("webdriver.chrome.driver","C:\\chromedriver.exe");
  	   driver=new ChromeDriver();
  		driver.get(baseUrl);
    }

  @Test
  public void f() throws InterruptedException {
      driver.findElement(By.id("email")).sendKeys("yourusername@gmail.com");
      driver.findElement(By.id("pass")).sendKeys("password");
      Thread.sleep(5000);


  }


  @AfterTest
  public void afterTest() {
	  driver.close();

  }
