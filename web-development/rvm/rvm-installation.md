RVM (ruby version manager) cheats
=================================

<h4>Install RVM:</h4>
<pre>
$ \curl -sSL https://get.rvm.io | bash -s stable --ruby
$ nano ~/.bash_profile 
# Add to file and source:
[[ -s "$HOME/.profile" ]] && source "$HOME/.profile" # Load the default .profile
[[ -s "$HOME/.rvm/scripts/rvm" ]] && source "$HOME/.rvm/scripts/rvm"
</pre>

<h4>Install Ruby in RVM:</h4>
<pre>
$ rvm install 2.1.0
</pre>


<h4>Remove RVM:</h4>
<pre>
$ rvm implode
$ gem uninstall rvm
# remove environment variables in bash_profile
</pre>
