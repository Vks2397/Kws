package Edverse;

import java.util.concurrent.TimeUnit;

import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class LogIn {
	private static final String By = null;

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		
		System.setProperty("webdriver.chrome.driver", "C:\\Users\\AG\\Downloads\\chromedriver_win32C\\chromedriver.exe");
		
       WebDriver driver = new ChromeDriver();
       
       driver.manage().timeouts().implicitlyWait(20, TimeUnit.SECONDS);
       
       driver.get("https://www.edverse.com/login.html");
       WebElement txtbx_username = driver.findElement(By.name("user_login"));
       
       txtbx_username.sendKeys("Enter email");
       driver.findElement(By.name("login_password")).sendkeys("Enter password");
       driver.findElement(By.id("loginsubmit")).click();
       
       String expected_title = "showing home page";
       String actual_title = driver.getTitle();
       
       if (expected_title.equals(actual_title)) {
    	   System.out.println("Login Successfull");
       }else {
    	   System.out.println("login faild");
       }
       
	}

}
