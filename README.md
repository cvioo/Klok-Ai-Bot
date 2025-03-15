# Klok-Ai Bot 

How to Use:

1. Open the console in your Microsoft Edge browser (Ctrl + Shift + I or F12).


2. Paste the entire script above into the console and press Enter.


3. The auto chat will begin

4. SCRIPT ------

// Function to display a "Follow on Twitter" pop-up warning bar
function displayTwitterFollowWarning() {
    const warningBar = document.createElement('div');
    
    // Styling the warning bar to be fixed at the top of the window
    warningBar.style.position = 'fixed';
    warningBar.style.top = '0';
    warningBar.style.left = '0';
    warningBar.style.width = '100%';
    warningBar.style.backgroundColor = '#ffcc00';
    warningBar.style.color = '#000';
    warningBar.style.textAlign = 'center';
    warningBar.style.padding = '10px';
    warningBar.style.zIndex = '10000'; // Ensure it's above all other elements

    // Adding text and the "Follow" button
    warningBar.innerHTML = `
        <span style="font-size: 16px; font-weight: bold;">Follow @ROSLA_AHEMED on Twitter!</span>
        <a href="https://twitter.com/ROSLA_AHEMED" target="_blank" style="background-color: #1DA1F2; color: white; padding: 10px 20px; border: none; border-radius: 5px; cursor: pointer; margin-left: 20px; text-decoration: none;">
            Follow Now
        </a>
        <button id="closeWarningBar" style="margin-left: 20px; padding: 5px 10px; background-color: red; color: white; border: none; border-radius: 3px; cursor: pointer;">Close</button>
    `;

    // Append the warning bar to the document body
    document.body.appendChild(warningBar);

    // Close button functionality
    document.getElementById('closeWarningBar').addEventListener('click', function() {
        warningBar.style.display = 'none'; // Hide the warning bar when closed
    });
}

// Function to automatically send chat messages
(function() {
    const questions = [
        "How do I sign up?",
        "Is there a free trial?",
        "How do I reset my password?",
        "What are the benefits of KlokApp?",
        "How does KlokApp AI work?",
        "Is there customer support available?",
        "Can I cancel my subscription?",
        "What payment methods are accepted?",
        "How do I change my email address?",
        "Where can I see my usage statistics?",
        "Can I upgrade my plan later?",
        "How do I earn more points on Klok?",
        "Are there any discounts available?",
        "Is my data safe with Klok?",
        "Can I integrate Klok with other tools?",
        "Where can I read the privacy policy?",
        "Can I share my account with someone else?",
        "How do I report a bug?",
        "Does Klok offer an API?",
        "How do I update my billing information?",
        "What happens if I exceed my usage limit?",
        "Can I get a refund?",
        "How do I log out?",
        "What features are in development?",
        "Does Klok offer team collaboration features?",
        "Where can I find tutorials for Klok?",
        "Can I customize my dashboard?",
        "How do I deactivate my account?",
        "What is Klok's uptime guarantee?",
        "How do I contact technical support?",
        "Can I integrate Klok with Slack?",
        "How does Klok handle outages?",
        "How do I change my password?",
        "What is Klok's cancellation policy?",
        "Can I use Klok on mobile?",
        "Is there a KlokApp community?",
        "What languages does Klok support?",
        "What happens if I lose my password?",
        "Are there referral rewards?",
        "Can I manage multiple accounts on Klok?",
        "What security measures are in place?",
        "Can I link my social media to Klok?",
        "How do I add a new user?",
        "Does Klok provide analytics?",
        "How can I track my performance?",
        "Is there an onboarding process?",
        "How do I delete my account?",
        "What happens when my subscription expires?",
        "How do I reset my 2FA?",
        "Can I export my data?"
    ];

    let questionIndex = 0;

    // Function to send a message
    function sendMessage(question) {
        const textarea = document.querySelector('textarea[placeholder="Ask me anything "]');
        const sendButton = document.querySelector('button[type="submit"]');
        
        if (textarea && sendButton) {
            textarea.value = question;
            textarea.dispatchEvent(new Event('input', { bubbles: true }));
            sendButton.click();
        } else {
            console.log('Chat input field or send button not found.');
        }
    }

    // Function to ask the next question with a 30-second delay
    function askNextQuestion() {
        if (questionIndex < questions.length) {
            sendMessage(questions[questionIndex]);
            questionIndex++;
            setTimeout(askNextQuestion, 30000); // Wait 30 seconds between questions
        }
    }

    // Start asking questions
    askNextQuestion();

    // Show Twitter follow pop-up after 30 seconds
    setTimeout(displayTwitterFollowWarning, 30000);

})();
