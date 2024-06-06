# Lab 04 - Creating a DLP policy and generating an alert in Microsoft
Purview

### Introduction

Microsoft Copilot for Security is a cloud-based AI platform that can
assist you in identifying, summarizing, triaging, and remediating alerts
and events in Microsoft Purview for:

- Microsoft Purview Data Loss Prevention (DLP)

- Microsoft Purview Insider Risk Management

- Microsoft Purview Communication Compliance

- Microsoft Purview eDiscovery

It also supports security and compliance professionals in different
scenarios, such as alert and incident response, threat hunting, and
intelligence gathering. For more information about what it can do

### Objectives

- To create a Microsoft Purview account.

- To create custom Data Loss Prevention (DLP) policies for Microsoft
  Copilot for Security.

- To test the effectiveness of the DLP policy by sending simulated
  credit card information to a specific user in Microsoft Teams,
  observing flagged messages, and checking alerts in the Purview portal.

### Task 1: Creating Microsoft Purview Account

1.  In Microsoft Azure portal search bar, type +++**Microsoft Purview
    accounts**+++, then navigate and click on **Microsoft Purview
    accounts** under **Services**.

<img src="./media/image1.png" style="width:6.5in;height:4.16875in" />

2.  In the **Microsoft Purview accounts** page, click on **+ Create**.

> <img src="./media/image2.png" style="width:6.5in;height:4.16875in"
> alt="A screenshot of a computer Description automatically generated" />

3.  In the **Create Microsoft Purview account** page, enter the
    following details and click on **Review + Create** button.

| Subscription | Azure Pass |
|----|----|
| Resource group | **MCS-RG** |
| Microsoft Purview account name | Enter the name of your choice (here, we entered **securitycopilot2**) |
| Location | **EastUS** |

> <img src="./media/image3.png" style="width:6.5in;height:4.16806in"
> alt="A screenshot of a computer Description automatically generated" />

4.  Open a new tab in the Edge browser address bar and enter the
    following URL: +++<https://purview.microsoft.com/>+++. If prompted,
    then sign in with your O365 tenant credentials. Close **Welcome to
    the new Microsoft Purview portal!** dialog box.

> <img src="./media/image4.png" style="width:5.93704in;height:4.75026in"
> alt="A screenshot of a computer Description automatically generated" />

5.  Click on the **Switch** button beside Microsoft 365 compliance
    portal.

> <img src="./media/image5.png" style="width:6.5in;height:4.16875in" />

6.  You’ll be directed to Microsoft Purview portal.

> <img src="./media/image6.png" style="width:6.5in;height:4.16875in"
> alt="A screenshot of a computer Description automatically generated" />

### Task 2: Setting Custom DLP policies for Microsoft Copilot for Security

1.  In the **Microsoft Purview** portal, navigate to **Solutions**, then
    click on **Data loss prevention** as shown in the below image.
    <img src="./media/image7.png" style="width:6.5in;height:4.16875in" />

2.  Click on **Policies**. In the **Policies** page, navigate and click
    on **+Create policy**.

<img src="./media/image8.png" style="width:6.225in;height:3.76667in"
alt="A screenshot of a computer Description automatically generated" />

3.  In **Template or custom policy** pane, under **Categories**,
    navigate and click on **Custom**. Under **Regulations**, click on
    **Custom policy**. Then, click on the **Next** button.

<img src="./media/image9.png" style="width:6.5in;height:4.16875in" />

4.  On **Name your DLP policy** pane, in the **Name** field, enter the
    following name:

+++**Custom Policy for Microsoft Security Copilot**+++, then click on
the **Next** button.

<img src="./media/image10.png" style="width:6.5in;height:4.16875in" />

5.  Leave the **Assign admin units** pane in the default state and click
    on the **Next** button.

<img src="./media/image11.png" style="width:6.5in;height:4.16875in"
alt="A screenshot of a computer Description automatically generated" />

6.  On **Choose where to apply the policy** pane, select the check boxes
    of **Exchange email, Sharepoint sites, OneDrive accounts, Team chat
    and channel messages**, and **Devices**, then click on the **Next**
    button.

> <img src="./media/image12.png" style="width:6.5in;height:4.16875in"
> alt="A screenshot of a computer Description automatically generated" />

7.  On **Define policy settings** pane, select the radio button of
    **Create or customize advanced DLP rules** and click on the **Next**
    button.

<img src="./media/image13.png" style="width:6.5in;height:4.16875in"
alt="A screenshot of a computer Description automatically generated" />

