1. Run `ruby -v`

If it doesn't return '2.1.1', keep going.  Otherwise, you're done.

2. Run `rvm`

If it doesn't print out info about RVM, follow the installation instructions here:

http://rvm.io/

3. Run `rvm install 2.1.1`

If it says you have rvm installed, keep going.
Otherwise, wait for it to install, and then keep going.

4. Run `rvm use --default 2.1.1`

Cross your fingers.

Run `ruby -v`.  It should now be 2.1.1.

Restart terminal.

Run `ruby -v`.  It should still be 2.1.1.

5. Make sure you have postgress installed.

`which postgres` should return something. Otherwise, install postrges with homebrew or apt-get.

6. Success.

Savor it.
