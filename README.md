Prompt Engineering Tutorial for QA & GitHub Copilot

Book Structure (From Beginner to Expert)

1. Introduction to Prompt Engineering

Imagine you're speaking to a powerful assistant who knows almost everything—but only gives you the best response when you ask the right question. That "question" is your prompt.

Prompt Engineering is the art and science of crafting clear, goal-driven prompts to get the most accurate, useful responses from language models like ChatGPT and GitHub Copilot. In QA, it can automate tedious testing tasks, speed up debugging, and supercharge documentation.

🎯 Real-World Analogy:

Think of a prompt like a Jira ticket. If you write a vague one, the developer may ask 5 follow-ups. But if it's specific, it can go straight to execution.

🤖 In QA and automation, prompt engineering can help:

Generate robust Selenium or Rest Assured test cases

Discover edge cases that are easily missed

Explain or refactor existing test code

Summarize failed logs or compare versions of scripts

🧠 Why It Matters:

GPT-4 can process 50+ pages of code at once

GitHub Copilot can suggest tests, functions, regex

You save hours on boilerplate and research

By the end of this book, you'll be able to:
✅ Create powerful prompts for testing tools✅ Use GitHub Copilot like a smart pair programmer✅ Build your own prompt libraries✅ Teach others on your team how to do the same

2. Understanding Language Models (LLMs)

Before using them effectively, let’s understand how LLMs work.

🧩 Core Concepts

Token: The basic unit of input. "TestAutomation" = 2 tokens.

Temperature: Controls randomness. Lower = more accurate, Higher = more creative. For QA, stick to 0.2–0.5.

Context Window: LLM memory span. GPT-4 = ~32,000 tokens (~50 pages).

💡 LLM Capabilities for QA:

Generate structured code (tests, mocks, data factories)

Convert scenario steps into test functions

Explain complex functions in layman’s terms

Detect gaps in test coverage

❗ Limitations:

May hallucinate functions or methods

Can't access real-time data or logs (unless you paste them)

Output depends entirely on your input clarity

✅ Best Practice: Treat LLMs like junior engineers. If you give sloppy input, expect guesswork.

3. Anatomy of a Good Prompt

Let’s say you want to generate a login test. You could say:❌ "Write a login test." — too vague.✅ "Write a Java Selenium test using Selenide to verify login with valid and invalid credentials, and assert expected error/success messages."

🛠️ 3 Parts of a Good Prompt

Instruction – What to do ("Write a test case")

Context – Language, framework, endpoint, data

Constraints – Timeouts, response codes, structure

✨ Prompt Formats

Zero-shot – No examples. Just instructions.

Few-shot – Include 1-2 examples first

Chain-of-thought – Add logical reasoning steps

🔁 Example Progression

Zero-shot:

"Write a login test in Java."

Few-shot:

"Here are two test cases. Write one more for forgot password."

Chain-of-thought:

"Generate a test and explain how each step validates the feature."

✅ Best Practice: Start simple, iterate. Always test your prompt.

4. Prompt Patterns and Templates

Use these templates daily in QA. Memorize or save them!

🧪 Code Generation

"Write a Java method to validate email format using regex."

🧪 Test Case Generation

"Generate a Selenium test using TestNG that opens the login page, enters credentials, clicks submit, and validates dashboard access."

🐞 Bug Reproduction

"Simulate steps in Selenium to reproduce a 403 forbidden error when accessing /admin without login."

🧹 Data Extraction

"Extract phone numbers from this JSON response."

📊 Test Summary

"Summarize the difference between test_log_v1 and test_log_v2 in less than 5 bullet points."

✅ Best Practice: Always include URLs, sample payloads, or schema in the prompt if needed.

5. Prompt Engineering for QA Automation

Let’s walk through real-world QA prompting examples you can use today.

✅ UI Test Case (Selenium/Selenide)

Basic Prompt:

"Write a Selenium Java test case using Selenide for login."

Better Prompt:

"Generate a Java UI test using Selenide that navigates to https://example.com/login, tests with valid and invalid credentials, checks error alerts, and verifies dashboard on successful login."

✅ Do:

Specify site URL

Mention all user scenarios (valid/invalid)

Include success + failure conditions

🚫 Don't:

Ask generic prompts like "Make a UI test"

Forget assertions or output expectations

✅ API Testing (Rest Assured)

