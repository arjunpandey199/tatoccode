
	import java.util.ArrayList;

import org.openqa.selenium.*;
	import org.openqa.selenium.firefox.FirefoxDriver;
import org.openqa.selenium.interactions.Actions;
import org.openqa.selenium.support.ui.ExpectedConditions;
import org.openqa.selenium.support.ui.WebDriverWait;
	public class tatoc {

	public static void main(String args[]) {
	System.setProperty("webdriver.gecko.driver", "/home/qainfotech/Downloads/geckodriver");
	WebDriver driver=new FirefoxDriver();
	driver.get("http://10.0.1.86/tatoc");
	driver.findElement(By.cssSelector("A")).click();
	driver.findElement(By.className("greenbox")).click();
	driver.switchTo().frame("main");
	
	WebElement color1=driver.findElement(By.id("answer"));
	String a1=color1.getAttribute("class");
	driver.switchTo().frame("child");
	WebElement color2=driver.findElement(By.id("answer"));
	String a2=color2.getAttribute("class");
	while(a1!=a2)
	{
	driver.switchTo().parentFrame();
	driver.findElement(By.cssSelector("A")).click();
	driver.switchTo().frame("child");
	color2=driver.findElement(By.id("answer"));
	a2=color2.getAttribute("class");
	if(a1.equals(a2))
	break;

	}
	driver.switchTo().parentFrame();
	driver.findElement(By.linkText("Proceed")).click();
	
	
	
	
	
	driver.switchTo().defaultContent();


	WebElement drag = driver.findElement(By.xpath("//*[@id='dragbox']"));
    WebElement drop = driver.findElement(By.xpath("//*[@id='dropbox']"));
    Actions act = new Actions(driver);
    act.dragAndDrop(drag, drop).build().perform();
    driver.findElement(By.linkText("Proceed")).click();
   
    WebDriverWait wait = new  WebDriverWait(driver , 10);
    WebElement obj = wait.until(ExpectedConditions.presenceOfElementLocated(By.cssSelector("body > div > div.page > a:nth-child(4)")));
    obj.click();
  
    
	ArrayList<String> str = new ArrayList<String> (driver.getWindowHandles());
	driver.switchTo().window(str.get(1));
    wait.until(ExpectedConditions.presenceOfElementLocated(By.cssSelector("#name")));
	driver.findElement(By.cssSelector("#name")).sendKeys("Arpit");
	driver.findElement(By.cssSelector("#submit")).click();
	 driver.switchTo().window(str.get(0));
	 driver.findElement(By.linkText("Proceed")).click();
	 
	 
	 
	 driver.findElement(By.linkText("Generate Token")).click();
	 
	 String s=driver.findElement(By.xpath("//*[@id='token']")).getText();
	 String[] tokenValue= s.split("\\s");
	 String token= tokenValue[1];
	  Cookie cookie= new Cookie("Token",token);
	  driver.manage().addCookie(cookie);
	  driver.findElement(By.linkText("Proceed")).click();
	  
	 

	 

	}
	}

