# 株式会社ツクロア 就業規則

株式会社ツクロアで運用中の就業規則です。  
本就業規則は主に以下の2点を参考に作成しました。

- [モデル就業規則(平成31年3月時点のもの)](https://www.mhlw.go.jp/stf/seisakunitsuite/bunya/koyou_roudou/roudoukijun/zigyonushi/model/index.html)
- [デンキヤギ株式会社 就業規則](https://github.com/DenkiYagi/EmployeeHandbook)

就業規則・各規程のうち、就業規則と賃金規程は[@Takashi-U](https://github.com/Takashi-U)さんのチェックを経て施行しています。

## 主な特徴

- 労働者の名称を社員としている
- すべての社員の就業場所を自宅としている
- すべての社員にフレックスタイム制を適用している
- すべての社員の基本給は時間給として取り扱う
- 年次有給休暇を一斉付与している

## issueテンプレートの使い方

就業規則・各規程に定めのある手続きをおこなうためのテンプレートです。  
別途プライベートリポジトリで利用することを想定しています。  
git-subtreeを使って導入してください。

```
$ git remote add employee-handbook git@github.com:tuqulore/employee-handbook.git
$ git subtree add --prefix .github --squash employee-handbook master
```

導入後は以下のように更新してください。

```
$ git subtree pull --prefix .github --squash employee-handbook master
```

## ライセンス

<p xmlns:dct="http://purl.org/dc/terms/" xmlns:vcard="http://www.w3.org/2001/vcard-rdf/3.0#">
  <a rel="license"
     href="http://creativecommons.org/publicdomain/zero/1.0/">
    <img src="http://i.creativecommons.org/p/zero/1.0/88x31.png" style="border-style: none;" alt="CC0" />
  </a>
  <br />
  To the extent possible under law,
  <a rel="dct:publisher"
     href="https://tuqulore.com/">
    <span property="dct:title">株式会社ツクロア</span></a>
  has waived all copyright and related or neighboring rights to
  <span property="dct:title">株式会社ツクロア 就業規則</span>.
This work is published from:
<span property="vcard:Country" datatype="dct:ISO3166"
      content="JP" about="https://tuqulore.com/">
  日本</span>.
</p>
