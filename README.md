# Tendablecode

package new_automation_testcases;



import org.openqa.selenium.By;
//import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.Keys;

import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebDriver.Timeouts;
import org.openqa.selenium.WebDriverException;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.interactions.Actions;
import org.openqa.selenium.support.ui.ExpectedConditions;
import org.openqa.selenium.support.ui.Select;
import org.openqa.selenium.support.ui.WebDriverWait;
//import org.openqa.selenium.support.ui.WebDriverWait;
import org.testng.annotations.AfterTest;
import org.testng.annotations.BeforeTest;
import org.testng.annotations.Test;


import org.testng.Assert;
import java.util.concurrent.TimeUnit;



public class TestTendable {

	
		// TODO Auto-generated method stub
	 WebDriver driver;

	 @BeforeTest
	
	    public void setUp() {
	        // Set the path of the chromedriver executable
	    	System.setProperty("WebDriver.Chrome.driver", "C:\\Users\\hp\\Downloads\\chromedriver_win32");
	    	 driver = new ChromeDriver();
	        // Navigate to the Tendable website
	        driver.get("https://www.tendable.com");
	        driver.manage().window().maximize();
	        
	        } 
	        
	
        // Locate the top-level menu elements by their link text
    
       
        
	
      @Test 
	        public void TestMenuAccessibility() {
	       
    	  WebElement storyMenu = driver.findElement(By.linkText("Our Story"));
    	  Assert.assertTrue(storyMenu.isEnabled(), "Login button is not enabled");
          Assert.assertTrue(storyMenu.isDisplayed(), "Login button is not displayed");
    	  
    	   //storyMenu.click();
    	     
	        WebElement solutionMenu = driver.findElement(By.linkText("Our Solution"));
	        Assert.assertTrue(solutionMenu.isEnabled(), "Login button is not enabled");
	          Assert.assertTrue(solutionMenu.isDisplayed(), "Login button is not displayed");
	         
	        
	        
	       // solutionMenu.click();
	        
	        WebElement whyMenu = driver.findElement(By.linkText("Why Tendable?"));
	        Assert.assertTrue(whyMenu .isEnabled(), "Login button is not enabled");
	          Assert.assertTrue(whyMenu .isDisplayed(), "Login button is not displayed");}
	        
	        //whyMenu.click();
      @Test
	    public void testRequestDemoButton() {	  
	        	 
	     // Locate the top-level menu elements by their link text
	    	WebElement RequestDemo = driver.findElement(By.linkText("Request a Demo"));
	    	 

		        //Click on each top-level menu and verify that the Request a Demo button is present and active
		       
		    
			       // Call the isDisplayed method and store the result in a variable
			        boolean isElementVisible = RequestDemo.isDisplayed();

			        // Verify the expected value with the actual value using Assert class
			        Assert.assertTrue(isElementVisible, "The element is not visible");
			        
			        RequestDemo.click();
	   
	        // Locate the top-level menu elements by their link text
			        WebElement storyMenuu = driver.findElement(By.linkText("Our Story"));
			        storyMenuu.click();
			     
		       WebElement storyMenue = driver.findElement(By.linkText("Our Story"));
		       storyMenue.click();
		     
		       
		       
		        WebElement solutionMenue = driver.findElement(By.linkText("Our Solution"));
		        solutionMenue.click();
		        
		        WebElement whyMenu = driver.findElement(By.linkText("Why Tendable?"));
		        whyMenu.click();   
		        
		        WebElement aboutUs = driver.findElement(By.linkText("About Us"));
		        aboutUs.click();
     
			        WebElement contactUs = driver.findElement(By.linkText("Contact Us"));
			    	contactUs.click();
			    	
			    	WebElement contactUsSection = driver.findElement(By.xpath("//button[@class='body-button bg-plain-600 toggle-control']")); 
			        contactUsSection.click();
			        WebElement nameField = driver.findElement(By.xpath("//input[@name='fullName']"));
			        nameField.sendKeys("John Doe");
			        WebElement organisation = driver.findElement(By.xpath("//input[@name='organisationName']")); 
			        organisation.sendKeys("johndoe@example.com");
			        WebElement phoneField = driver.findElement(By.xpath("//input[@name='cellPhone']"));  
			        phoneField.sendKeys("1234567890");
			        
			        WebElement emailField = driver.findElement(By.xpath("//input[@name='email']")); 
			        emailField.sendKeys("johndoe@example.com");
			    
			        
			        WebElement jobrole = driver.findElement(By.xpath("//select[@id='form-input-jobRole']"));
			       
			        Select a = new Select(jobrole);
			        a.selectByValue("Job Role");
			        
			        Actions aa = new Actions(driver);
			      //scroll down a page
			      aa.sendKeys(Keys.PAGE_DOWN).build().perform();
			    // Timeouts implicitlyWait =  driver.manage().timeouts().implicitlyWait(5, TimeUnit.SECONDS);
			      
			     //WebElement submitButton = driver.findElement(By.xpath("//button[@name='form_page_submit']"));
		
			      
			     WebElement submitButton = driver.findElement(By.cssSelector("input[type='submit']"));
				     submitButton.click();
			     
			        //aa.sendKeys(Keys.PAGE_UP).build().perform();
			       
			        
			      //expected error text
			        String exp = "Sorry, there was an error submitting the form. Please try again.";
			        //identify actual error message
			        WebElement errormessage = driver.findElement(By.className("ff-form-errors"));
			        String act = errormessage.getText();
			        System.out.println("Error message is: "+ act);
			        //verify error message with Assertion
			        Assert.assertEquals(exp, act);

		     
      }
	    @AfterTest
	    public void tearDown() {
	        // Close the browser
	       driver.quit();
	    }
      }       
	    


