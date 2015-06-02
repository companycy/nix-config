
The final call in a tail-recursive function can be implemented by a jump back to the beginning of that function

The arguments of that call can overwrite the parameters of the current instantiation of gcd, so that no new stack space is needed.

More generally, if the last action of a function is a call to another (possibly the same)
function, only a single stack frame is needed for both functions. Such calls are called
“tail calls”. 


The type Int => Int is the type of functions that take arguments of type Int and
return results of type Int

The type Int => Int is the type of functions that take arguments of type Int and
return results of type Int

The part before the arrow ‘=>’ are the parameters of the function, whereas the part
following the ‘=>’ is its body.

(x1: T1, ..., xn: Tn) => E
is equivalent to the block
{ def f (x1: T1, ..., xn: Tn) = E ; f _ }




i meant things like "all members are private", "closures are classes", "a breakpoint in a line containg a call like foreach and a closure will break no matter if the "closure line" itself is executed or if the "execution cursor" is at the line outside the closure and "for loops are actually compiled to foreach-calls, and the inside of the loop is a closure"
these things. knowing that the mysterious variable "v$9" or whatever you are seeing in the debugger is actually a parameter that is named "x" in your code or knowing that you are a few steps deeper in the method call hierachy than you would seem to be greatly helps.



node --debug-brk 1.js

select * INTO OUTFILE '/tmp/2014-8-7.S3.csv' FIELDS TERMINATED BY ',' OPTIONALLY ENCLOSED BY '"' from gem_depletion_history where created_at between 1407340800 and 1407427199;

select * INTO OUTFILE '/tmp/test.csv' FIELDS TERMINATED BY ',' OPTIONALLY ENCLOSED BY '"' from gem_depletion_history where created_at between 1407340800 and 1407427199;

# select * INTO OUTFILE '/tmp/test.csv' FIELDS TERMINATED BY ',' OPTIONALLY ENCLOSED BY '"' from gem_depletion_history LINES TERMINATED BY '\n' where created_at between 1407340800 and 1407427199;

select column_name from information_schema.columns where table_schema='tw_1_mars' and table_name='thirdparty_orders';


mysql -u xixun -p -h172.16.3.22

1. use mysql;
2. update user set File_priv = 'Y' where User = 'xixun';
3. FLUSH PRIVILEGES;


alter table tablename modify column char(1) comment 'THIS IS A SIGN';

On GCC compile with -std=c++11.
On GCC versions below 4.7, use -std=c++0x -pthread (instead of -std=c++0x).


g++ -std=c++11 -o pthread_server pthread_server.cpp 


sudo tcpdump -i eth0

Next enter the following three commands to disable firewall.
# service iptables save
# service iptables stop
# chkconfig iptables off

If you are using IPv6 firewall, enter:
# service ip6tables save
# service ip6tables stop
# chkconfig ip6tables off


tc qdisc del dev eth0 root

tc qdisc add dev eth0 root handle 1: htb default 2 # r2q 1

tc class add dev eth0 parent 1: classid 1:1 htb rate 1mbit ceil 3mbit

tc  filter add dev eth0 parent 1: protocol ip prio 16 u32 match ip dst 192.168.0.9  flowid 1:1

tc  filter add dev eth0 parent 1: protocol ip prio 16 u32 match ip dst 192.168.0.117  flowid 1:1

tc  filter add dev eth0 parent 1: protocol ip prio 16 u32 match ip dst 192.168.0.118  flowid 1:1




C-x r k
Kill the text of the region-rectangle, saving its contents as the “last killed rectangle” (kill-rectangle). 
C-x r M-w
Save the text of the region-rectangle as the “last killed rectangle” (copy-rectangle-as-kill). 
C-x r d
Delete the text of the region-rectangle (delete-rectangle). 
C-x r y
Yank the last killed rectangle with its upper left corner at point (yank-rectangle). 
C-x r o
Insert blank space to fill the space of the region-rectangle (open-rectangle). This pushes the previous contents of the region-rectangle to the right. 
C-x r N
Insert line numbers along the left edge of the region-rectangle (rectangle-number-lines). This pushes the previous contents of the region-rectangle to the right. 
C-x r c
Clear the region-rectangle by replacing all of its contents with spaces (clear-rectangle). 
M-x delete-whitespace-rectangle
Delete whitespace in each of the lines on the specified rectangle, starting from the left edge column of the rectangle
C-x r t string <RET>
Replace rectangle contents with string on each line (string-rectangle). 

M-x string-insert-rectangle <RET> string <RET>
Insert string on each line of the rectangle.

M-^
join lines



Here is how to define a keyboard macro:

`C-x (’ or <f3>– start defining a keyboard macro
`C-x )’ or <f4>– stop defining the keyboard macro
And here is how to execute a keyboard macro you’ve defined:

‘C-x e’ or <f4> – execute the keyboard macro

delete-trailing-whitespace' 



sudo ln -s /usr/local/bin/node /usr/bin/node
sudo ln -s /usr/local/lib/node /usr/lib/node
sudo ln -s /usr/local/bin/npm /usr/bin/npm
sudo ln -s /usr/local/bin/node-waf /usr/bin/node-waf



# service iptables stop
# chkconfig iptables off


# service ip6tables stop
# chkconfig ip6tables off


chkconfig -- add frontendserver
chkconfig --level 345 frontendserver on



/Applications/Emacs.app/Contents/MacOS/Emacs --debug-init
Preferences -> Settings -> Keyboard and turn on "Use option as meta key"

:set formatoptions-=cro

rsync -avz ~/Documents/emacs-lisp root@192.168.101.1:~/
rsync -avz ~/.emacs.d root@192.168.101.1:~/.emacs.d/

rsync --partial <!--  -->

--delete-source-files
-Ph

cp .emacs.linux .emacs


sudo /sbin/chkconfig --add redis-server
sudo chkconfig --level 345 redis-server on
sudo useradd redis

chkconfig --list | grep redis

4 – Add these lines, including #, right after #!/bin/bash or #!/bin/sh:
# chkconfig: 2345 95 20
# description: Some description
# What your script does (not sure if this is necessary though)
# processname: redis-server

thrift -r --gen js:node tutorial.thrift