8.  On **Customized advanced DLP rules** pane, click on **+ Create
    rule**.<img src="./media/image14.png" style="width:6.5in;height:4.16875in" />

9.  On the **Create rule** page, in the **Name** field, enter
    **Sensitive Information of Credit Card**.

<img src="./media/image15.png" style="width:6.5in;height:4.16875in" />

10. Scroll down to **Conditions** section and click on **+Add
    condition**, then select **Content contains** as shown in the below
    image.

<img src="./media/image16.png" style="width:6.5in;height:2.08958in" />
11. In the **Content contains** section, leave **Group name** and
**Group operator** in default state, click on the dropdown beside
**Add** and select **Sensitive info types** as shown in the below image.

<img src="./media/image17.png" style="width:6.5in;height:2.04375in" />

12\. In the **Sensitive info types** pane that appear on the right side,
type +++**credit card number**+++ in the search bar. Select **Credit
Card Number** check box, then click on the **Add** button.

<img src="./media/image18.png" style="width:6.5in;height:4.16875in" />

<img src="./media/image19.png" style="width:6.5in;height:4.16875in"
alt="A screenshot of a computer Description automatically generated" />

13. Scroll down to **User notifications** section and Turn **On** the
    toggle button.

<img src="./media/image20.png" style="width:6.5in;height:4.16875in" />

14. Scroll down to **Incident reports** section, select the severity
    level of the alerts and reports as **High**.

<img src="./media/image21.png" style="width:6.5in;height:4.16875in" />

15. Leave all the parameters in the default state and click on the
    **Save** button.

<img src="./media/image22.png" style="width:6.5in;height:4.16875in" />

16. Click on the **Next** button.

<img src="./media/image23.png" style="width:6.5in;height:4.1625in" />

17. In the **Policy mode** pane, select the radio button of **Turn the
    policy on immediately** and click on the **Next** button.

<img src="./media/image24.png" style="width:6.5in;height:4.1625in" />

18. On **Review and finish** pane, carefully review the DLP policy, then
    click on the **Submit** button.

<img src="./media/image25.png" style="width:6.5in;height:4.1625in"
alt="A screenshot of a computer Description automatically generated" />

19. The New policy will be created, click on the **Done** button.

<img src="./media/image26.png" style="width:6.5in;height:4.1625in" />

<img src="./media/image27.png" style="width:6.5in;height:4.1625in" />

### Task 3: Creating an alert in Microsoft Teams

1.  Click on the horizontal dots beside **Microsoft Purview**, then
    navigate and click on **Teams** as shown in the below image.

> <img src="./media/image28.png" style="width:6.5in;height:5.82222in" />

2.  In Microsoft Teams search bar, search and select the name of user -
    **Robert Frost**.

> <img src="./media/image29.png"
> style="width:6.00121in;height:3.84308in" />

3.  Test the DLP policy that you have created using the following
    **Credit Card Type** and **Credit Card Number**. Select the name of
    the Credit Card along with the number and send that information in
    team to Robert Frost.

| **Credit Card Type**   | **Credit Card Number** |
|------------------------|------------------------|
| +++American Express+++ | +++378282246310005+++  |
| +++JCB+++              | +++3566002020360505+++ |
| +++MasterCard+++       | +++5105105105105100+++ |
| Visa                   | 4012888888881881       |

> You’ll observe that your message was flagged every time.
>
> <img src="./media/image30.png" style="width:6.5in;height:3.96597in" />

4.  In the **Data Loss Prevention** section, navigate and click on
    **Alerts**, you’ll see the Alerts stating – **DLP policy match for
    Teams conversation** along with the **Severity** and **Status** of
    the alerts.

> <img src="./media/image31.png" style="width:6.5in;height:4.1625in" />
>
> **Note**: You’ll analyze the alerts generated through the Custom DLP
> policy using Microsoft Copilot for Security in the upcoming task. As
> the SCU consume a lot of credits; therefore, to prevent unnecessary
> credit loss, we’ve moved this task in the next lab.

**Summary**

In this lab, you’ve set up a Microsoft Purview account, then you’ve
configured custom Data Loss Prevention (DLP) policies for Microsoft
Copilot for Security, and created alerts in Microsoft Teams to test the
effectiveness of these policies. This hands-on exercise has equipped you
with valuable skills in data protection and compliance management within
Microsoft's ecosystem, enhancing your understanding of security measures
in cloud-based environments.

