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