redis-cli KEYS "PREFIX*" | xargs redis-cli DEL

netstat -atp | grep -i "listen"  // linux

netstat -plnt | grep ':6379'

sudo lsof -n -i4TCP:9092 |grep -i listen
sudo lsof -i TCP:$PORT | grep LISTEN
sudo lsof -iTCP:$PORT -sTCP:LISTEN 
sudo lsof -i :80 # checks port 80
sudo lsof -i -P | grep -i "listen"


thrift -r --gen java  ServiceTest.thrift


node-gyp configure build

git reset --hard FETCH_HEAD

git reset HEAD srcfile

git diff -- '*.c' '*.h'

git diff --ignore-space-change 

You need to create a local branch that tracks a remote branch. The following command will create a local branch named daves_branch, tracking the remote branch origin/daves_branch. When you push your changes the remote branch will be updated.
git checkout --track origin/daves_branch

git push <remotename> <commit SHA>:<remotebranchname>
<!-- push local commit to remote branch -->
git push -f origin 83791dfaa0a02320225f5c4fd0e09634feb39712:master

git format-patch -1 <sha>

git apply patch

git am patch

git log -p filename

Merge: fc17405 ee2de56
take those two commit ids and reverse them. so in order get the diff that you want, you would do:
git diff ee2de56..fc17405

git diff --name-only ee2de56..fc17405

git stash show -p stash@{0}

git checkout stash@{0} -- <filename>

git diff --staged

git reset --hard 0d1d7fc32

<!-- for merge issue -->
git add lib/hello.html
git commit -m "Merged master fixed conflict."


git rm -r one-of-the-directories
git commit -m "Remove duplicated directory"
git push origin master


git pull
git add --all
git commit -m "fix some bug"
git push origin master

git checkout -b old-state 0d1d7fc32

get which remote br local br is tracking
git branch -vv
git branch -av


$ git remote add repo_b username@host:path/to/repository.git
$ git pull repo_b master

git checkout -b stable_branch c653e295d773fa4463f8a

git branch -d stable_branch

push local branch to remote rep
$ git checkout -b feature_branch_name
... edit files, add and commit ...
$ git push -u origin feature_branch_name

Step one, fetch master from the remote origin. The master branch on origin will be fetched and the local copy will be named origin/master.
git fetch origin master
Then you merge origin/master into master.
git merge origin/master

If your local changes are bad then just remove them or reset your local master to the state on remote
git reset --hard origin/master


sudo yum install npm


nc -u localhost 48772



cp -fr  GCC\ 4.2.xcplugin /Applications/Xcode.app/Contents/PlugIns/Xcode3Core.ideplugin/Contents/SharedSupport/Developer/Library/Xcode/Plug-ins


whereis libpthread.so
libpthread: /usr/lib64/libpthread.so



cat /etc/launchd.conf


The forall method takes a function p that returns a Boolean. The semantics of forall says: return true if for every x in the collection, p(x) is true.
So:
List(1,2,3).forall(x => x < 3)

Like every collection type in the scala.collection namespace a Map has the filter method defined and Optionhas the isDefined method, which is true for Some and false for None. You can filter out the Nonevalues by combining these two:

scala> map.filter(_._2.isDefined)


f you're filtering out None values, you might as well extract the Some values at the same time to end up with a Map[String,Int]:

scala> map.collect { case (key, Some(value)) => (key, value) }.toMap
res0: scala.collection.immutable.Map[String,Int] = Map(one -> 1, two -> 2)

list.map(i => i.key -> i.value).toMap


M-^ join line

SELECT UNIX_TIMESTAMP(datetime_field) as timestamp FROM table

mysqldump -u... -p... mydb t1 t2 t3 > mydb_tables.sql
mysql -hhostname -uuser database < path/to/test.sql
mysql> source '\home\user\Desktop\test.sql';

mysqldump -uroot new_project_config lnu_config > lnu_config.sql 
mysql -uroot new_project_config  < lnu_config.sql 

UPDATE mysql.user SET Password=PASSWORD('MyNewPass') WHERE User='root';
FLUSH PRIVILEGES;

mysqld_safe --init-file=/home/me/mysql-init &

lsof -nc mysqld | grep -vE '(\.so(\..*)?$|\.frm|\.MY?|\.ibd|ib_logfile|ibdata|TCP)'

SELECT CEILING(Total_InnoDB_Bytes*1.6/POWER(1024,3)) RIBPS FROM
(SELECT SUM(data_length+index_length) Total_InnoDB_Bytes
FROM information_schema.tables WHERE engine='InnoDB') A;

mysql中的skip-name-resolve

/usr/local/bin/mysql.server start|restart|stop

sudo /usr/local/mysql/bin/mysqld_safe

select load_file("/tmp/test.xml");


show variables like 'secure%';
sudo chmod 644 /tmp/test.xml 


use new_project_config;



KEY and INDEX are synonyms in MySQL. They mean the same thing. In databases you would use indexes to improve the speed of data retrieval. An index is typically created on columns used in JOIN, WHERE, and ORDER BY clauses.

Imagine you have a table called users and you want to search for all the users which have the last name 'Smith'. Without an index, the database would have to go through all the records of the table: this is slow, because the more records you have in your database, the more work it has to do to find the result. On the other hand, an index will help the database skip quickly to the relevant pages where the 'Smith' records are held. This is very similar to how we, humans, go through a phone book directory to find someone by the last name: We don't start searching through the directory from cover to cover, as long we inserted the information in some order that we can use to skip quickly to the 'S' pages.

Primary keys and unique keys are similar. A primary key is a column, or a combination of columns, that can uniquely identify a row. It is a special case of unique key. A table can have at most one primary key, but more than one unique key. When you specify a unique key on a column, no two distinct rows in a table can have the same value.

Also note that columns defined as primary keys or unique keys are automatically indexed in MySQL.


DELETE FROM new_project_config.lnu_config WHERE config_type="BasicBuffInfoConfig";


But in my case I wanted to do something more like flat map in this case, I want a map to come out that misses out the key 1 because it’s value is None. flatMap doesn’t work on maps like mapValues, it get’s passed the tuple and if it returns a List single items you’ll get a list back, but if you return a tuple you’ll get a Map back.

