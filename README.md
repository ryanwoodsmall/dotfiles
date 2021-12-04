# dotfiles
.d.o.t.f.i.l.e.s.

# use

eval this, maybe:

```shell
for d in ${PWD}/dot_* ; do
  t=${d//dot_/.}
  t=${t//${PWD}/${HOME}}
  h=${t%/*}
  test -e ${t} && mv ${t}{,.PRE-$(date +%Y%m%d%H%M%S)} || true
  echo "test -e ${h} || mkdir -p ${h}"
  echo "test -e ${t} || ln -s ${d} ${t}"
done
```

or run this, if you trust some guy on the internet:

```shell
for p in bim3 bim elvis ex vile vim ; do
  u="https://raw.githubusercontent.com/ryanwoodsmall/dotfiles/master/dot_${p}rc"
  f="${HOME}/$(basename ${u//dot_/.})"
  test -e ${f} && mv ${f}{,.PRE-$(date +%Y%m%d%H%M%S)} || true
  curl -kLo "${f}" "${u}"
done
```
