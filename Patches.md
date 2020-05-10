In the `./enhancements` folder, there are several .patch files, which can be applied in the following manner:

```
 git apply fps.patch --ignore-whitespace --reject
```
If any rejections occur, you can search for them with `find | grep .rej`.
Try to solve rejections through [wiggle](https://github.com/neilbrown/wiggle).
```
wiggle rejection.rej --replace
```

