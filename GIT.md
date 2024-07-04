# Work with objects in .git repo

```sh
# create file snapshot with hash and write as an object to .git folder 
git hash-object -w dir/challenge.txt > dir/hash.txt

# print file content using hash as a tag
git cat-file -p $(cat dir/hash.txt)

# list all blobs from .git folder
git fsck

# add dir/file structure to index with blob hash
git update-index --add --cacheinfo 100644 $(cat dir/hash.txt) dir/challenge.txt

# list all blobs in the repository
git ls-file -s

# print git tree hash 
git write-tree

# print git structure: blobs and trees
git cat-file -p $(git write-tree)
git cat-file -t tree_hash
```