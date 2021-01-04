	Hello everyone. Let's talk about linters and fixers, or how to never worry about code formatting. So what linters and fixers look like? Here some code fragment. As you can see, this is awful. There are so many repeat violations and so many issues, so imagine that fixing this code by hand one by one it will be just a nightmare and takes much time. And now I move to next slide and see what happens. So here is code that already cleaned up. So let's talk about how to do that.
	Even if it's not that extreme, you may be always dealing with the problems with the typos extra spaces, or additional tabs. The coding style guidelines are really useful. They makes the code more readable clean easy to spot problems, but the problem is they require a lot of effort, because we are human beings and we able to make mistakes. It  means that we introduce typos, leave extra space here and there, so it's really hard to achieve really really clean code. 
	Of course it's not a new issue and it was solved already. So we already have these tools called linters and fixers. They are indispensable tools to help us spot the mistake right away and keep our codes super clean  and tidy. 
	Now it's time to talk about differences between linters and fixers. Linters focuses at static code analysis and spotting problems. After analysis, they tell us what's wrong about the code or what can be potentially wrong about the code. 
	Here you can see what typically happened after you run linter. This linter called ESLint. We can see information about two mistakes, fist about exceeding the allowed line length and second about  about declaring an unused variable. Fixing this errors help us keep our code clean. 
	So how about the fixers? Fixers fix code according selected style guide and keep the code that fixes many issues by formatting the code. That's the fixers.
	Here you can see most popular tools which can help you with making your JS code really clean. They are: ESLint, Prettier.
	Let's talk about them in details.
	Let’s start with Prettier. What is Prettier? Prettier is an opinionated code fixer. It automatically formats your code in a specific way. So, prettier removed all extra spaces, replaces quotes with single one, displays nesting correctly. Take a look how's it works on the slide (GIF) to understand how it works. 
	So, why do we need it?
	Prettier cleans up existing code base: on a single command line. Only imagine how much time you need to clean up over 20,000 lines of code?
 	Easy to adopt: Prettier uses the least controversial coding style while formatting your code. Since it’s open source, many people work on it, fix and keep up to date.
   	Focus on writing code: developers spend a lot of time to formatting code and waste mental energy doing so. Let Prettier handle it while you focus on the core business logic. 
 	Helping Newbie Developers: If you are a new developer working side by side with great engineers and you want to look cool writing clean code, be smart! Use Prettier. Additionally Prettier help to increase your skill: you write new code properly after you see which corrections  Prettier did  with your code last time.
	So, how we can configure Prettier on your project? We need to create a prettier.config.js file in our root app folder, and add some prettier rules to it.
	Let's discuss it in more details.
	printWidth will ensure that your code does not exceed more then 100 characters.
	singleQuote will convert all your double quotes into single quotes.
	jsxBracketSameLine will put &gt; of a multi line JSX element on the last line.
	tabWidth specifies the number of spaces per indentation level.
	semi if true will print ; at the end statements.	
	ESLint
	ESLint is a code linter. There are code linters for most programming languages, and compilers sometimes incorporate linting into the compilation process. 
	Why do we need one for JavaScript?
	Since JavaScript is dynamic and a loosely typed language, it is prone to developer errors. JS is interpreted language, so we not able to fix it during compilation process.  .js files are typically executed before you will have chance to find syntax or other errors.
	Linting tools like ESLint allow developers to find problems with their JavaScript code without executing it.
	So, why we should use ESLint?
	Everything in ESLint is pluggable. You can add rules on run time — the rules and formatter don’t have to be bundled to be used. Every linting rule you add is stand alone, any rule can be turned on or off. Each rule can be set to a warning or an error. Your choice.
	Using ESLint, you get complete customization of how you want your style guide to look.
	Now there are 2 most popular style guides out there at the moment:
    	Google JavaScript Style Guide;
    	Airbnb JavaScript Style Guide.
	What style guide you use it's might depend on project. From my side I use Airbnb JavaScript Style Guide, let's quick check how we can configure ESLint to follow it.
	To start configuration process, firstly we should update our package.json file like this.
	At the first part  we place information about the project, next  scripts which we will use to initiate linter and  last part is dependencies we need. 
	So let’s talk about dependencies in more details.  
    babel-eslint: this package allows you to use lint on all Babel goodness easily. You don’t necessarily need this plugin if you are not using Flow or experimental features that are not yet supported by ESLint.
    eslint: this is the main tool that is needed for linting your code.
    eslint-config-airbnb: this package provides all the Airbnb’s ESLint configuration as an extensible shared configuration, which you can modify.
    eslint-plugin-babel: An eslint plugin companion to babel-eslint.
    babel-eslint does a great job at adapting eslint for use with Babel.
    eslint-plugin-import: This plugin intends to support linting of ES2015+ (ES6+) import/export syntax, and prevent issues with misspelling of file paths and import names. 
    eslint-plugin-jsx-a11y: linting rules in place for accessibility rules on JSX elements. Because accessibility is important!
    eslint-plugin-prettier: This helps ESLint work smoothly with Prettier. So when Prettier formats code, it does it keeping our ESLint rules in mind.
    eslint-plugin-react: React-specific linting rules for ESLint.
    eslint-config-jest-enzyme: This helps with React- and Enzyme-specific variables which are globalized. This lint config lets ESLint know about those globals and not warn about them — like the assertions it and describe.
    eslint-plugin-jest: ESLint plugin for Jest.
    Next step - to create a .eslintrc.js file in your root app/ folder. Lets talk about script content a little more.
    env: An environment defines global variables that are predefined. The available environments — in our case it is es6, browser and node.    .
    extends: An array of strings — each additional configuration extends the preceding configurations.
    Right now we are using the linting rules by airbnb which are extended to jest and then extended to jest-enzyme.
    plugins: plugins are basically linting rules that we want to use.
    Right now we are using babel, import, jsx-a11y, react, prettier, all of which I have explained above.
    parser: By default ESLint uses Espree, but since we are using babel, we need to use Babel-ESLint.
    parserOptions: When we change the default parser for Espree to babel-eslint , we need to specify parserOptions — it is required.
    In the options I tell ESLint that ecmaVersion is going to lint version 6. Since we are writing our code in an EcmaScript module and not a script we specify sourceType as module.
    rules: This is the part which I love the most about ESLint, the customization.
    All the rules that we have extended and added with our plugins, we can change or override. rules is the place where you do it. I have already put comments in the Gist against each rule and for your understanding.
    Now we configure ESLint and Prettier and able to keep our code clean.
    For more info about Linter and Fixers please check links in description.