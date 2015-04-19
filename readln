#!/usr/bin/env python3

# Reads a line or lines from a file and prints them to standard output
# Copyright 2015 Theseas Maroulis

# This program is free software: you can redistribute it and/or modify
# it under the terms of the GNU General Public License as published by
# the Free Software Foundation, either version 3 of the License, or
# (at your option) any later version.

# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.

# You should have received a copy of the GNU General Public License
# along with this program.  If not, see <http://www.gnu.org/licenses/>.

import sys

def get_range(_range):
    start = 0
    end = 0
    status = 0
    if _range.find('..')!=-1:
        l = _range.split('..')
        try:
            start = int(l[0])
            end = int(l[1])
        except ValueError:
            print("Invalid range values!\nCorrect format is STARTLINE..ENDLINE")
            status = 2
    else:
        try:
            start = end = int(_range)
        except ValueError:
            print("Invalid range values!\nCorrect format is STARTLINE..ENDLINE")
            status = 2
    return (start, end, status)

def print_lines(start, end, _file):
    i=1
    line='.'
    while line!='' and i<=end:
        line=_file.readline()
        if i>=start:
            print(line, end='')
        i += 1
    return 0;

if __name__=='__main__':
    f = None;
    status = 0
    start = 0;
    end = 0;
    if len(sys.argv)==3:
        try:
            f = open(sys.argv[2])
            start, end, status = get_range(sys.argv[1])
            print_lines(start, end, f)
        except OSError:
            print("File not found: %s" % sys.argv[2])
            status = 1
    else:
        print("\nUsage readln RANGE FILE")
        print("The following example reads line 1 through 3 from file.txt")
        print("\t$ readln 1..3 file.txt")
        print("Output:\n\tline 1 content\n\tline 2 content\n\tline 3 content.")
        print("\nThe example bellow reads a single line from file.txt")
        print("\t$ readln 10 file.txt")
        print("Output:\n\tline 10 content\n")
        status = 3
    exit(status)
