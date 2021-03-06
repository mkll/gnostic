# Vocabulary Operations

This directory contains a command-line tool that provides operations for Vocabulary structures, 
including intersection, difference, union, and export.

## Usage:

The vocabulary-operations tool accepts a command that specifies which operation (union, intersection, difference, export) to run, and accepts at least one vocabulary file as an argument. Files can be provided using either command line arguments:

        vocabulary-operations -[command] [<file1.pb>] [<file2.pb>] ... [<filen.pb>]

or can be read using standard input:

        vocabulary-operations -[command] < [<files.txt>]

where <files.txt> is a text file containing the paths of vocabulary protocol buffer files. 

## Examples:

        vocabulary-operations -union < [<files.txt>] 

The `-union` options creates a new Vocabulary pb that combines the provided pb files into one large Vocabulary pb. The new Vocabulary pb is saved in the current working directory as "vocabulary-operations.pb"

        vocabulary-operations -intersection [<file1.pb>] [<file2.pb>] 

The `-intersection` options creates a new Vocabulary pb that contains vocabulary that is present in all of the provided files. The new Vocabulary pb is saved in the current working directory as "vocabulary-operations.pb"

        vocabulary-operations -difference [<file1.pb>] [<file2.pb>] 

The `-difference` options creates a new Vocabulary pb that contains vocabulary that is present in the first provided file but not the other provided files. The new Vocabulary pb is saved in the current working directory as "vocabulary-operations.pb"

         vocabulary-operations -export [<file1.pb>]

The `-export` option accepts *one* Vocabulary file and converts it into a user-friendly readable CSV file. The CSV file is saved in the current working directory as "vocabulary-operations.csv".                    
**Note:** While the other options accept both command line arguments and standard input, the export function only supports command line arguments.