scala> m.flatMap(e => List(e._2))
res85: scala.collection.immutable.Iterable[Int] = List(2, 4, 6)

scala> m.flatMap(e => List(e))
res86: scala.collection.immutable.Map[Int,Int] = Map(1 -> 2, 2 -> 4, 3 -> 6)

scala> m.flatMap { case (k,v) => h(k,v) }
res108: scala.collection.immutable.Map[Int,Int] = Map(2 -> 4, 3 -> 6)

react instead of receive makes it possible to re-use threads, which is good for performance, since threads are expensive in the JVM.


each actor waiting on receive is occupying a thread.


val mixedList = List("a", 1, 2, "b", 19, 42.0) //this is a List[Any]
val results = mixedList collect {
  case s: String => "String:" + s
  case i: Int => "Int:" + i.toString
}
The argument to to collect method is a PartialFunction[Any,String].  PartialFunction because it's not defined for all possible inputs of type Any (that being the type of the List) and String because that's what all the clauses return.

If you tried to use map instead of collect, the the double value at the end of mixedList would cause a MatchError. Using collect just discards this, as well as any other value for which the PartialFunction is not defined.

One possible use would be to apply different logic to elements of the list:

var strings = List.empty[String]
var ints = List.empty[Int]
mixedList collect {
  case s: String => strings :+= s
  case i: Int => ints :+= i
}
Although this is just an example, using mutable variables like this is considered by many to be a war crime - So please don't do it!

A much better solution is to use collect twice:

val strings = mixedList collect { case s: String => s }
val ints = mixedList collect { case i: Int => i }
Or if you know for certain that the list only contains two types of values, you can use partition, which splits a collections into values depending on whether or not they match some predicate:

//if the list only contains Strings and Ints:
val (strings, ints) = mixedList partition { case s: String => true; case _ => false }
The catch here is that both strings and ints are of type List[Any], though you can easily coerce them back to something more typesafe (perhaps by using collect...)

If you already have a type-safe collection and want to split on some other property of the elements, then things are a bit easier for you:

val intList = List(2,7,9,1,6,5,8,2,4,6,2,9,8)
val (big,small) = intList partition (_ > 5)
//big and small are both now List[Int]s



val arr = Array("Hello","World")

Array.fill[Byte](5)(0)
List(0 to 100:_*)
(0 to 100).toList
List.range(0,100)


val (key, leftAttr) = cells.splitAt(2)

scala> val ns = <foo xmlns:id="bar" id:hi="fooMe"></foo>
ns: scala.xml.Elem = <foo id:hi="fooMe" xmlns:id="bar"></foo>

scala> ns \ "@{bar}hi"
res9: scala.xml.NodeSeq = fooMe


val system = ActorSystem()
val myActor = system.actorOf(Props[MyActor])
or, if your actor took constructor arguments:

