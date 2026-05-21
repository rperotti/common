C:\Users\rick perotti\Documents\GitHub\common\sample-livelabs-templates\sample-workshop\riti_first_lab
http://127.0.0.1:5500/sample-workshop/workshops/desktop/index.html?lab=riti_first_lab

# Explore a Workflow Agent in AI Agent Studio

## Introduction

### About AI Agent Workflows

Workflows are a predetermined set of tasks, which can be represented as a connected sequence of nodes. Each node performs a defined function, for example, extracting data, calling a business object, running an LLM, or sending an email. The node then passes its output to the next step. For business processes that require a strict order of execution, you can embed the required AI agents within the workflow.

Estimated Time: 30 minutes

### Objectives

Learn about workflow agents and execute one of the pre-built workflow agents.  Below are node types available in AI Agent Studio that are used to build workflow agents.

![Image sizing applied](images/Nodes.png =100%x*)

By the end of this lab, participants will:
* Have a high-level understanding of how workflow agents are built.
* Have a quick peak into different types of nodes available to build workflow agents.
* Execute a pre-built workflow agent with human approval by uploading document in chat interface.

*This is the "fold" - below items are collapsed by default*

## Task 1: Locate and copy the pre-existing Quote to Purchase Requisition Chat Assistant template

1. Step 1

Login to the lab environment using the credentials provided.

 Navigate to **Tools** -> **AI Agent Studio**

![Image sizing applied](images/LoggedIn.png =100%x*)

1. Step 2

You will land on the **AI Agent Studio tab**. This tab displays all of the Prebuilt Templates. You can quickly configure, deploy,
and extend Oracle-delivered agents using this catalog of pre-built templates and a guided assembly process.

![Image sizing applied](images/LandingPage.png =60%x*)

1. Step 3

Search for **Chat Assistant** in the search box:

![Image sizing applied](images/FindTemplet.png =60%x*)

Click on **Copy Template** for the **Quote to Purchase Requisition Chat Assistant**.
If you do not see Copy Template, click on the 3 dots in the bottom right corner of the Quote to Purchase Requisition Chat Assistant box.

1. Step 4 In the Agent Team Suffix box, enter **YOUR INITIAL CODE**.

![Image alt text](images/warning.png =30%x*)

Click on the **Continue** button.
If you get a message that a component with that name already exists, make sure you are using a unique code. Add a number if required.

![Image alt text](images/AddYourInitials.png =60%x*)

1. Step 5 Next you will save your agent team copy and ensure that you can locate it.

Click the **Save and Close** button in the top right of the screen:

![Image alt text](images/SaveAndClose.png =60%x*)

1. Step 6 On the tab bar on the bottom of the screen, Click on **Agent Teams**:

![Image alt text](images/SaveAndCloseDone.png =60%x*)

1. 7 Enter **YOUR INITIAL CODE** in the search box and hit **ENTER**:

![Image alt text](images/DraftMode2.png =60%x*)

1. 9 Select the **DRAFT** button (your agent team will be in draft status). You should see your newly-created agent team:

![Image alt text](images/StatusCheckPoint.png =50%x*)

## Task 2: Examine the pre-built Quote to Purchase Requisition Chat Assistant template components

2. Step 1 Open up the Agent Team

Go to **Agent Teams** tab and search for Quote to Purchase Requisition Chat Assistant **Your Initials**.
Click on **Pencil** icon to go in edit mode to review this agent.

![Image alt text](images/DraftMode2.png =50%x*)

2. Step 2 Open the configuration dialog

Click on **Settings** that shows panel with details, LLM, security and other configurations added for this agent.
Review below tabs. When done, click **Cancel** so that no accidental changes are saved.

- **LLM**: This Agent Team has the default LLM set.
- **Chat Experience**: It has enabled Enable File Upload in Chat Experience so that documents can be uploaded.
- **Variables**: It has one variable defined.

![Image alt text](images/DetailsDialog.png =50%x*)

2. Step 3 Examine a node

