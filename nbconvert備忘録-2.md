# jupyter-nbconvertをブラウザ上で使う方法
Gooogle Colaboratoryあるいはローカルな環境で作った.ipynbファイルををMarkdown,PDF,HTML,LaTeX出力したい時がある。そこでうっかりローカルな環境が使えなくなってしまったときに変換するコマンドであるjupyter-nbconvertをブラウザで使う方法（と実際の使用例）を載せる。
## xelatex のインストール
xelatexはpdf出力に必須。以下のコマンドを実行してインストールする。なお!マークはpythonのコードではなくターミナルの実行コマンドを使う合図である。


```python
!apt-get install texlive-xetex texlive-fonts-recommended texlive-plain-generic
```

次にgoogle driveをこのipynbファイルに紐づける（アップロードすることも可能、要は左のフォルダマークのとこ、contentsに入っていれば良い）


```python
from google.colab import drive
drive.mount('/content/drive')
```

    Mounted at /content/drive


jupyter-nbconvertをつかう。使い方は!jupyter-nbconvertとそのまま打ち込めば確認可能。なおファイルのパス（空白をエスケープすることに注意）を「パスをコピー」から記載することを忘れずに。変換し終わると変換後のファイルがcontentsに出力される。


```python
!jupyter-nbconvert
```


```python
!jupyter-nbconvert --to Markdown /content/drive/MyDrive/Colab\ Notebooks/下書き.ipynb
```

    [NbConvertApp] Converting notebook /content/drive/MyDrive/Colab Notebooks/下書き.ipynb to Markdown
    [NbConvertApp] Support files will be in 下書き_files/
    [NbConvertApp] Making directory /content/drive/MyDrive/Colab Notebooks/下書き_files
    [NbConvertApp] Making directory /content/drive/MyDrive/Colab Notebooks/下書き_files
    [NbConvertApp] Making directory /content/drive/MyDrive/Colab Notebooks/下書き_files
    [NbConvertApp] Making directory /content/drive/MyDrive/Colab Notebooks/下書き_files
    [NbConvertApp] Making directory /content/drive/MyDrive/Colab Notebooks/下書き_files
    [NbConvertApp] Making directory /content/drive/MyDrive/Colab Notebooks/下書き_files
    [NbConvertApp] Making directory /content/drive/MyDrive/Colab Notebooks/下書き_files
    [NbConvertApp] Making directory /content/drive/MyDrive/Colab Notebooks/下書き_files
    [NbConvertApp] Writing 866747 bytes to /content/drive/MyDrive/Colab Notebooks/下書き.md



```python
!jupyter-nbconvert --to markdown /content/drive/MyDrive/Colab\ Notebooks/Life\ Science/Life\ Science\ 6.ipynb
```

    [NbConvertApp] Converting notebook /content/drive/MyDrive/Colab Notebooks/Life Science/Life Science 6.ipynb to markdown
    [NbConvertApp] Support files will be in Life Science 6_files/
    [NbConvertApp] Making directory /content/drive/MyDrive/Colab Notebooks/Life Science/Life Science 6_files
    [NbConvertApp] Making directory /content/drive/MyDrive/Colab Notebooks/Life Science/Life Science 6_files
    [NbConvertApp] Making directory /content/drive/MyDrive/Colab Notebooks/Life Science/Life Science 6_files
    [NbConvertApp] Writing 803692 bytes to /content/drive/MyDrive/Colab Notebooks/Life Science/Life Science 6.md



```python
!jupyter-nbconvert --to html /content/drive/MyDrive/Colab\ Notebooks/nbconvert備忘録.ipynb
```

    [NbConvertApp] Converting notebook /content/drive/MyDrive/Colab Notebooks/nbconvert備忘録.ipynb to html
    [NbConvertApp] Writing 280306 bytes to /content/drive/MyDrive/Colab Notebooks/nbconvert備忘録.html