Prompt:

"Generate a JUnit test using Rest Assured for POST /api/users with name and email. Expect 201. Add negative case for missing email."

Bonus Tip: Add sample JSON payload to your prompt for more precision.

✅ Edge Case Discovery

Ask:

"List 7 edge cases for a registration form with name, email, phone."

Then follow-up:

"Convert to BDD format using Gherkin."

✅ Scenario to Code Prompting

You write:

"Convert this test scenario into a Selenium TestNG test: 'User clicks forgot password, submits email, receives reset confirmation.'"

Ask for refinements:

"Now add assertion to verify toast message and navigation to homepage."

✅ Best Practice: Treat prompt engineering like TDD—iterate quickly.

6. Prompt Engineering with GitHub Copilot Enterprise

Let’s now focus on Copilot—your AI pair programmer inside IntelliJ or VSCode.

💡 What’s Different in Copilot Enterprise?

Access to internal codebase context (with org permissions)

Custom-trained models based on enterprise workflows

Enhanced security and IP compliance

Markdown-aware, docstring-based completions

🖥️ Using Copilot in IntelliJ (QA Example)

Step-by-step for UI automation test prompt:

Open LoginTest.java

Type a comment:

// Test: Login with valid credentials using Selenide

Pause and watch Copilot generate a valid test function

Refine by adding inline prompts:

// Add negative case for blank password

Copilot understands context from filenames, previous code, and comment descriptions.

🛠️ Example Prompts Inside IDE:

// Test: POST /users returns 201 with valid payload

// Validate email field with incorrect format

// Extract phone number from user JSON response

✅ Pro Tip: Copilot loves detailed comments. Don’t just type “Test API.” Instead, describe the flow:

"Test POST /login with missing password. Assert 401 error response with error message."

✅ Best Practices for Copilot Prompting:

Always begin with a clear comment describing what you want

Break down prompts: one action per line

Keep your function names descriptive (Copilot reads them!)

Provide JSON examples in multiline comments when needed

⚠️ Common Pitfalls:

🚫 Vague prompts: “Do login test”🚫 Missing assertions: Copilot may stop at UI interaction if no assertion is mentioned🚫 Too many prompts in one comment block

🔁 Iteration Workflow:

Type high-level comment

Let Copilot autocomplete

Accept, review, and modify

Rerun and prompt again to refine

✅ Pro Tip: Treat Copilot like a junior SDET. Review everything it writes.

7. Advanced Prompting Techniques

Once you're comfortable writing clear, structured prompts, it's time to level up. These advanced techniques let you do more with fewer prompts and get predictable, high-quality results.

🔗 Prompt Chaining

Prompt chaining is the practice of breaking a big task into smaller logical steps and prompting each step one-by-one.

Example Use Case:

You want to generate test cases for a new signup feature.

First prompt:

"List 5 possible user journeys for signup on a typical e-commerce app."

Second prompt:

"For each journey, write a test case in Gherkin format."

Third prompt:

"Convert these Gherkin test cases into Java TestNG tests using Selenide."

✅ Best Practice: Use this when the LLM fails to complete complex tasks in one go.

🧠 System Prompts and Role-Based Prompting

Language models can behave differently based on the "persona" or role you assign them.

Example:

"You are a senior QA automation engineer. Write a Selenium test for the login feature with detailed comments and best practices."

This sets the tone for the response and influences quality.

✅ Use role context when asking for structured, professional output or domain-specific tasks.

📦 JSON & Structured Output Prompts

For QA reporting, test data generation, or integrations, you often want structured responses like JSON.

Example:

"Generate 3 negative test cases for a login API. Output each case as JSON with keys: test_name, input, expected_output, status_code."

Sample Output:

[
  {
    "test_name": "Missing password",
    "input": {"username": "user1"},
    "expected_output": "Password is required",
    "status_code": 400
  }
]

✅ Pro Tip: Always state: “Respond only in JSON. No explanations.” to avoid extra text.

🧪 Combining Tools (LLM + Copilot + CLI)

Prompt engineering becomes more powerful when you combine tools:

Use ChatGPT to generate edge cases

Use Copilot to turn them into code

Use CLI tools to validate or run them

Workflow:

ChatGPT → "List 10 edge cases for password reset"

ChatGPT → "Generate Java test cases"

Copy to IDE → Copilot continues code with test coverage

