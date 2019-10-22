# Performance Testing with JMeter

## Installation

Follow the download instructions found [here](https://jmeter.apache.org/download_jmeter.cgi). You'll be asked to download a zip file and unzip the contents into your application directory. In MAC/OSX this is typically the `Applications` directory. In Windows, it's `Program Files`.

Be advised that the latest verision of JMeter needs have Java 8 installed on the host machine.

Once installed, you'll find the executable in the `./bin` directory. The executable file for MAX/OSX is `jmeter`. For Windows, it's `jmeter.bat`.

(You find detailed instructions for intalling JMeter [here](https://jmeter.apache.org/usermanual/get-started.html#install).)

## Running a Test

**Step 1:** Go to the GitHub respository that contains the `pinger` application and follow the instructions to get the application up and running on Katacoda. You'll find the instructions [here](https://github.com/reselbob/pinger#building-and-running-pinger-as-a-docker-container-on-katacoda).

**Step 2:** Save the public URL that was created when you brought up `pinger` under Katacoda. (The process is discussed in setup instructions described above in **Step 1**.

**Step 3:** Start up JMeter.

MAC/OSX

`sh <JMETER_APP_DIRECTORY>/bin/jmeter.sh`

Windows

`<JMETER_APP_DIRECTORY>/bin/jmeter.bat`

You'll be presented with the UI shown below.

![jmeter 1](./images/jmeter/jmeter-01.png)


**Step 4:** We're going to add a pre-existing preformance test that is saved to a a file, `simple-pinger-test-plan.jmx`.

Click the open file icon on the upper left of the JMeter icon bar as shwown in the figure below.

![jmeter 2](./images/jmeter/jmeter-02.png)

Once you click the icon, an Open dialog appears.

**Step 5:** Navigate your local file system to the location where you cloned the source code for this exercise from GitHub. Select the file,  `simple-pinger-test-plan.jmx` and click the Open button on the lower right of the dialog box.

![jmeter 3](./images/jmeter/jmeter-03.png)

**Step 6:**: You'll see test plan load into the UI as shown in the figure below.

![jmeter 6](./images/jmeter/jmeter-04.png)

**Step 7:** Next need to subsitute the default URL to an aribtrary instance of `pinger` running on Katacoda with the actual URL for the instance you created in **Step 1**.

Click the test plans HTTP Request, named `API Endpoint` as shown on the left side of the figure below. You'll be presented the HTTP Request UI. The value we're going to substitute is the one in the `Server Name or IP` textbox as shown in the illustration below.

![jmeter 7](./images/jmeter/jmeter-05.png)

**Step 8:** Go back to the Katacoda web page were your instance of `pinger` is running. Copy the Katacoda domain name that is particular to your running instance. The figure below shows an example of a domain name to copy.

![jmeter 8](./images/jmeter/jmeter-06.png)

Yours will be different.

**Step 9:** Paste the domain name copied in the previous step into the `Server Name or IP` textbox as shown in the illustration below.

![jmeter 9](./images/jmeter/jmeter-07.png)

**Step 10:** Next we need to as the `csv` file that will contain the query parameters that the performance test will cycle through.

Select right click on thread group, `Microservice Caller` then click, `Add` followed by `Config Element` and then `CSV Data Set Config` as shown in the figure below.

![jmeter 9](./images/jmeter/jmeter-08a.png)

The `CSV Data Set Config` dialog will appear.

**Step 11:** Select the `Browse` button as shown in the figure below.

![jmeter 11](./images/jmeter/jmeter-08b.png)

**Step 12:**

![jmeter 12](./images/jmeter/jmeter-09.png)

**Step 13:**

![jmeter 13](./images/jmeter/jmeter-10.png)

**Step 14:**

![jmeter 14](./images/jmeter/jmeter-11.png)

**Step 15:**

![jmeter 15](./images/jmeter/jmeter-12.png)

**Step 16:**

![jmeter 16](./images/jmeter/jmeter-13.png)

**Step 17:**

![jmeter 17](./images/jmeter/jmeter-14.png)