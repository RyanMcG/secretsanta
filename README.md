# secretsanta

The internet is a cold dark place with only terrible secret santa generators.

This is a standalone python script that takes a file or reads from standard
input a list of names and prints to standard output same names in the same
order but as santa assignments:

## Usage

Pipe into standard input:

```
echo 'Bob\nSally\nMandip' | ./secretsanta
Sally
Mandip
Bob
```

Or read from a file:

```
echo 'Bob\nSally\nMandip' > children.txt
./secretsanta children.txt > santas.txt
```

### Examples

#### ab
With just `a` and `b` the only possible output is `ba`:

```
echo 'a\nb' | ./secretsanta
b
a
```
This means `a` (which is the first line of the input) should be assigned to `b`
(the first line of the output).

#### abc
With just `a`, `b` and `c` you might get `bca` or `cab`:

```
echo 'a\nb\nc' | ./secretsanta
b
c
a
```

Or maybe...

```
echo 'a\nb\nc' | ./secretsanta
c
a
b
```
