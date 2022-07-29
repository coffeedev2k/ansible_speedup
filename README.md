

target article
https://habr.com/ru/company/d2cio/blog/343368/

# ansible_speedup


test run

ansible-playbook test.yml -i hosts.ini


measuring run 1 - simple

./time_test.sh ansible-playbook test.yml -i hosts.ini

        Samples:        10
        Mean Avg:       13.830

real 15.00
real 14.30
real 13.79
real 14.19
real 13.19
real 13.36
real 13.38
real 13.18
real 13.37
real 14.54

measuring run 2 - with SSH multiplexing

        Samples:        10
        Mean Avg:       14.789

real 15.88
real 13.93
real 14.86
real 15.44
real 13.82
real 14.93
real 15.77
real 14.12
real 13.97
real 15.17



measuring run 3 - with SSH multiplexing + Pipelining 

        Samples:        10
        Mean Avg:       7.3120

real 8.90
real 7.60
real 7.39
real 7.21
real 7.06
real 7.04
real 7.00
real 7.09
real 6.82
real 7.01


measuring run 4 - with SSH multiplexing + Pipelining + PreferredAuthentications и UseDNS

        Samples:        10
        Mean Avg:       7.0660

real 8.64
real 7.09
real 7.11
real 6.83
real 7.04
real 6.78
real 6.72
real 6.65
real 6.82
real 6.98

measuring run 5 - with SSH multiplexing + Pipelining + PreferredAuthentications и UseDNS without gathering facts

        Samples:        10
        Mean Avg:       5.4530

real 6.90
real 5.30
real 5.29
real 5.35
real 5.40
real 5.18
real 5.26
real 5.33
real 5.21
real 5.31


measuring run 6 our work config

        Samples:        10
        Mean Avg:       7.2970

real 8.34
real 7.42
real 7.46
real 7.45
real 7.14
real 6.97
real 7.02
real 6.96
real 7.20
real 7.01