✅ Best Practice: Keep a clipboard file or PromptPlaybook.md in your repo with reusable prompt chains.

8. Debugging & Iterating Prompts

Even the best prompts sometimes fail. The model might give:

Partial output

Wrong format

Repeated or irrelevant content

Like code, prompts need to be debugged and refined. Here’s how.

🔍 Common Prompt Failure Modes

Vague prompt → Ambiguous or generic output

Overloaded prompt → Confusing or incomplete response

No formatting instructions → Output mixes explanation with code

No examples provided → LLM guesses instead of following pattern

🔄 Prompt Refinement Workflow

Think of this like testing a flaky script:

Start with a simple prompt

✅ "Write a Selenium test for login page."

Add context

✅ "Use Selenide in Java. Input valid and invalid credentials."

Specify structure or format

✅ "Respond only with code."

Test output and improve

❌ If assertions are missing, re-prompt:

"Add assertions for success and failure states."

✅ Pro Tip: Save every good version of a prompt that worked. Reuse it later.

🧪 Prompt A/B Testing

Test two prompt versions for the same task and compare which gives better, cleaner, or more accurate results.

Version A:

"Write a test case for login."

Version B:

"Generate a Java TestNG test using Selenide to test login on https://app.testsite.com. Check both valid and invalid flows and assert UI messages."

📊 Evaluate output:

Which test has better assertions?

Is the code reusable?

Is it production-grade?

✅ Build your own "prompt test cases" for quality control.

🗂️ Creating & Maintaining a Prompt Library

Once you find prompts that work reliably, don’t keep them in memory—document them.

📁 Sample Prompt Library Structure:

/PromptPlaybook.md
  - UI Prompts
  - API Prompts
  - Data Validation
  - Debug Logs
  - Code Review

✅ Best Practice: Add comments, versions, and when to use which prompt.

✅ Organize by framework:

Selenide

Rest Assured

Postman

Cucumber (Gherkin)

🔧 Tools for Prompt Iteration

ChatGPT history → Reuse previous successful prompts

Notion / Obsidian / GitHub Wiki → To store structured prompt libraries

Versioned Prompt Sheets (Excel or Markdown) → Track refinements over time

✅ Use "prompt history" just like commit history. Learn what worked and why.



9. Collaborative Prompting

Just like we share test scripts, libraries, and frameworks in a QA team—prompt engineering can and should be collaborative.

🤝 Why Collaborate on Prompts?

Prompts that work for one engineer will likely work for others

Encourages prompt reuse, not reinvention

Reduces prompt failures and accelerates test generation

Teaches junior engineers better practices

👥 Prompt Reviews (Like Code Reviews)

Start treating prompts as first-class test assets.
Have teammates review prompt phrasing, clarity, constraints, and expected outputs.

✅ Good Prompt Review Checklist:

Is the intent clear?

Is the scope well-defined?

Are test conditions/assertions explicit?

Does the prompt avoid vague phrasing like "check" or "verify"?

✅ Pro Tip: Add reviewed prompts to your team’s internal QA handbook.

🔄 Version Control for Prompts

Just like you maintain Git repos, create a version-controlled prompt library.

Structure:

/prompts
  ├── ui-tests
  ├── api-tests
  ├── testdata-generation
  └── utils

README.md  → How to use, when to use, examples

Each prompt file can include:

Description

Input prompt

Expected response format

Edge case notes

Links to working test examples

✅ Tip: Maintain a changelog for evolving prompt logic

💼 Prompts in QA Onboarding

When new testers join your team:

Let them study your PromptPlaybook

Assign them a "prompt A/B challenge"

Review their results in a learning session

This builds prompting muscle memory across the org.

📣 Communication + Prompts = Power

Pair programming with LLMs works even better when you:

Co-write prompts live in meetings

Screen share with junior QAs to show your prompting thought process

Convert real bug reports into promptable scenarios

Example:

"Given this real production bug report, write 3 promptable test scenarios and generate code with Copilot."

✅ Prompt reviews = knowledge sharing + QA mentorship

10. Ethics & Guardrails

Using AI tools like ChatGPT or Copilot in a QA environment introduces powerful capabilities—but also new risks. Ethics and guardrails ensure that your prompts:

Don't leak sensitive data

Don't result in unsafe or biased outputs

Respect organizational compliance policies

Let’s break it down by what to watch out for, and how to mitigate risk.

