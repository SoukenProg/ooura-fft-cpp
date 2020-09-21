# 大浦版FFT(一次元DFT/DCT) C++ラッパーライブラリ
## Cコードの改変部分
`fftsg.c`のうち、以下の部分を改変しています。

- (C++の場合)コード全体を`fftsg`名前空間内に入れるように
    - それに伴い、コード中の`#include`は先頭の名前空間外に移動
- double型をfloat型に置き換えたものを追加(`fftsg_float.c`)
    - float版は関数名の末尾に`f`を追加(C言語はオーバーロードできないため)
    - float版は実数値に`f`のサフィックスを付けてfloat型に
    - float版では数学関数に`sinf()`などのfloat用関数を使うよう変更(C言語の数学関数はオーバーロードされないため)
    - (C++の場合)オーバーロードでdouble型とfloat型の関数を同じ関数名で使用できるように
- 内部の計算に使用する関数は`static`を付けて内部リンケージにするように
    - そのままだとリンク時にdouble版とfloat版の関数名が衝突するため

## 大浦版FFTについて
### 配布ページ
- http://www.kurims.kyoto-u.ac.jp/~ooura/fft-j.html

### README原文
- [readme_fftsg.txt](readme_fftsg.txt)

### ライセンス原文
```
Copyright Takuya OOURA, 1996-2001

このソースコードはフリーソフトです．商用目的を含め，このコードの使用， コピー，修正及び配布は自由に行って結構です．ただし，このコードの修正を 行った場合は，そのことを明記してください．
```
