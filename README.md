# test-cps-certificate

## Usage

~~~
% ./test-cps-certificate -h
Usage: ./test-cps-certificate [options] CN...

Available options:
    -t, --test                       Search and fetch certificates from the TEST directory
    -g, --gn=GIVEN_NAME              Filter on given name
    -s, --sn=SURNAME                 Filter on surname
~~~

## Examples

Check a bunch of TEST CPS:
~~~
% ./test-cps-certificate -t 00B2127377 00B1058698 00B1058706 500000000021550/CPAT0001
[ FAIL ] NI MI2737 (certificate signature failure)
[  OK  ] KIT DOC5869 
[ FAIL ] MUMUMUMUMUMUMUMUMUMUMUMUMUM MAXIMAXIMAXIMAXIMAXIMAX5870 (certificate signature failure)
[  OK  ] CHARLES RESPONSABLE0000021550001 
2 successes, 2 failures (50% success rate)
~~~

Check the CPS of a Health Profesional:

~~~
% ./test-cps-certificate -g MARIE-PIERRE -s BERNARD
[ FAIL ] MARIE-PIERRE BERNARD (certificate signature failure)
[  OK  ] MARIE-PIERRE BERNARD 
1 successes, 1 failures (50% success rate)
~~~
