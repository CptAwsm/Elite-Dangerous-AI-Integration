# Getting Started

Welcome to the setup guide for COVAS:NEXT! Follow the steps below to get up and running. If you encounter any issues along the way, check the **Common Issues** section under each step and join the [Discord server](https://discord.gg/9c58jxVuAT) for additional support.

## Important Notes Before You Begin

- **Costs:** The application uses the OpenAI API, which costs money based on usage. Typical usage costs are **around $0.10 per hour**, depending on your playstyle. Alternatives are available, but they will significantly degrade your experience and are not recommended.

- **Microphone:** You will need a working microphone to interact with the AI and preferably a headset to prevent the AI from hearing itself.

- **Antivirus Software:** Some antivirus software may flag the application as a virus due to **a false positive**. This can be very annoying and you may need to add an exception in your antivirus software or disable it, if you encounter this issue.

Also, please check our [FAQ](./10_faq.md) for additional information.

---

## Step 1: Download the Application

[:fontawesome-solid-download: Download from GitHub](https://github.com/RatherRude/Elite-Dangerous-AI-Integration/releases/latest){ .md-button .md-button--primary }

1. Download the zip file containing the application.
2. Once downloaded, locate the zip file on your computer.

??? note "Common Issues"

    - **Problem:** A virus was detected during the download.

        **Solution:** Some antivirus software may flag the application as a virus due to a false positive. The application is safe to use.
        Try downloading it again. If the issue persists, you may need to add an exception in your antivirus software or disable it temporarily while downloading.

---

## Step 2: Extract the Zip File

1. Right-click on the downloaded zip file and choose "Extract All..." or similar based on your operating system.
2. Choose a folder for extraction and ensure all files are successfully extracted.

??? note "Common Issues"

    - **Problem:** A virus was detected during extraction.
    
        **Solution:** Some antivirus software may detect the application as a virus. This is a false positive.  
        Add an exception for the application in your antivirus software or disable it temporarily while extracting.

---

## Step 3: Start the Application

1. Open the extracted folder.
2. Double-click on the "start" file to launch the application. This should open the configuration UI.

??? note "Common Issues"

    - **Problem:** I don't know how to start the application.
    
        **Solution:** Open the extracted folder and double-click on the "start" file.

    - **Problem:** A virus was detected.
    
        **Solution:** Add an exception for the application in your antivirus software or disable it temporarily.

    - **Problem:** An error message about "chat.exe" or "chat.py" appears.

        **Solution:** Re-extract the zip file and add an exception in your antivirus software to prevent files from being quarantined.

    - **Problem:** The window closes immediately.
    
        **Solution:** Contact support. This may be an application issue requiring developer intervention.

    - **Problem:** An error message appears on startup.
    
        **Solution:** Contact support with details from the error message.


---

## Step 4: Obtain an OpenAI API Key

OpenAI likes changing their API key system, so documentation may be out of date. At the time of writing, you can get an API key using the following links:

1. Navigate to [platform.openai.com](https://platform.openai.com/) and sign up for an account.

2. Create an API key at [platform.openai.com/api-keys](https://platform.openai.com/api-keys). 

3. You may need to charge your account with some money before you can use the API key.

??? note "Common Issues"

    - **Problem:** I don't want to pay for an API key.
    
        **Solution:** None, unless you know exactly what you're doing and can set up a local models. This is not recommended and will significantly degrade your experience.
    
    - **Problem:** I already have a ChatGPT subscription.

        **Solution:** ChatGPT and the OpenAI API are separate services. You cannot use a ChatGPT Subscription for COVAS:NEXT. You will need to sign up for an OpenAI account and generate an API key via [platform.openai.com](https://platform.openai.com/).

---

## Step 5: Configure Your Profile

1. In the configuration UI, enter your commander name.
2. Next, enter your OpenAI API key.
3. We recommend using Push-to-Talk (PTT) for voice detection and setting the keybind accordingly (HOTAS, Controller or Keyboard supported).

??? note "Common Issues"

    - **Problem:** I don’t know what to enter as the commander name.
    
        **Solution:** Use any name you prefer. This is how the AI will address you in the game and relate events inside the game to you.

    - **Problem:** I don’t know how to obtain an API key.
    
        **Solution:** Visit [OpenAI API Keys](https://platform.openai.com/api-keys) to sign up and generate a key if you haven’t done so already. Note that you may need to add credits to your account to activate the API.

---

## Step 5: Open the "Debug Output" Window

1. Click the "Start AI" button to get started.
2. Verify that a black "Debug Output" window appears.

??? note "Common Issues"

    - **Problem:** The application is unresponsive.
    
        **Solution:** Close the application and try again. If the issue persists, reach out to support for assistance.

---

## Step 6: Check for Errors in the "Debug Output" Window

1. Look for any error messages in the "Debug Output" window immediately after starting the application.

??? note "Common Issues"

    - **Problem:** Errors related to "chat.exe" appear.
    
        **Solution:** Re-extract the zip file and ensure an antivirus exception is set to prevent file deletion.

---

## Step 7: Test the Application’s Voice Detection

1. Start speaking into your microphone, either using Push-to-Talk (PTT) or voice detection.
2. Verify that your speech text appears in the "Debug Output" window.

??? note "Common Issues"

    - **Problem:** An error message appears containing the number "429"
        
        **Solution:** If you have recently charged your credit balance, you may need to wait a few minute for the payment to process. If you have not charged your account, you need to do so to use the API.

    - **Problem:** Nothing happens when you speak.
    
        **Solution:** Check your microphone settings and ensure it’s properly configured for the application.

---

## Step 8: Check the Response

1. After you speak, confirm that the AI generates a response, visible in the "Debug Output" window.
2. Ensure that the application reads the response text aloud.

??? note "Common Issues"

    - **Problem:** The application doesn't generate or read out responses.
    
        **Solution:** Ensure your audio output is working correctly. If the issue persists, check for error messages and consult support if needed.

---

## Step 9: Test a Command

1. Try issuing a command to the AI, such as "Retract landing gear."
2. Observe if the AI performs the action.
3. Read more about the available commands in the [Actions](./20_actions.md) documentation.

??? note "Common Issues"

    - **Problem:** The AI acknowledges the command but does not perform it.**
    
        **Solution:** Ensure that all keybindings are properly configured. See [Keybindings](./keybindings.md) for more information.

    - **Problem:** The AI tells me to check the keybindings.
    
        **Solution:** Check the [Keybindings](./keybindings.md) documentation for more information.

---