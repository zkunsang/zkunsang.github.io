pen your terminal and run

curl -sSL https://raw.githubusercontent.com/rvm/rvm/master/binscripts/rvm-installer | bash -s stable
When this is complete, you need to restart your terminal for the rvm command to work.

Now, run rvm list known

This shows the list of versions of the ruby.

Now, run rvm install ruby@latest to get the latest ruby version.

If you type ruby -v in the terminal, you should see ruby X.X.X.

If it still shows you ruby 2.0., run rvm use ruby-X.X.X --default.