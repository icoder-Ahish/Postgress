# Postgress

# Install Postgres on Your system

## Here are the steps to download the postgres sql:

(1) Go to the official PostgreSQL website: https://www.postgresql.org/
(2) Click on the "Download" button at the top of the page.
(3) Select your operating system (in this case, Windows).
(4) Select your version (preferably the latest stable release).
(5) Download the installer appropriate for your system (32-bit or 64-bit).
(6) Run the downloaded installer and follow the instructions.
(7) During the installation, you will be prompted to set a password for the default PostgreSQL user ("postgres").
(8) Complete the installation process.

After the installation, you can access the PostgreSQL command-line interface ("psql") by opening the "SQL Shell (psql)" program from the PostgreSQL folder in your Start Menu.

You can also access PostgreSQL using a graphical user interface (GUI) tool such as pgAdmin, which you can download from the PostgreSQL website.


## Connection with streamlit code snnipet

    import streamlit as st
    import psycopg2

    # Define function to establish database connection
    def create_conn():
        conn = psycopg2.connect(
            host="localhost",
            database="database_name",
            # database="streamlitdb",
            user="postgres",
            password="linux"
        )
        return conn

    # Connect to database
    conn = create_conn()

    # Define SQL query
    query = "SELECT * FROM users;"
    # query = "SELECT * FROM streamlitTable;"

    # Execute query
    cur = conn.cursor()
    cur.execute(query)

    # Fetch and display results
    results = cur.fetchall()
    for row in results:
        st.write(row)

    # Close cursor and connection
    cur.close()
    conn.close()



