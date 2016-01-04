
# refer to http://askubuntu.com/questions/107008/how-to-speed-up-compilation-of-ubuntu-apps-make-cmake-gcc

1. apt-get install distcc on all nodes
2. vi /etc/default/distcc on all nodes

STARTDISTCC="true"

ALLOWEDNETS="192.168.128.0/24"

# LISTENER="127.0.0.1"

NICE="10"

JOBS="10"

ZEROCONF="false"

3. assume compiler node is: 192.168.128.3
   helper nodes are: 192.168.128.4/5/6
   ssh helper_node "service distcc start"

4. export PATH="/usr/lib/distcc:$PATH"
   export DISTCC_HOSTS='192.168.128.4  192.168.128.5 192.168.128.6'
   distcc --show-hosts

# you can add localhost to hosts as you wish like below
   export DISTCC_HOSTS='localhost 192.168.128.4  192.168.128.5 192.168.128.6'


5. on compiler: distccmon-text 2
   on helper_nodes: tail -f /var/log/distccd.log

6. use Makefile on project, take pitrix-common for example:

APIOBJS=api/base_api.so api/constants.so api/error_msg.so api/common.so api/error_code.so api/error.so api/return_tools.so

OBJS=$(APIOBJS)

.SUFFIXES: .c .so .py

%.c : %.py
        cython -D -2 --embed $<

%.so : %.c
        $(CC) -shared -pthread -fPIC -fwrapv -O2 -Wall -fno-strict-aliasing -I/usr/include/python2.7 -c $< -o $@

all: $(APIOBJS)

7. make -j$(distcc -j)

# one more thing: -c is necessary to use distcc, refer to dcc_scan_args() in arg.c

    if (!seen_opt_c && !seen_opt_s) {
        rs_log_info("compiler apparently called not for compile");
        return EXIT_DISTCC_FAILED;
    }

