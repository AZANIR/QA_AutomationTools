# Cross environment


Managing environment variables in Nodejs and Modern JS apps
=====================================

![](https://miro.medium.com/v2/resize:fit:828/format:webp/1*bNXslQsg8CYCyD5-1MkK5A.jpeg)

Cross-env is a tool that helps set environment variables across different platforms in a Node.js project. It is particularly useful when working with different operating systems, as environment variables may be defined differently depending on the platform being used. Cross-env provides a consistent way to set environment variables regardless of the platform.

Using Cross-env in a JavaScript test project is straightforward. You can simply install it as a development dependency using npm or yarn:
Cross-env is a tool that helps set environment variables across different platforms in a Node.js project. It is particularly useful when working with different operating systems, as environment variables may be defined differently depending on the platform being used. Cross-env provides a consistent way to set environment variables regardless of the platform.

Using Cross-env in a JavaScript test project is straightforward. You can simply install it as a development dependency using npm or yarn:

.. code-block:: bash

    $ npm install --save-dev cross-env

Once installed, you can use it in your package.json file to define your npm scripts. Here's an example of how to use Cross-env with Jest:

.. code-block:: json

    {
      "scripts": {
        "test": "cross-env NODE_ENV=test jest"
      }
    }

In this example, we're setting the NODE_ENV environment variable to "test" using Cross-env before running the Jest test suite. This ensures that the test environment is properly configured.

You can also combine Cross-env with other environment variables defined in your project's .env file or through your operating system. Here's an example of how to combine Cross-env with a custom environment variable defined in a .env file:

.. code-block:: bash

    # .env file
    MY_CUSTOM_VAR=123

    # package.json file
    {
      "scripts": {
        "test": "cross-env NODE_ENV=test MY_CUSTOM_VAR=$MY_CUSTOM_VAR jest"
      }
    }

In this example, we're setting the MY_CUSTOM_VAR environment variable to the value defined in our .env file, and then using Cross-env to set it for the duration of our test script.

Cross-env is a powerful tool that can simplify cross-platform development and testing. By providing a consistent way to set environment variables, it can help you avoid common bugs and errors that can arise from differences in environment variable syntax and behavior across platforms.

Here's an example of how you can use Cross-env in a TypeScript project:

.. code-block:: json

    {
      "scripts": {
        "build": "cross-env NODE_ENV=production tsc",
        "dev": "cross-env NODE_ENV=development ts-node-dev src/index.ts",
        "test": "cross-env NODE_ENV=test jest"
      }
    }

In this example, we're using Cross-env to set the NODE_ENV environment variable to "production", "development", or "test" depending on the script we're running. This is a common pattern in Node.js projects, where different environment variables are used to configure different aspects of the application (such as database connections, API keys, or logging behavior).

Finally, here's an example of how to use Cross-env with a command-line tool like nodemon:

.. code-block:: json

    {
      "scripts": {
        "dev": "cross-env NODE_ENV=development nodemon --exec ts-node src/index.ts"
      }
    }

In this example, we're using Cross-env to set the NODE_ENV environment variable to "development" before running nodemon. This allows nodemon to watch our TypeScript files and restart the server automatically when changes are detected, while ensuring that the environment is properly configured.

Overall, Cross-env is a powerful tool that can simplify the management of environment variables in Node.js projects. By providing a consistent way to set environment variables across different platforms, it can help you avoid common bugs and errors, and ensure that your application runs reliably and consistently across all environments.


How it use another environment in real projects
===================================================

In real projects, you may use other environment variables in addition to or instead of the NODE_ENV variable, depending on your needs. Here are some examples of other environment variables that are commonly used in Node.js projects:

    1 PORT: This environment variable is used to specify the port on which the server should listen. For example:

    .. code-block:: json

        "dev": "cross-env NODE_ENV=development PORT=3000 nodemon --exec ts-node src/index.ts"

    2 DATABASE_URL: This environment variable is used to specify the URL of the database to connect to. For example:

    .. code-block:: json

        "dev": "cross-env NODE_ENV=development DATABASE_URL=postgres://user:password@localhost/mydatabase nodemon --exec ts-node src/index.ts"

    3 API_KEY: This environment variable is used to specify an API key that is required for accessing an external API. For example:

    .. code-block:: json

            "dev": "cross-env NODE_ENV=development API_KEY=12345 nodemon --exec ts-node src/index.ts"

    4 LOG_LEVEL: This environment variable is used to specify the level of logging that should be used in the application. For example:

    .. code-block:: json

        "dev": "cross-env NODE_ENV=development LOG_LEVEL=debug nodemon --exec ts-node src/index.ts"


In general, you can use any environment variable that is relevant to your application. You can define these variables in a .env file or in the environment of the machine on which the application is running. You can then use Cross-env to set these variables for the duration of your script, as shown in the examples above. This can help you ensure that your application is properly configured and behaves consistently across all environments.

How to use it in test code
==================================

In test code, you can access environment variables using the process.env object. To use Cross-env in test code, you can set the NODE_ENV environment variable to "test" or any other value that you need for your tests.

Here's an example of how to use Cross-env in Jest test code:

.. code-block:: javascript

    // example.test.ts

    describe("Example tests", () => {
      beforeAll(() => {
        process.env.NODE_ENV = "test";
      });

      it("should run test", () => {
        // test code here
      });
    });


In this example, we're setting the NODE_ENV environment variable to "test" in the beforeAll function, which runs once before all of the tests. This ensures that the environment is properly configured for the duration of the tests.

You can use this pattern in any test framework or library that supports setting environment variables. Just make sure to set the environment variable at the appropriate point in your test code (such as in a beforeAll or beforeEach function), and access it using the process.env object.

Note that setting environment variables in test code can be useful for testing different configurations or behaviors of your application. For example, you might want to test how your application behaves when the database connection fails, or when a certain API key is not provided. By setting environment variables in your test code, you can simulate these scenarios and ensure that your application behaves correctly under different conditions.


Example switch with different environments in test code
===================================

Sure, here's an example of how you can switch between different environments in test code using Cross-env:

.. code-block:: javascript

    // example.test.ts

    describe("Example tests", () => {
      describe("In development environment", () => {
        beforeAll(() => {
          process.env.NODE_ENV = "development";
        });

        it("should run development test", () => {
          // test code for development environment
        });
      });

      describe("In production environment", () => {
        beforeAll(() => {
          process.env.NODE_ENV = "production";
        });

        it("should run production test", () => {
          // test code for production environment
        });
      });
    });

In this example, we're using Jest to run two sets of tests: one for the development environment, and one for the production environment. We're using the describe function to group the tests by environment, and setting the NODE_ENV environment variable to "development" or "production" in the beforeAll function of each group.

When Jest runs the tests, it will first set the NODE_ENV variable to "development" and run the tests in the first describe block. After that, it will set the NODE_ENV variable to "production" and run the tests in the second describe block. This allows you to test different configurations or behaviors of your application under different environments.

Note that this is just one example of how you can switch between environments in test code using Cross-env. You can adapt this pattern to your specific needs, and use it with any test framework or library that supports setting environment variables.


In the example I provided, if you choose the development environment, only the tests in the first describe block will run. The second describe block, which contains tests for the production environment, will be skipped.

This is because we're using the beforeAll function to set the NODE_ENV environment variable before running the tests in each describe block. So when the first describe block runs, NODE_ENV will be set to development, and the tests in that block will be executed. But when the second describe block is reached, NODE_ENV will be set to production, so the tests in that block will be skipped.

If you want to run tests for both environments, you can modify the example to use two different test files, one for each environment. For example:

.. code-block:: javascript

    // development.test.ts

    describe("Development tests", () => {
      beforeAll(() => {
        process.env.NODE_ENV = "development";
      });

      it("should run development test", () => {
        // test code for development environment
      });
    });

    // production.test.ts

    describe("Production tests", () => {
      beforeAll(() => {
        process.env.NODE_ENV = "production";
      });

      it("should run production test", () => {
        // test code for production environment
      });
    });


In this example, we're using two separate test files, one for the development environment and one for the production environment. Each test file sets the NODE_ENV environment variable in the beforeAll function, and contains tests that are specific to that environment. When you run your test suite, you can choose which test file(s) to run based on the environment you want to test.

To switch between different environments in your code depending on the NODE_ENV environment variable, you can use conditional statements or configuration files that are specific to each environment.

Here's an example of how you can use a configuration file to switch between environments:

.. code-block:: javascript

    // config.js

    const developmentConfig = {
      apiUrl: "http://localhost:3000",
      debug: true,
      // other configuration options for development environment
    };

    const productionConfig = {
      apiUrl: "https://api.example.com",
      debug: false,
      // other configuration options for production environment
    };

    const config = process.env.NODE_ENV === "production"
      ? productionConfig
      : developmentConfig;

    module.exports = config;

In this example, we're defining two configuration objects, one for the development environment and one for the production environment. We're then using the NODE_ENV environment variable to determine which configuration object to use, and exporting that object as the default export of the module.

To use this configuration file in your code, you can simply require it and access the configuration options as properties of the exported object:

.. code-block:: javascript

    // app.js

    const config = require("./config");

    if (config.debug) {
      console.log("Debug mode enabled");
    }

    fetch(config.apiUrl + "/data")
      .then(response => response.json())
      .then(data => {
        // process data using configuration options
      })
      .catch(error => {
        // handle error using configuration options
      });


In this example, we're using the config object to access the debug and apiUrl configuration options, depending on the current environment. If NODE_ENV is set to production, the config object will contain the configuration options for the production environment, and if it's set to development, it will contain the options for the development environment.

Note that this is just one example of how you can switch between environments in your code depending on the NODE_ENV environment variable. You can adapt this pattern to your specific needs, and use it with any configuration options that are specific to your application.

