# Github Actionsでワークフロー設定

pytest / mypy / flake8 をGithub Actionsで設定しPRまたはMergeの際に実行することで、devopsの向上を図る。

## 環境はpoetryで

poetryで環境を設定しておき、GAのpythonランタイムはpoetryで制御する。

### カスタムモジュールはpoetryでパスを通しておく

pyproject.tomlで以下のように書いておけば良い。

```toml
[tool.poetry]
name = ...
...
packages = [
    { include = "lib", from = "." },
]
```

## Featurework

sphinxでドキュメント生成、Github Pagesで公開をGithub Actionsで制御しておきたい。