Now let’s review one of the nodes of this agent. Open the **Get User Session Information** node to review its setup.

![Image alt text](images/EditSessionButton.png =50%x*)

Note that function **getUserSession** under business object **Self Detail** is set to be used in this node.
Optionally, you can navigate to the **Business Object** tab at the bottom of the page and query up this Business Object to see it’s setup in more detail.

![Image alt text](images/GetUserSessionDetail.png =50%x*)

2. Step 4 Continue to examine a node

Scroll further down the page and note that the JSON specification has been entered. The results of the business object will 
be returned in this format, and the use of the JSON specification means that the attributes can be referred to directly in 
subsequent nodes.

![Image alt text](images/GetUserSessionMoreDetail.png =50%x*)

2. Step 5  Examine Other Nodes

Feel free to review other types of nodes in this workflow When done, proceed to the next step where we will be running this agent and seeing it in action.

## Task 3: See the agent in action

3. Step 1 Prepare the purchase order for use.

For this exercise, we will be cutting and pasting from our lab guide and creating a text file for the purchase order.

Cut and paste this section into NotePad or another text editor.  Change the **ZZZZZ** with your initials.

    <copy>
    18790 Grainger Place
    Seattle, WA 98052
    123.123.1234
    QUOTE
    Bill To:
    Hope Johnson
    Supremo Corporation
    888 Cloud Way
    San Francisco, CA 94114
    Qty Description Unit Price (USD) Amount
    1.00 Each Replacement of fabrication machinery belt 565.00 565.00
    3.00 Hour Labor 80.00 240.00
    Subtotal 805.00
    Tax 64.40
    Total 869.40
    Quote #: ZZZZZZ_QUOTE_2609127
    Quote Date: June 1, 2026
    Due Date: Sep 15, 2026
    Terms and Conditions
    1. Delivery will be made within 7 days following Advanced Corporation’s receipt of payment.
    2. Delivery will be made f.o.b. Advanced Corporation’s facility.
    3. Advanced Corporation’s general terms and conditions of purchase apply to this quotation.
    4. This quotation may be accepted to form a binding contract upon any one of the following options:
    a. Signature below and payment to Advanced Corporation for the items in this quote prior to the
    expiration date.
    b. Issuance of a purchase order to Advanced Corporation referencing this quote and the terms and
    conditions herein prior to the expiration date above
    </copy>

When you have updated the text file save and close it.

![Image alt text](images/Textpad.png =50%x*)

3. Step 2. Run the agent with your quotation file. If the browser session has timed out, re-login and search for your agent in **Agent Teams**.

![Image alt text](images/RunTheAgent.png =50%x*)

3. Step 3. Upload the file

Type query **Create Requisition** as the text message.
Click on This Device and select your text file you created in the previous step.

When both text message and file are entered, click **“Up”** button to start processing

![Image alt text](images/ReadyToRun.png =40%x*)

 When the processing reaches the Human Approval node it will pause awaiting input. Click on the **Approve** button.

![Image alt text](images/RunningTheAgent.png =50%x*)

When the flow is successfully complete, a link will be provided to access the new Requisition in Fusion.

![Image alt text](images/ApprovedRun.png =50%x*)

3. Step 4.  Examine the created Requisition

 Right click on the hyperlink to open up the requisition in a new window.
 Review the requisition details to ensure they match your quotation document.

 ![Image alt text](images/RecInFusion.png =80%x*)

This completes all tasks assigned to you for this lab.

## Summary

You should now have a introductory understanding provided by the pre-built Quote to Purchase Requisition Chat Assistant agent template.


## Learn More

* [Oracle Introduces AI Agent Studio](https://www.oracle.com/news/announcement/oracle-introduces-ai-agent-studio-2025-03-20/)
* [Learning Path for Fusion AI Agent Studio](https://blogs.oracle.com/fusioncoe/fusion-ai-agent-studio-learning-path)

## Acknowledgements
- **Author** - Rick Perotti, Platform Specialist, Office of Technology & Innovation
* **Last Updated By/Date** - Rick Perotti, May 2026