val myActor = system.actorOf(Props(new MyActor("arg1"))
or, if you were in the body of another Actor,

val myActor = context.actorOf(Props(new Actor("arg1"))
and then your actor could immediately receive messages, e.g.

myActor ! MyMessage


An assignment expression has type Unit in Scala. That is the reason for your compiler warning.

There is a nice idiom in Scala that avoids the while loop:

val iterator = Iterator.continually(reader.readNext()).takeWhile(_ != null)
This gives you an iterator over whatever reader.readNext returns.

The continually method returns an "infinite" iterator and takeWhile takes the prefix of that, up to but not including the first null.

def askForName() = readLine("Name: ")

def askForNameAgain() = {
    println("Name was taken already. Try again.")
    askForName()
}

sudo yum install -y screen emacs

def inputNames = Stream.cons( askForName(), Stream.continually(askForNameAgain()))

val name = inputNames.find( !names.contains(_) )


 "org.jboss.netty" % "netty" % "3.2.0.Final"


mysqldump -uroot -h localhost new_project > new_project_dump.sql
mysql -uroot -h localhost lnu < new_project_dump.sql 

Create new database and rename all tables in the old database to be in the new database:

CREATE database new_db_name;
RENAME TABLE db_name.table1 TO new_db_name, db_name.table2 TO new_db_name;
DROP database db_name;
In Linux shell, use mysqldump to back up the old database, then restore the dumped daenter code heretabase under a new name using the MySQL utility. Finally, use the drop database command to drop the old database. This option can perform badly for large database.

mysqldump -uxxxx -pxxxx -h xxxx db_name > db_name_dump.sql
mysql -uxxxx -pxxxx -h xxxx -e "CREATE DATABASE new_db_name"
mysql -uxxxx -pxxxx -h xxxx new_db_name < db_name_dump.sql
mysql -uxxxx -pxxxx -h xxxx -e "DROP DATABASE db_name"

show databases;
show tables from tw_6_mars;
describe [dbname.]table_name

insert into `lnu`.`equipments_lnu` ( `id`, `item_id`, `player_id`, `lvl`) values ( '0', '3', '2', '11')


00  21-23/1  04  08  *  date >> test.log  2>&1


ssh-keygen -t rsa
ssh-copy-id -i ~/.ssh/id_rsa.pub root@203.69.109.230
ssh-copy-id -i ~/.ssh/id_rsa.pub chenying@58.215.165.113
xixun@12345
I chmod 755 on .. and now it's working. 

[c77cc@tw-game-server-11 ~]$ ls -la  .ssh/
total 24
drwxr-xr-x  2 c77cc c77cc 4096 Nov 18 14:27 .
drwx------. 6 c77cc c77cc 4096 Sep 23 22:55 ..  -> 755
-rw-------  1 c77cc c77cc  399 Nov 18 14:27 authorized_keys
-rw-------  1 c77cc c77cc 1675 Jun  9 22:26 id_rsa
-rw-r--r--  1 c77cc c77cc  397 Jun  9 22:26 id_rsa.pub
-rw-r--r--  1 c77cc c77cc  394 Jun  9 22:26 known_hosts


scp -rp sourcedirectory user@dest:/path

rsync -av /local/dir server:/remote/dir

rsync -azv ~/.screenrc root@172.16.3.43:~/;rsync -azv ~/.emacs* root@172.16.3.43:~/; rsync -azv ~/.emacs* root@172.16.3.43:~/; rsync -azv ~/emacs-lisp root@172.16.3.43:~/

steam;
fuzhou


iftop -i eth0

s: hide source
t: double direction
B: bar

cat /etc/password shows you all existing users.


grep -l
grep -m 10 

you can delete a remote branch using

git push origin --delete <branchName>

git remote -v

git show

git mergetools

git checkout --ours filename.c
git checkout --theirs filename.c
git add filename.c
git commit -m "using theirs"


git remote show origin

git remote add android  git@192.168.100.1:/var/git/mars.git
git pull android master
git remote show android


git clone git@git.dev.xixun.com:mars_api_project.git

For a specific file use:
git checkout path/to/file/to/revert

For all unstaged files use:
git checkout -- .

git log --stat

git show 9b9d1e321a95b75903d91b975e862f1a2675d1da
git log --pretty=oneline



[root@tw-db-server-21 ~]# mysql -h 172.16.3.21  -uxixun -p tw_1_mars -e 'select * from gem_depletion_history where created_at between 1407340800 and 1407427199 ' > gem_depletion_history.2014.8.7.log

symfony:
        1. framework
        2. mail
        3. doctrine
        4. monolog


export VENV=~/env
/usr/local/bin/virtualenv   $VENV
$VENV/bin/python helloworld.py

python setup.py install

$VENV/bin/pcreate -s starter MyProject
$VENV/bin/pcreate -s alchemy MyProject
$ cd MyProject
$ $VENV/bin/python setup.py develop

$VENV/bin/python setup.py test -q

$VENV/bin/pserve development.ini




sudo nginx -s stop && sudo nginx


mysql.server stop/start


pkill


egit install in eclpise
http://download.eclipse.org/egit/updates 


everest
注册码：FT9PHAIQ47XIFJXHI19FA1R1Y 或 H1LHI1U347R8FJ2LRFVFLMRD8


liup@123


real9ib8ju

-- check hardware info
dmidecode

lspci is a great utility for listing the system hardware. (Anything on the PCI bus, anyway.)
cat /proc/cpuinfo - Displays CPU info
cat /proc/meminfo - Displays memory info
dmesg (or cat /var/log/dmesg) contains some info, not necessarily everything.
If you have a RedHat/CentOS system, you can use sosreport to collect a good bit of information, though I don't know if it has all the hardware info listed in it.




ssh-keygen -R *ip_address_or_hostname*


with open("/etc/apt/sources.list", "r") as sources:
    lines = sources.readlines()
with open("/etc/apt/sources.list", "w") as sources:
    for line in lines:
        sources.write(re.sub(r'^# deb', 'deb', line))
The with statement ensures that the file is closed correctly, and re-opening the file in "w" mode empties the file before you write to it. re.sub(pattern, replace, string) is the equivalent of s/pattern/replace/ in sed/perl.


cat /etc/redhat-release 


tar -zcvf - navicat101_premium_en_for_mac | split -b 10240k - navicat101_premium_en_for_mac.tar.gz

cat navicat101_premium_en_for_mac.tar.gz.* | tar -zxv


du --block-size=MiB --max-depth=1 | sort -n


screen -ls
screen -r 
screen -X -S [session # you want to kill] quit
screen -d -r

Sync the system clock to the current time:
# ntpd -g -q
Check that the time appears correct:
# date
Sync the server's hardware clock to the system clock:
# hwclock -wu

sudo ntpdate pool.ntp.org

find /your/dir -type f -exec touch {} +

yum remove 'php*'
yum remove 'MySQL*'

yum list installed |grep -i mysql

yum install vixie-cron or yum install cronie
service crond start
chkconfig crond on



DigitalColor Meter APP


find .emacs.d/ -name "*.elc" -type f -delete

ALTER TABLE some_table AUTO_INCREMENT = 0


Follow steps below

1.Start the mysql server instance or daemon with the --skip-grant-tables option. (security setting)
<!-- /etc/init.d/mysql stop -->
$ mysqld --skip-grant-tables

2.Then Execute these statements.
$ mysql -u root mysql
$mysql> UPDATE user SET Password=PASSWORD('jit2ces3be2') where USER='root';
$mysql> FLUSH PRIVILEGES;

3.Finally, restart the instance/daemon without the --skip-grant-tables option.
$ /etc/init.d/mysql restart

4.You should be able to connect with your new password.
$ mysql -u root -p


Type the following two commands (you must login as the root user):
# /etc/init.d/iptables save
# /etc/init.d/iptables stop

Turn off firewall on boot:
# chkconfig iptables off


Type the following command to turn on iptables firewall:
# /etc/init.d/iptables start

Turn on firewall on boot:
# chkconfig iptables on


iptables -A INPUT -s 172.16.3.0/24 -j ACCEPT

Open port XY

Open flle /etc/sysconfig/iptables:

# vi /etc/sysconfig/iptables

Append rule as follows: <!-- for redis -->

-A RH-Firewall-1-INPUT -m state --state NEW -m tcp -p tcp --dport 6379 -j ACCEPT

 
Save and close the file. Restart iptables:

# /etc/init.d/iptables restart

Verify that port is open

Run following command:

# netstat -tulpn | less

Make sure iptables is allowing port connections:

# iptables -L -n



Normally information like this will be found in one of the following places in OS X:

/Users/username/Library/Preferences/AppName
/Users/username/Library/Preferences/com.appname.plist
/Users/username/Library/Application Support/AppName
/Library/Preferences/AppName
/Library/Preferences/com.appname.plist
/Library/Application Support/AppName
If the app adheres to the standard OS X conventions you weill find info in one or all of these places. If it doesnt store here you might check for a /Users/username/.intellij folder or something similar in your home directory


nl file| more


bjchenys-Mac-mini:Unity bjcheny$ pwd
/Library/Application Support/Unity
bjchenys-Mac-mini:Unity bjcheny$ ls
Unity_v4.x.ulf

bjchenys-Mac-mini:Contents bjcheny$ find . -iname unity -type f -exec ls -lh {} \;
-rwxr-xr-x  1 bjcheny  admin    40M Oct 11  2013 ./MacOS/Unity
bjchenys-Mac-mini:Contents bjcheny$ pwd
/Applications/Unity4.2.2/Unity.app/Contents




def listAnalysis(list: List[Any]) = list match {
   case Nil => "empty"
   case 'a' :: tail => "starting by 'a'"
   case (head:Int) :: _ if head > 3 => "starting by an int greater than 3"
   case (head:Int) :: _ => "starting by an int"
   case _ => "whatever"
   }

du -ch | grep total

In my case, I didn't want to keep the files, so this worked for me:
git clean  -d  -fx ""


If your excess commits are only visible to you, you can just do git reset --hard origin/master to move back to where the origin is.
Doing a git revert makes new commits to remove old commits in a way that keeps everyone's history sane.


add sth in cs code to compile again


sestatus # selinux status



Here are exact steps to follow:

1. You need to install PHP’s devel package for PHP commands execution
yum install php-devel
Make sure you also have php-paer package installed
yum install php-pear

2. Next install GCC and GCC C++ compilers to compile Xdebug extension yourself.
yum install gcc gcc-c++ autoconf automake

3. Compile Xdebug
pecl install Xdebug

4. Find the php.ini file using
locate php.ini

And add the following line

[xdebug]
zend_extension="/usr/lib64/php/modules/xdebug.so"
xdebug.remote_enable = 1

5. Restart Apache
service httpd restart

6. Test if it works – create test.php with the following code

<?php phpinfo() ?>
and check if you have the following output



val a = collection.mutable.Map(1->"one",2->"two",3->"three")
a: scala.collection.mutable.Map[Int,java.lang.String] = 
  Map(2 -> two, 1 -> one, 3 -> three)

scala> a.retain((k,v) => v.length < 4)  




class AClass(aVal: String)
In this code, aVal is a final variable. So You already have a final variable.

class AClass(val aVal: String)
In this code, aVal is final and you have getter of aVAl. So you can use it like below

scala> val a= new AClass("aa")
a: A1 = A1@1d7d58f

scala> a.aVal
res2: String = aa
And finally,

class AClass(var aVal: String)
In this code, aVal is not final and you have getter and setter of aVal. 


ls $(brew --prefix)/Library/Formula 


select * from base_questions where question like "%感冒%"

wget http://scalasbt.artifactoryonline.com/scalasbt/sbt-native-packages/org/scala-sbt/sbt//0.13.0/sbt.rpm
yum localinstall sbt.rpm 

sbt update
sbt start-script
sbt run


yum search java | grep 'java-'
java-1.7.0-openjdk-devel.x86_64


wget http://www.scala-lang.org/files/archive/scala-2.10.1.tgz
tar xvf scala-2.10.1.tgz
sudo mv scala-2.10.1 /usr/lib
sudo ln -s /usr/lib/scala-2.10.1 /usr/lib/scala
export PATH=$PATH:/usr/lib/scala/bin
scala -version



To use it, use the bundled emacs21 to create a text file in /etc/yum.repos.d/puias-unsupported.repo .
It should have these contents:

[puias-unsupported]
name=PUIAS Unsupported $releasever
baseurl=http://puias.princeton.edu/data/puias/unsupported/5/$basearch/
enabled=0
gpgcheck=0

Then, use it like this:

sudo yum --disablerepo="*" --enablerepo=puias-unsupported install emacs23

The RPMs are:

emacs23-23.2-5.x86_64.rpm
emacs23-common-23.2-5.x86_64.rpm
If you install it this way, it will be placed into /usr/emacs23/ . It does not replace the existing emacs21.
There is also a nox version of emacs23 in that repo. And a bunch of other stuff.
Additionally, to make it work correctly and prevent warnings, I did the following:

cd /usr/share/emacs/
ln -s /usr/emacs23/share/emacs/23.2
mkdir 23.2/leim
mkdir -p /usr/libexec/emacs/23.2/x86_64-redhat-linux-gnu



# su -
# yum install -y gcc make ncurses-devel giflib-devel libjpeg-devel libtiff-devel
# cd /usr/local/src
# wget http://ftp.gnu.org/pub/gnu/emacs/emacs-24.3.tar.gz
# tar xzvf emacs-24.3.tar.gz
# cd emacs-24.3
# ./configure --without-x --without-selinux
# make && make install
# which emacs
/usr/local/bin/emacs
# emacs --version
GNU Emacs 24.3.1


/etc/init.d/yum-updatesd stop
chkconfig --level 2345 yum-updatesd off


-Xms
　　设置Java堆的初始化大小。例如 -Xms1024m,Java堆的初始化大小就设置为1G.
-Xmx
　　设置Java堆的最大值。例如 -Xmx3072m,Java堆的最大值就设置为3G.
-Xss
　　设置Java线程栈的值。例如 -Xss128m,Java线程栈的值就设置为128兆。

-XX:PermSize<=size>和-XX:MaxPermSize<=size>
　　设置Java永久保存区域（Permanent Generation Space）的大小。PermSize设置初始值，MaxPermSize设置最大值。 该区域主要存储class的信息，且不会被 垃圾回收器回收，如果加载的class过多，就会报错：java.lang.OutOfMemoryError: PermGen space. -XX:PermSize=64m -XX:MaxPermSize=128m,表示Java永久保存区域大小初始化问为64兆，最大为128兆。



[root@Mars-Gateway scrooge]# ./sbt 'scrooge-generator/run-main com.twitter.scrooge.Main XEquipment.thrift '
[info] Loading project definition from /root/scrooge/project
Missing bintray credentials /root/.bintray/.credentials. Some bintray features depend on this.
[info] Set current project to scrooge (in build file:/root/scrooge/)
[info] Running com.twitter.scrooge.Main XEquipment.thrift   
[success] Total time: 2 s, completed Sep 30, 2014 8:24:37 PM
[root@Mars-Gateway scrooge]# 


grep sshd /var/log/audit/audit.log  


<!-- in qingyun cloud -->
PasswordAuthentication yes



JRebel Evaluation activation code
rO0ABXNyAChjb20uemVyb3R1cm5hcm91bmQubGljZW5zaW5nLlVzZXJMaWNlbnNlAAAAAAAAAAECAANMAAdkYXRhTWFwdAAPTGphdmEvdXRpbC9NYXA7WwAHbGljZW5zZXQAAltCWwAJc2lnbmF0dXJlcQB+AAJ4cHB1cgACW0Ks8xf4BghU4AIAAHhwAAACY6ztAAVzcgARamF2YS51dGlsLkhhc2hNYXAFB9rBwxZg0QMAAkYACmxvYWRGYWN0b3JJAAl0aHJlc2hvbGR4cD9AAAAAAAAYdwgAAAAgAAAAFHQAA3VpZHQAKGJjNmJjNDZkNTkyMDM0MmI4YjAwMzdhOGUzNmMwZDMzYThjMzE0OTB0AAhsYXN0TmFtZXQABGNoZW50AAtHZW5lcmF0ZWRCeXQABEFVVE90AAVTZWF0c3QAATF0AAdQcm9kdWN0dAAGSlJlYmVsdAAEVHlwZXQACmV2YWx1YXRpb250AAdPcmRlcklkdAAAdAAMT3JnYW5pemF0aW9udAAFWGl4dW50AAplbnRlcnByaXNldAAEdHJ1ZXQACnZhbGlkVW50aWxzcgAOamF2YS51dGlsLkRhdGVoaoEBS1l0GQMAAHhwdwgAAAFQSzh5ZHh0AAd2ZXJzaW9udAADMS43dAAETmFtZXQACXlpbmcgY2hlbnQAC0dlbmVyYXRlZE9uc3EAfgAVdwgAAAFI84dNZHh0AAl2YWxpZERheXNzcgARamF2YS5sYW5nLkludGVnZXIS4qCk94GHOAIAAUkABXZhbHVleHIAEGphdmEubGFuZy5OdW1iZXKGrJUdC5TgiwIAAHhwAAAADnQABUVtYWlsdAATY29tcGFueWN5QGdtYWlsLmNvbXQAC2xpbWl0ZWRGcm9tcQB+ABx0AAhvdmVycmlkZXQABWZhbHNldAAJdmFsaWRGcm9tcQB+ABx0AAlmaXJzdE5hbWV0AAR5aW5ndAAMbGltaXRlZFVudGlscQB+ABZ4dXEAfgAEAAABAHLcC19vfuSlj9xLbWb5mJ5nnfibj+xgjdWwZlOW4Z4aE/Xgr3SQi/n75Ta3H4gEu75sKbzXEXTSvyDgJr4Utsjb74Vs8nCZHEeBA4TqCkDwHQMInf5hHrrrcObH3ia0F2vs/uiFaTLmtGJMlbfIEes7FTCYwpAugtzUA5JN9WhQg+i0U8GxXgLtw+cvzbhJ7JgfAU6wevRvEx51cS4q2lfGy4FWS4B84i8GVbtBX7qp5dCUMLh9FAnX/X6U2Gc+oCIeY0Epyt4OByW4I6S8sUYABH138IvM+PWGB77lWXF6pDLwIWeZvOM8Na4GWCMu717kzHF0D60UPcsvrHHszBw=



[c77cc@tw-staging-game-101 api.mars.staging_tw_1.xixun.com]$ curl -sS https://getcomposer.org/installer | php
#!/usr/bin/env php
All settings correct for using Composer
Downloading...

Composer successfully installed to: /var/www/vhosts/api.mars.staging_tw_1.xixun.com/composer.phar
Use it: php composer.phar
[c77cc@tw-staging-game-101 api.mars.staging_tw_1.xixun.com]$ mkdir -p ~/.composer/vendor/bin/
[c77cc@tw-staging-game-101 api.mars.staging_tw_1.xixun.com]$ php composer.phar global require "phpunit/phpunit=4.1.*"


phpunit  -c app  src/Xixun/ApiBundle/Tests/Controller/SpriteControllerTest.php


yum install -y MySQL-python


sudo easy_install redis


find . -type f -size +500M -exec ls -lh {} \;


python setup.py install

yum install -y python-setuptools


[root@game-server-95 api.mars.app_store_15.xixun.com]# pear install channel://pear.php.net/Console_ProgressBar-0.5.2beta
downloading Console_ProgressBar-0.5.2beta.tgz ...
Starting to download Console_ProgressBar-0.5.2beta.tgz (6,541 bytes)
.....done: 6,541 bytes
install ok: channel://pear.php.net/Console_ProgressBar-0.5.2beta
[root@game-server-95 api.mars.app_store_15.xixun.com]#


<!-- about epel -->
sed -i 's/(mirrorlist=http)s/\1/' /etc/yum.repos.d/epel.repo


Instrumentation 的最大作用，就是类定义动态改变和操作。


[c77cc@android-game-server-86 ~]$ ls -la .ssh/
total 24
drwx------ 2 c77cc c77cc 4096 Oct 29 14:46 .
drwx------ 6 c77cc c77cc 4096 Oct 29 14:47 ..
-rw------- 1 c77cc c77cc 1600 Oct 29 14:59 authorized_keys
-rw------- 1 c77cc c77cc 1675 Sep 21  2013 id_rsa
-rw-r--r-- 1 c77cc c77cc  402 Sep 21  2013 id_rsa.pub
-rw-r--r-- 1 c77cc c77cc  791 Sep 23  2013 known_hosts


M-x recover-session.



mysqldump -uroot -pdbpasswd -d dbname test>db.sql;


rpm2cpio xxx.rpm | cpio -div



#Add typesafe repository     
wget http://apt.typesafe.com/repo-deb-build-0002.deb `

#Install the repository
sudo dpkg -i repo-deb-build-0002.deb

#Refresh
sudo apt-get update

#Install sbt
sudo apt-get install sbt

#check whether sbt is installed
sbt


Type: C-x C-k n title-case-macro

Ctrl+x Ctrl+k n indicates name the previous macro
When you do Ctrl+x Ctrl+k n, it will ask ‘Name for last kbd macro:’
(enter the name you require). I am naming it as title-case-macro.

m-x title-case-macro

m-x gud-break

m-x toggle-case-fold-search

** ntp
cp -f /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
yum -y install ntp
ntpdate  cn.pool.ntp.org
service ntpd start
chkconfig ntpd on

** build debug
./configure --CXXFLAGS="-g "

CFLAGS=-g CPPFLAGS=-g  ./configure 

** view session log from msi
msiexec /i Sample.msi /l*v Sample.msi.log



dhclient eth0
/usr/sbin/visudo
bjcheny ALL=(ALL:ALL) ALL

<!-- check 32bit or 64bit -->
uname -r


psql -d template1 -U postgres
CREATE DATABASE test;
CREATE USER bjcheny WITH PASSWORD 'passw0rd';
GRANT ALL PRIVILEGES ON DATABASE test to bjcheny;
su - bjcheny
psql -d test -U bjcheny

pg_dump -t my_user |psql test
alter table my_user owner to bjcheny;

yum install -y gcc bison-devel readline-devel zlib-devel openssl-devel wget && yum groupinstall -y 'Development Tools'

yum install mysql-connector-odbc
yum install unixODBC unixODBC-devel libtool-ltdl libtool-ltdl-devel
/etc/odbcinst.ini
<!-- no localhost in odbcinst.ini -->
odbcinst -q -d

mysql>INSERT INTO user (host, user, password, select_priv, insert_priv, update_priv) VALUES ('localhost', 'bjcheny', PASSWORD('passw0rd'), 'Y', 'Y', 'Y');
mysql>use mysql;
mysql>update user set host = '%' where user = bjcheny;
mysql>select host, user from user;
mysql>flush privileges;


yum install zlib-devel



Create a file called /etc/ld.so.conf.d/myapp.conf:
# vi /etc/ld.so.conf.d/myapp.conf
Add the following path:
/usr/local/lib
# ldconfig
# ldconfig -p | grep /usr/local/lib


How Do I Compile Program With Shared Libs And GNU GCC?
You can use the following gcc
$ gcc -Wl,-R/path/to/lib -I/path/to/include -L/path/to/lib -o myAppName mycode.c -llibapp2


export CPPFLAGS='-I/home/foo/sw/include'
export LDFLAGS='-L/home/foo/sw/lib/'
./configure


psql -h myhost -d mydb -U myuser

echo "select 1" | isql -v admin-connector


the correct odbc.ini entry is

[MSQL2005]
Driver  = ODBC Driver 11 for SQL Server
Description = Microsoft SQL ODBC Driver
Server  = your_mssql_server_host
Port  = 1433
Database =
[POSTGRESQL9] Driver  = PostgreSQL9 Driver
Description = Postgresql ODBC Driver
Servername = your_postgresql_server_host
Port  = 5432
Database = your_database




# To enable unixODBC tracing, add this section to odbcinst.ini.
# Include the [ODBC] section heading.
[ODBC]
Trace = yes
TraceFile = trace_file_path


Unicode
Driver={PostgreSQL UNICODE};Server=IP
address;Port=5432;Database=myDataBase;
Uid=myUsername;Pwd=myPassword;

ldconfig -p

xz -d 


\list lists all databases
\dt lists all tables in the current database

CREATE TABLE distributors (
did    integer PRIMARY KEY DEFAULT nextval('serial'),
name   varchar(40) NOT NULL CHECK (name <> '')
);

INSERT INTO films VALUES
    ('UA502', 'Bananas', 105, '1971-07-13', 'Comedy', '82 minutes')

\d+ tablename

/etc/init.d/postgresql restart

In your data/postgresql.conf file, change the log_statement setting to 'all'.


make config-recursive && make install clean
echo 'export BATCH=yes' >> ~/.bash_profile

make all-depends-list
That will recurse through all dependencies and print them for you. To
test different build scenarios and how they affect the dependency
list, try things like:

make NOPORTDOCS=yes NOPORTEXAMPLES=yes all-depends-list

make WITHOUT_X11=yes all-depends-list
Here is the full set of dependency print targets:

all-depends-list
build-depends-list
run-depends-list
package-depends-list
pretty-print-build-depends-list
pretty-print-run-depends-list


make config


set args a b c



dumpbin /exports dll

msiexec.exe /a c:\msi\installer.msi /qb targetdir=d:\msi\installer


ERP5 is an open source ERP based on Python and Zope.
OpenERP python
ADempiere ERP Business Suite Java
Compiere Java/Swing
OFBiz Java
JFire Java
OpenTaps Python

www.acclib.com
Manager


JB74G-FC8KR-B66C2-V82YF-Q3GBB 有效 XXXXX-640-4061082-45801 

<!-- vs2010 -->
YCFHQ-9DWCY-DKV88-T2TMH-G7BHP
"C:\Program Files (x86)\Microsoft Visual Studio 10.0\DIA SDK"





In VS add a breakpoint and specify the location as, for example
{,,sqloledb.dll}DllMain

Visual Basic considers a Fortran(cpp?) DLL as "Unmanaged code".  By default,
a VB project will NOT debug unmanaged code.  The user must enable this feature.


clang++ -std=c++11 main.cpp

clang main.c


sudo yum install mingw32-gcc-c++

tar -Jxvf **.tar.xz

sudo yum install -y qt-devel.x86_64

for socket lib on win: ws2_32.lib


783751
860101C

gpedit.msc


select pg_backend_pid();
Use a debugger to attach to the postgres
PID - gdb -p 1234 or, within a running gdb, attach 1234.


create table distributors(did integer PRIMARY KEY, name varchar(40));
drop table distributors;


p (Node*)((List)(*(Node*)((SelectStmt)(*((InsertStmt*)parsetree).selectStmt)).valuesLists.head.data.ptr_value)).head.data.ptr_value



create table jbxx(rybh integer PRIMARY KEY, sfzh varchar(40));
insert into jbxx values(102101, '440234198012091109');
insert into jbxx values(103101, '110234198111192104');
insert into jbxx values(104101, '331464199002095667');

create table rxzp(rybh  integer PRIMARY KEY, writetime varchar(40), CONSTRAINT rybh_1 FOREIGN KEY (rybh) REFERENCES jbxx (rybh));

drop table rxzp;

create table my_user(uid  integer PRIMARY KEY, uname varchar(16));
create table my_order(oid int, oname varchar(16), uid int, constraint uid_1 foreign key (uid) references my_user(uid));


gdb -tui

tbreak: Break once, and then remove the breakpoint

info locals: View all local variables

./configure CFLAGS="-O0 -g"
 ./configure CFLAGS="-O0 -g -std=c99" --enable-debug --enable-cassert
 --without-readline --without-zlib

select jbxx.sfzh, rxzp.writetime from jbxx full join rxzp on jbxx.rybh=rxzp.rybh;


fastgetattr
heap_getattr



single: types table?


delete middle column

drop table my_user_uid;

sudo du -sh /usr/local/pgsql/data/base


sudo apt-get install build-essential libreadline-dev zlib1g-dev flex bison libxml2-dev libxslt-dev libssl-dev


dmesg | egrep -i -B100 'killed process'



C-x <RET> f then enter unix or undecided-unix 



go get github.com/lib/pq
go build myrand.go


rpm -ivh http://ftp.riken.jp/Linux/fedora/epel/6/i386/epel-release-6-8.noarch.rpm
yum install -y golang
[golang@localhost ~]$ go run hello.go




rpm -Uvh
http://dl.fedoraproject.org/pub/epel/6/x86_64/epel-release-6-8.noarch.rpm
yum install golang


yum install docbook-style-dsssl -y



uim: universal information model


:%s/\t/AAA/g



yum localinstall package 从本机目录安装软件包
yum groupinstall group 安装某个组件的全部软件包

yum update package
yum check-update 列出所有可更新的软件包
yum list updates mysql* 查找mysql的更新
yum update 更新所有可更新的软件包
yum update mysql* 更新所有mysql的软件包
yum groupupdate group 更新某个组件的所有软件包
yum list 列出所有已安装和仓库中可用的软件包
yum list available 列出仓库中所有可用的软件包
yum list updates 列出仓库中比当前系统更新的软件包
yum list installed 列出已安装的软件包
yum list recent 列出新加入仓库的软件包
yum info 查询软件包信息

yum remove package
yum groupremove group 删除某个组件的全部软件包

yum clean packages 清除遗留在缓存里的包文件
yum clean metadata 清除遗留在缓存里的元数据
yum clean headers 清除遗留在缓存里的头文件
yum clean all 清除包文件，元数据，头文件

yum search package
yum info package 查找一个软件包的信息
yum list package 列出包含指定信息的软件包
yum list installed 列出已安装的软件包
yum list extras 列出不是通过软件仓库安装的软件包
yum list *ttp* 列出标题包含ttp的软件包
yum list updates 列出可以更新的软件包



$ echo aaa > a.txt
$ echo bbb > b.txt
$ echo ccc > c.txt

$ tar cvf x.tar *txt
a.txt
b.txt
c.txt

$ echo BBB > b.txt

$ tar -uvf x.tar b.txt
b.txt

$ tar tvf x.tar
-rw-rw-r-- ian/ian           4 2012-11-08 16:43:10 a.txt
-rw-rw-r-- ian/ian           4 2012-11-08 16:43:17 b.txt
-rw-rw-r-- ian/ian           4 2012-11-08 16:43:26 c.txt
-rw-rw-r-- ian/ian           4 2012-11-08 16:48:22 b.txt


tar --append --file=collection.tar rock

tar --delete -f vlc-2.1.5.20150330.allinone.tar 'vlc-2.1.5/contrib/win32/i686-w64-mingw32'

tar --update --file=collection.tar rock



tar --delete -f foo.tar 'etc/security'
tar -tvf foo.tar | grep 'etc/security'


Makefile:
http://nuclear.mutantstargoat.com/articles/make/

sudo apt-get install python-software-properties
sudo add-apt-repository ppa:webupd8team/java
sudo apt-get update
sudo apt-get install oracle-java7-installer

用户： share
密钥：78689-AFOCD-P3SDN-83DEC-BQ3UC-V6UK7

sudo yum install -y java-1.7.0-openjdk-devel

http://4554480.blog.51cto.com/4544480/1254275
sudo yum install -y tomcat6 tomcat6-webapps tomcat6-admin-webapps tomcat6-docs-webapp tomcat6-javadoc mysql-server


$ vagrant box add play url
$ vagrant init  # 初始化
$ vagrant up  # 启动虚拟机
$ vagrant halt  # 关闭虚拟机
$ vagrant reload  # 重启虚拟机
$ vagrant ssh  # SSH 至虚拟机
$ vagrant status  # 查看虚拟机运行状态
$ vagrant destroy  # 销毁当前虚拟机


http://www.scriptrock.com/articles/docker-vs-vagrant



license for vs2010 express:
6VPJ7-H3CXH-HBTPT-X4T74-3YVY7
PQT8W-68YB2-MPY6C-9JV9X-42WJV


-std=c++11


sudo groupadd docker



sudo yum install postgresql-libs  -y




$ C_INCLUDE_PATH=/opt/gdbm-1.8.3/include
$ export C_INCLUDE_PATH

$ CPLUS_INCLUDE_PATH=/opt/gdbm-1.8.3/include
$ export CPLUS_INCLUDE_PATH

$ LIBRARY_PATH=/opt/gdbm-1.8.3/lib
$ export LIBRARY_PATH

cd /etc/yum.repos.d
wget http://people.centos.org/tru/devtools-1.1/devtools-1.1.repo
yum --enablerepo=testing-1.1-devtools-6 install devtoolset-1.1-gcc devtoolset-1.1-gcc-c++

export CC=/opt/centos/devtoolset-1.1/root/usr/bin/gcc
export CPP=/opt/centos/devtoolset-1.1/root/usr/bin/cpp
export CXX=/opt/centos/devtoolset-1.1/root/usr/bin/c++


/cygdrive/c/Users/bjcheny/.vagrant.d/tmp

psql connect to coordinator

CREATE INDEX index_name ON table_name (column_name)

readline-devel zlib-devel flex bison jade  docbook-style-dsssl

service iptables status


=hx

select * from act, patient where act.pid=patient.pid;


VS2010 CDKEY:YCFHQ9DWCYDKV88T2TMHG7BHP


svn chenying:123456

.inputrc:
set completion-ignore-case on
