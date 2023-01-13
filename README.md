# sqinner 
A MSSQL service login bruteforcer and `xp_cmdshell` wrapper

## Setup

### Install dependencies

#### 1. Clone this repo

#### 2. Install required system packages

`[sudo] apt-get install freetds-dev`

#### 3. Install required Python packages

`[sudo] pip install -r requirements.txt`

#### 4. Run sqinner.py

`python sqinner.py -h`

## Usage 

#### Help

`python sqinner.py -h`

#### General usage

sqinner's command format is as follows:

`python sqinner.py <target> <port> -u/--usernames <usernames> -p/--passwords <passwords> [-v/--verbose]`

With the following inputs:

`<target>` - the IP address or hostname of the target running MSSQL

`<port>` - which port to attempt a connection on

`<usernames>` - a single value or comma-separated list of usernames and/or filenames in which to look for usernames, e.g. `-u users.txt,sa,test`

`<passwords>` - a single value or comma-separated list of passwords and/or filenames in which to look for passwords, e.g. `-u passwords.txt,sa,test`

## Examples

We'll use the target `10.0.0.1` and assume that it has MSSQL running and listening on port `1433` for these examples.

#### Attempt a login with username 'sa' and password 'sa' with verbose output

`python sqinner.py 10.0.0.2 1433 -u sa -p sa -v`

#### Attempt a login with usernames 'sa' and 'test', and passwords 'sa' and 'test'

`python sqinner.py 10.0.0.2 1433 -u sa,test -p sa,test`

#### Attempt a login with usernames contained within users.txt and 'test', and passwords contained within passwords.txt and 'test' with verbose output

`python sqinner.py 10.0.0.2 1433 -u users.txt,test -p passwords.txt,test -v`
