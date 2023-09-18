
# Food Pantry Inventory Management

![GitHub repo size](https://img.shields.io/github/repo-size/YourUsername/Food-Pantry-Inventory)
![GitHub stars](https://img.shields.io/github/stars/YourUsername/Food-Pantry-Inventory?style=social)
![GitHub forks](https://img.shields.io/github/forks/YourUsername/Food-Pantry-Inventory?style=social)

Welcome to the Food Pantry Inventory open-source project! This project is designed to track inventory in the warehouse of a food pantry. It enables you to manage boxes of products by location (row, bin, and tier), contents (green beans, corn, etc.), and expiration year. The expiration can optionally be tracked by half-year, quarter, or arbitrary month ranges.

## Quick Start

Follow these steps to get started with the Food Pantry Inventory project:

1. **Download and Unpack**
   - Download the zip file for the master branch of this project.
   - Unpack the zip file in a convenient directory.

2. **Create a Python Virtual Environment**
   - Navigate to the root directory of the project.
   - Create a Python virtual environment, e.g., `virtualenv venv`.
   - Activate the virtual environment using `source venv/bin/activate`.

3. **Install Dependencies**
   - Install the required libraries using `pip3 install -r requirements.txt`.
   - Note: If you are on Windows 10 and plan to run it locally, you may need to remove uWSGI and change Pendulum to 2.0.3 in the requirements file.

4. **Database Configuration**
   - This project defaults to using PostgreSQL. If you choose to use a different database, install any additional libraries needed to support it.

5. **Configure Private Settings**
   - Create a directory `./FPIDjango/private`.
   - Copy `./FPIDjango/private_settings.py` to `./FPIDjango/private/private_settings.py`.
   - Note: The `.gitignore` file is set to ignore anything in the `./FPIDjango/private` subdirectory.

6. **Database Setup**
   - Create a database and start a server for it. Make note of the database name, server access details (host, port, etc.), and credentials for a user that can modify the schema.

7. **Modify Private Settings**
   - Update `./FPIDjango/private/private_settings.py` as follows:
     - `DB_ENGINE` - Set to the appropriate backend for your database.
     - `DB_NAME` - Set the database name for this project.
     - `DB_USER` - User name from the credentials that can modify the schema for this database.
     - `DB_PSWD` - Password for the `DB_USER`.
     - `DB_HOST` - IP or URL to reach the database server.
     - `DB_PORT` - Port the server is using to listen for requests.
     - `MY_SECRET_KEY` - A random string of 50 bytes or more. You can use `./StandaloneTools/GenerateSecretKey.py` for this purpose.

8. **Database Migration**
   - Populate the database with required tables by running:
     ```bash
     ./manage.py migrate
     ```
   - Your database should now have tables starting with `auth*`, `django*`, and `fpiweb*`.

9. **Usage**
   - The inventory system is now ready to use.
     - To start it, use `run_inv`.
     - To test it, use `run_pytest` to run all Django unit tests and the pytests in the `tests` subdirectory.
     - Alternatively, you can run the tests with the following commands:
       ```bash
       source venv/bin/activate
       ./manage.py test
       ```

## Contributions

Contributions to this project are encouraged! If you have ideas for improvements, want to report issues, or contribute code, please feel free to open an issue or submit a pull request.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.

## Acknowledgments

Special thanks to the open-source community for valuable insights and tools.

---

You can use this template by creating a new README.md file in your GitHub repository and replacing "YourUsername" with your actual GitHub username or organization name. Customize and expand upon it as needed.
