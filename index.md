# jupyter-nbconvertをブラウザ上で使う方法
Gooogle Colaboratoryあるいはローカルな環境で作った.ipynbファイルををMarkdown,PDF,HTML,LaTeX出力したい時がある。そこでうっかりローカルな環境が使えなくなってしまったときに変換するコマンドであるjupyter-nbconvertをブラウザで使う方法（と実際の使用例）を載せる。
## xelatex のインストール
xelatexはpdf出力に必須。以下のコマンドを実行してインストールする。なお!マークはpythonのコードではなくターミナルの実行コマンドを使う合図である。


```python
!apt-get install texlive texlive-xetex texlive-latex-extra pandoc
```

以下は必要に応じて


```python
!apt-get update
```


```python
!pip install pypandoc
```

次にgoogle driveをこのipynbファイルに紐づける（アップロードすることも可能、要は左のフォルダマークのとこ、contentsに入っていれば良い）


```python
from google.colab import drive
drive.mount('/content/drive')
```

    Mounted at /content/drive


jupyter-nbconvertをつかう。使い方は!jupyter-nbconvertとそのまま打ち込めば確認可能。なおファイルのパス（空白をエスケープすることに注意）を「パスをコピー」から記載することを忘れずに。変換し終わると変換後のファイルがcontentsに出力される。


```python
!jupyter-nbconvert --to Markdown /content/drive/MyDrive/Colab\ Notebooks/下書き.ipynb
```


```python
!jupyter-nbconvert --to markdown /content/drive/MyDrive/Colab\ Notebooks/Life\ Science/Life\ Science\ 6.ipynb
```


```python
!jupyter-nbconvert --to markdown /content/drive/MyDrive/Colab\ Notebooks/nbconvert備忘録.ipynb
```

ちなみにターミナルコマンドをつかうとこうなる


```python
!echo $PATH
```

    /opt/bin:/usr/local/nvidia/bin:/usr/local/cuda/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/tools/node/bin:/tools/google-cloud-sdk/bin



```python
!pwd
```

    /content



```python
!jupyter-nbconvert --to latex /content/python_bibouroku.ipynb
```


```python
!jupyter-nbconvert --to html "/content/drive/MyDrive/Colab Notebooks/nbconvert備忘録.ipynb"
```

    [NbConvertApp] Converting notebook /content/drive/MyDrive/Colab Notebooks/nbconvert備忘録.ipynb to html
    [NbConvertApp] Writing 280995 bytes to /content/drive/MyDrive/Colab Notebooks/nbconvert備忘録.html