🚫 Common Prompting Risks in QA

1. Leaking Sensitive Info

Prompts like:

"Generate tests for our internal payment gateway code snippet"

...may expose business logic, secrets, or tokens if shared publicly or copied into an online LLM with no data protection.

✅ Safe Practice: Use only enterprise-level tools like GitHub Copilot Enterprise or on-prem LLMs for sensitive repos.

2. Hallucinations (False Information)

LLMs may invent classes, methods, or API endpoints that don’t exist.

Example:

"Write a Selenium test for UserController.validateToken()" (but no such method exists)

✅ Always review generated code manually before committing.✅ Use Copilot suggestions as drafts, not production code.

3. Bias or Discriminatory Suggestions

Even in QA, if you're testing forms with user data, poorly framed prompts may suggest:

Gendered test data only

Culturally biased names or assumptions

✅ Provide neutral or inclusive context when generating data.✅ Validate generated data fields for representation.

🛡️ Best Practices for Safe Prompting

✅ Use AI in Secure Environments

Stick to Copilot Enterprise, which respects org boundaries

Disable prompts that include confidential user data

✅ Keep Prompts Reproducible & Transparent

Save input/output pairs for audit

Share prompt versions with teammates

✅ Train Your Team in Responsible Use

Include prompt ethics in onboarding

Review examples of dangerous or misleading prompts

✅ Avoid Prompts Like:

“Scan our entire repo and write all tests”  ❌

“Write tests for user auth with this private key”  ❌

✅ Do This Instead:

“Write a generic Selenide test for login, without using internal APIs”

“Suggest test coverage areas for this code snippet (no credentials included)”

✅ When in doubt, prompt with abstraction. Remove real tokens, emails, API secrets.

⚖️ Legal & Compliance Notes

LLMs do not guarantee output is free of IP conflicts

Code copied from AI should always be reviewed & checked for license compatibility

Don’t paste proprietary bug reports into free online tools

✅ Use enterprise chat + enterprise Copilot + org GitHub account to stay safe.

11. Future of Prompt Engineering

Prompt engineering is not a static skill—it’s evolving fast. The future blends LLMs, automation agents, and retrieval systems into seamless workflows.

Let’s look at the trends shaping the next era of QA + AI.

🤖 AI Agents for QA

AI agents are autonomous tools that:

Take goals as input ("achieve 90% test coverage")

Break it into subtasks

Prompt LLMs at each stage

Collect results and improve over time

🧠 Example: Autonomous Test Generator Agent

Reads your API spec or Swagger doc

Generates test scenarios (prompt 1)

Converts to Gherkin syntax (prompt 2)

Generates Selenium code (prompt 3)

Logs test summary & coverage report (prompt 4)

✅ Why it matters: You go from writing tests manually to defining what “coverage” means and letting the agent do the work.

📚 Retrieval-Augmented Generation (RAG)

RAG = combining LLMs with search/retrieval of internal documents.

🔧 QA Example:

“Generate test cases for our signup API using our internal test strategy document + swagger.yaml”

LLM + RAG can:

Pull your org’s test templates

Reference actual business rules

Avoid hallucinating because it uses real source docs

✅ Use RAG when you want outputs aligned to company standards
✅ Platforms like OpenAI’s GPTs or LangChain support RAG-based workflows

🔁 CI/CD + Prompt Automation

You can integrate prompts into your test pipelines!

Example Use Case:

In your GitHub Actions workflow:

On every new feature branch, trigger a prompt like:

"Suggest 3 regression test cases based on changes in this PR."

This can:

Speed up peer review

Suggest missed test areas

Auto-generate tests for small changes

✅ Combine GitHub Copilot with GitHub Actions + ChatGPT API for magic

🔮 What’s Next?

LLM agents that file bugs, reproduce them, and suggest fixes

Prompt IDEs with autocomplete for prompt construction

Teams using prompt coverage metrics just like code coverage

“PromptOps” roles managing prompt workflows in CI/CD

✅ Get ahead: start documenting prompts like test cases
✅ Reuse + refine them as first-class QA assets

Congratulations! You’ve reached the end of the expert-level tutorial.
Next steps:

Use this material in your team seminar

Build your own prompt libraries

Share successful prompt patterns within your QA org

You’re now equipped to lead the prompt engineering revolution inside your team 💡

