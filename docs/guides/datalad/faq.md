# DataLad New User FAQ

The following is a list of questions for which we have found the answers already and wanted to share to new DataLad users (within the NIMH IRP especially).

## What is DataLad?

From [the DataLad Handbook "philosophy" section](https://handbook.datalad.org/en/latest/intro/philosophy.html):

> DataLad is a software tool developed to aid with everything related to the evolution of digital objects.
>
> It is not only keeping track of code, it is not only keeping track of data, it is not only making sharing, retrieving and linking data (and metadata) easy, but it assists with the combination of all things necessary in the digital workflow of data and science.
>
> As built-in, but optional features, DataLad yields FAIR resources – for example metadata and provenance – and anything (or everything) can be easily shared should the user want this.


## How does DataLad work?

From [the DataLad Handbook FAQ](https://handbook.datalad.org/en/latest/basics/101-180-FAQ.html#what-does-datalad-add-to-git-and-git-annex):

> - Both Git and git-annex are made to work with a single repository at a time. A key advantage that DataLad brings to the table is that it makes the boundaries between repositories vanish from a user’s point of view. Most core commands have a `--recursive` option that will discover and traverse any subdatasets and do-the-right-thing. Whereas git and git-annex would require the caller to first cd to the target repository, DataLad figures out which repository the given paths belong to and then works within that repository. `datalad save . --recursive` will solve the subdataset problem above for example, no matter what was changed/added, no matter where in a tree of subdatasets.
> - DataLad provides users with the ability to act on “virtual” file paths. If software needs data files that are carried in a subdataset (in Git terms: submodule) for a computation or test, a `datalad get` will discover if there are any subdatasets to install at a particular version to eventually provide the file content.
> - DataLad adds metadata facilities for metadata extraction in various flavors, and can store extracted and aggregated metadata under `.datalad/metadata`.

## What's the advantage of DataLad over just storing and modifying files myself?

From [the DatLad Handbook "summary" section](https://handbook.datalad.org/en/latest/intro/executive_summary.html#full-provenance-capture-and-reproducibility):

> DataLad allows to capture full provenance: The origin of datasets, the origin of files obtained from web sources, complete machine-readable and automatically reproducible records of how files were created (including software environments).
>
> You or your collaborators can thus re-obtain or reproducibly recompute content with a single command, and make use of extensive provenance of dataset content (who created it, when, and how?).

## Do I have to use DataLad?

No, but you should consider if it is the right tool for your use case.

## When should I use DataLad?

When you want to embrace open science FAIR principles and make your data more reusable and reproducible.

## How would I usually use DataLad?

One of two ways to start.

1. If you already have a dataset then use:

    ```bash
    # wherever your dataset lives
    cd /my/dataset

    # turn it into a datalad dataset there
    datalad create --force .

    # this step can be used any time you've made modifications you're ready to track
    datalad save -m "Some message about your dataset"
    ```

1. If you are just starting a dataset then instead use:

    ```bash
    # go into your parent folder
    cd /my/datasets

    # datalad will create your subfolder
    datalad create my_new_dataset

    # go into your new datalad subfolder dataset
    cd my_new_dataset
    ```

Either way, after you have a DataLad dataset you can repeat this below cycle anytime:

```bash
# 1. MAKE ANY MODIFICATION(S) ; then
# 2. save your modifications
datalad save -m "Some message about your changes"
```

## When would I need to use DataLad different than described above?

When you have curated a dataset or have downloaded a curated dataset and you are ready to use more DataLad features like cloning, installing, or getting files.

## What are DataLad super-datasets and sub-datasets?

From [the DataLad FAQ](https://handbook.datalad.org/en/latest/basics/101-180-FAQ.html#what-is-the-difference-between-a-superdataset-a-subdataset-and-a-dataset):

> Conceptually and technically, there is no difference between a dataset, a subdataset, or a superdataset. The only aspect that makes a dataset a subdataset or superdataset is whether it is registered in another dataset or contains registered datasets.

## How do I interact with DataLad cloned files?

You change directory into the cloned folder and use `datalad install .` to retrieve the relevant files you want to use or access.

## Why do I have to DataLad install the data if I've already cloned the data?

DataLad stores cloned data as empty files to save space so you don't have to retain a full copy to use the dataset.

## Are cloned DataLad files copies of the original files?

No. They are git annex records of the source files. A kind of a database of where to find each piece of data, remotely or locally.

## What happens if I modify a file in a DataLad-controlled directory?

Using `datalad status` you can see the changed file paths and when you are ready you can `datalad save` the modified file(s).

## Are softlinks (a.k.a. symlinks or symbolic links) preserved through DataLad?

Yes. You can version softlinks, but be careful. DataLad will preserve the exact target of the softlink so if you take the DataLad dataset to another filesystem with a different hierarchy you will have versioned broken softlinks.
