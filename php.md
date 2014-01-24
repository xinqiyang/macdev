#php开发环境的设置   

##PHP(可选)


Php的环境配置,也可以直接实用brew来进行安装,安装的是比较新的php5.x系列的版本.

我这边自己安装的是5.4的之前的版本. 最新的应该也差不多...



###install php 

brew tap homebrew/dupes 
brew tap josegonzalez/homebrew-php 

###brew install php54
brew install php54 --width-mysql --with-intl --with-fpm --without-apache



Install Xcode, Command Line Tools, Xquartz (on 10.8)    

In a terminal (probably best to do one thing at a time):    

ruby -e"$(curl -fsSkL raw.github.com/mxcl/homebrew/go)"   

brew tap homebrew/dupesbrew tap josegonzalez/homebrew-php   

brew install php54 --with-mysql   

chmod-R ug+w/usr/local/Cellar/php54/5.4.7/lib/php   

pear config-set php_ini /usr/local/etc/php/5.4/php.ini   

PATH="$(brew --prefix josegonzalez/php/php54)/bin:$PATH"   

cat>>/etc/apache2/httpd.conf << EOF   
LoadModule php5_module    /usr/local/Cellar/php54/5.4.7/libexec/apache2/libphp5.so   
EOF   

brew install php54-mcrypt   
brew install php54-apc   
brew install php54-xdebug   

brew install mysqlunset TMPDIRmysql_install_db --verbose--user=`whoami`--basedir="$(brew --prefix mysql)"--datadir=/usr/local/var/mysql --tmpdir=/tmp     
mkdir-p ~/Library/LaunchAgents   

cp/usr/local/Cellar/mysql/5.5.27/homebrew.mxcl.mysql.plist ~/Library/LaunchAgents/   

launchctl load -w ~/Library/LaunchAgents/homebrew.mxcl.mysql.plist   

launchctl start homebrew.mxcl.mysql   
cat>> ~/.profile << EOF   
PATH="$(brew --prefix josegonzalez/php/php54)/bin:$PATH"   
EOF



http://i.justrealized.com/2010/install-pear-phpunit/

pear channel-discover pear.phpunit.de
pear channel-discover pear.symfony-project.com
pear channel-discover components.ez.no
pearinstallphpunit/PHPUnit














