---
layout: default
---
# Argparse

[Official Documentation](https://docs.python.org/3/library/argparse.html)

```python
parser = argparse.ArgumentParser()
parser.add_argument('file', help='Explanations')
parser.add_argument('files', nargs='*') # Collect 0+ arguments in list
parser.add_argument('files', nargs='+') # Collect 1+ arguments in list
parser.add_argument('-n', '--count', default=1, type=int)
parser.add_argument('--required', required=True))
parser.add_argument('--date', type=parse_date) # type can be set to arbitrary unary function
parser.add_argument('--order', choices=['ascending', 'descending'], default='ascending')
parser.add_argument('--position', nargs=2, metavar=('x', 'y'))
parser.add_argument('-x', dest='better_varname')
parser.add_argument('--flag', action='store_true') # Default false
parser.add_argument('--flag', action='store_false') # Default true
parser.add_argument('--flag', action='store_const', const='5', dest='var') # Stores 5 in var
parser.add_argument('-v', action='count', dest='verbosity_level') # -vvv causes verbosity_level=3
parser.set_defaults(x=1, y=2, z=3)

args = parser.parse_args()
```

## Commands

```python
parser = argparse.ArgumentParser()
parser.set_defaults(func=lambda args: parser.print_help()) # Missing command -> print help
subparsers = parser.add_subparsers(help='sub-command help')

subparser = subparsers.add_parser('command1', help='explanations about command1')
subparser.add_argument(...)
subparser.set_defaults(func=command1) # function command1 will be stored

args = parser.parse_args()
args.func(args)
```
