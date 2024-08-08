//# Is_Selected

package UI_Verificationcommands;

import java.time.Duration;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class isDesplayed_Staticelement {

	public static void main(String[] args) throws Exception 
	{
		
		WebDriver driver=new ChromeDriver();
		driver.get("https://www.irctc.co.in/nget/train-search");
		driver.manage().window().maximize();
		driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(300));
		
		WebElement Login_btn=driver.findElement(By.xpath("//a[@aria-label='Click here to Login in application']"));
		if(Login_btn.isDisplayed())
			Login_btn.click();
		else
			System.out.println("Element Not visible at webpage");
		
		Thread.sleep(300);
		
		WebElement User_Name=driver.findElement(By.xpath("//input[contains(@placeholder,'User Name')]"));
		if (User_Name.isDisplayed()&& User_Name.isEnabled()) 
		{
			User_Name.clear();
			User_Name.sendKeys("sreelekhakaytham");
				
		} 
		else
		{
			System.out.println("Username is not visible");
			
		}
		Thread.sleep(300);
		WebElement Password=driver.findElement(By.xpath("//input[@type='password']"));
		if (Password.isDisplayed()&& Password.isEnabled()) 
		{
			Password.clear();
			Password.sendKeys("Ammanana@123");
			
		} 
		else 
		{
			System.out.println("Password is not visible");
		}
		Thread.sleep(300);
		WebElement Captcha=driver.findElement(By.xpath("//input[contains(@name,'captcha')]"));
		if (Captcha.isDisplayed()&& Captcha.isEnabled())
		{
			Captcha.clear();
			Captcha.sendKeys("e3QaQ");
			
		} else 
		{
			System.out.println("Captcha is not visible");
			
		}
		Thread.sleep(300);
		driver.findElement(By.xpath("(//label[@class='css-label_c t_c'])[5]")).click();
		
		Thread.sleep(300);
		driver.findElement(By.xpath("//button[@type='submit'][contains(.,'Cancel')]")).click();
		Thread.sleep(300);
		WebElement Search=driver.findElement(By.xpath("(//button[contains(@type,'submit')])[2]"));
		boolean flag=Search.isSelected();
		System.out.println("Search is selected" +flag);
		Search.click();
		
		
		
	}

}
