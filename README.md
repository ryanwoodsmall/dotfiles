# dotfiles
.d.o.t.f.i.l.e.s.

# use

eval this, maybe:

```shell
for d in ${PWD}/dot_* ; do
  t=${d//dot_/.}
  t=${t//${PWD}/${HOME}}
  h=${t%/*}
  echo "test -e ${h} || mkdir -p ${h}"
  echo "test -e ${t} || ln -s ${d} ${t}"
done
```

or run this, if you trust some guy on the internet:

```shell
for u in https://raw.githubusercontent.com/ryanwoodsmall/dotfiles/master/dot_{bim{3,},elvis,ex,vile,vim}rc
do
  f="$(basename ${u//dot_/.})"
  curl -kLo "${HOME}/${f}" "${u}"
done
```
