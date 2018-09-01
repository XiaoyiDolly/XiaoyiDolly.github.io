'''
git checkout --orphan gh-pages
git reset --hard
git commit --allow-empty -m "Initializing gh-pages branch"
git push upstream gh-pages

git checkout master
rm -rf public
git worktree add -B public public upstream/public

hugo
cd public && git add --all && git commit -m "Publishing to public" && cd ..
git push upstream public
'''