# DataLad New User FAQ

The following is a list of questions for which we have found the answers already and wanted to share to new DataLad users (within the NIMH IRP especially).

## What is DataLad?

DataLad sits on top of Git and git-annex and tries to integrate and expose their functionality fully. More in [the DataLad FAQ](https://handbook.datalad.org/en/latest/basics/101-180-FAQ.html#what-does-datalad-add-to-git-and-git-annex).

## How does DataLad work?

From [the DataLad FAQ](https://handbook.datalad.org/en/latest/basics/101-180-FAQ.html#what-does-datalad-add-to-git-and-git-annex):

> - Both Git and git-annex are made to work with a single repository at a time. A key advantage that DataLad brings to the table is that it makes the boundaries between repositories vanish from a user’s point of view. Most core commands have a `--recursive` option that will discover and traverse any subdatasets and do-the-right-thing. Whereas git and git-annex would require the caller to first cd to the target repository, DataLad figures out which repository the given paths belong to and then works within that repository. `datalad save . --recursive` will solve the subdataset problem above for example, no matter what was changed/added, no matter where in a tree of subdatasets.
> - DataLad provides users with the ability to act on “virtual” file paths. If software needs data files that are carried in a subdataset (in Git terms: submodule) for a computation or test, a `datalad get` will discover if there are any subdatasets to install at a particular version to eventually provide the file content.
> - DataLad adds metadata facilities for metadata extraction in various flavors, and can store extracted and aggregated metadata under `.datalad/metadata`.

## What's the advantage of DataLad over just storing and modifying files myself?

First,

## Do I have to use DataLad?

No.

## When should I use DataLad?

Whenever

## How would I usually use DataLad?

You would

## When would I need to use DataLad different than described above?

Whenever

## What are DataLad super-datasets and sub-datasets?

From [the DataLad FAQ](https://handbook.datalad.org/en/latest/basics/101-180-FAQ.html#what-is-the-difference-between-a-superdataset-a-subdataset-and-a-dataset):

> Conceptually and technically, there is no difference between a dataset, a subdataset, or a superdataset. The only aspect that makes a dataset a subdataset or superdataset is whether it is registered in another dataset or contains registered datasets.

## How do I interact with DataLad cloned files?

Cloned files

## Why do I have to DataLad install the data if I've already cloned the data?

DataLad stores cloned data as

## Are cloned DataLad files copies of the original files?

No.

## What happens if I modify a file in a DataLad-controlled directory?

First

## Are softlinks (a.k.a. symlinks or symbolic links) preserved through DataLad?

Yes.
