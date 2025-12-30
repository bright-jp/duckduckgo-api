# DuckDuckGo Search Scraper

[![Promo](https://media.brightdata.com/2025/08/SERP-API-50-off-GitHub-banner_1389_166.png)](https://brightdata.jp/products/serp-api/duckduckgo-search)

このリポジトリでは、DuckDuckGoの検索エンジン結果ページ（SERPs）からデータを抽出するための2つのソリューションを提供します。

- **無料 DuckDuckGo Scraper:** 小規模でDuckDuckGo検索結果をスクレイピングするためのツール
- **エンタープライズグレード DuckDuckGo SERP API:** 大量・リアルタイムのデータ抽出に対応した、スケーラブルで本番運用可能なソリューション（[Bright Data's SERP Scraper API](https://brightdata.jp/products/serp-api) の一部）

## Table of Contents

- [Free DuckDuckGo SERP Scraper](#free-duckduckgo-serp-scraper)
  - [Setup Requirements](#setup-requirements)
  - [Quick Start Guide](#quick-start-guide)
  - [Sample Output](#sample-output)
  - [Limitations](#limitations)
- [DuckDuckGo SERP API](#duckduckgo-serp-api)
  - [Key Benefits](#key-benefits)
  - [Getting Started](#getting-started)
- [Implementation Methods](#implementation-methods)
  - [Direct API Access](#direct-api-access)
  - [Native Proxy-Based Access](#native-proxy-based-access)
- [DuckDuckGo Search Query Parameters](#duckduckgo-search-query-parameters)
  - [Localization](#localization)
  - [Safe Search Configuration)](#safe-search-configuration-kp)
  - [Time Range Filtering](#time-range-filtering-df)
  - [Device Targeting](#device-targeting-brd_mobile)
  - [Browser Emulation](#browser-emulation-brd_browser)
- [Practical Example](#practical-example)
- [Support & Resources](#support--resources)

## Free DuckDuckGo SERP Scraper
Free DuckDuckGo SERP Scraperは、小規模に検索結果データを収集するためのシンプルな方法を提供します。プロキシの管理や大量処理のオーバーヘッドなしで、限られたデータが必要な場合に最適です。

<img width="800" alt="free-duckduckgo-serp-scraper" src="https://github.com/luminati-io/duckduckgo-api/blob/main/images/428465443-0472593e-615c-4723-96e7-08f83cb0b477.png" />

### Setup Requirements

- **Python 3.9+** – [Download Python](https://www.python.org/downloads/)
- **Required Packages:**
    - `selenium`（ブラウザ自動化用）
    - `webdriver-manager`（ブラウザドライバー管理用）
    - `beautifulsoup4`（HTML解析用）

以下でパッケージをインストールします：
```bash
pip install selenium webdriver-manager beautifulsoup4
```

> **Webスクレイピングが初めてですか？** <br>
まずは [Beginner’s Guide to Web Scraping with Python](https://brightdata.jp/blog/how-tos/web-scraping-with-python) で学習を始めてください。次に、[Using Selenium for Web Scraping](https://brightdata.jp/blog/how-tos/using-selenium-for-web-scraping) チュートリアルでレベルアップし、すでにSeleniumに慣れている場合は、高度な [SeleniumBase guide](https://brightdata.jp/blog/web-data/web-scraping-with-seleniumbase) でさらにスキルを伸ばしてください。
>

### Quick Start Guide

1. [duckduckgo-serp-scraper.py](https://github.com/triposat/DuckDuckGo-Search-Scraper/blob/main/duckduckgo-serp-scraper/duckduckgo-serp-scraper.py) ファイルを開きます。
2. 必要に応じて検索語をカスタマイズします：
    
    ```python
    SEARCH_TERMS = [
        "ergonomic office chair",
        "coffee maker",
    ]
    ```
    
3. スクリプトを実行してスクレイピングを開始します。

### Sample Output
以下はスクレイパーの出力プレビューです：

<img width="800" alt="free-duckduckgo-serp-scraper-output" src="https://github.com/luminati-io/duckduckgo-api/blob/main/images/428465286-d6891a93-2b5f-4243-8a17-e2a037c91570.png" />


### Limitations

無料スクレイパーは基本的なタスクには便利ですが、以下の重要な制限がある点に注意してください：

- 頻繁に使用するとIPアドレスをブロックされるリスクが高い
- リクエスト量の対応能力が限定的
- CAPTCHAの中断が頻繁に発生
- 本番環境には不向き

スケーラブルで安定したソリューションが必要な場合は、以下で説明するBright Dataの専用APIをご検討ください 👇

## DuckDuckGo SERP API

DuckDuckGo SERP APIは、Bright Dataの包括的な [SERP Scraper API](https://brightdata.jp/products/serp-api) スイートの一部です。業界をリードする [DuckDuckGo proxy infrastructure](https://brightdata.jp/solutions/duckduckgo-proxies) を活用し、単一のAPI呼び出しでリアルタイムのDuckDuckGo検索結果を提供します。

### Key Benefits

- **グローバルな精度**: 世界中の特定ロケーション向けに最適化された結果を取得できます。
- **Pay-Per-Success**: 成功したリクエストに対してのみ料金が発生します。
- **リアルタイムデータ**: 数秒で最新の検索結果にアクセスできます。
- **無制限のスケーラビリティ**: 大量スクレイピングを容易に処理できます。
- **コスト効率**: 高価なインフラは不要です。
- **信頼性の高いパフォーマンス**: 高度なアンチブロッキング技術により一貫した結果を確保します。
- **24/7 エキスパートサポート**: 必要なときにいつでも支援を受けられます。

📌 Try Before You Buy: [SERP API Live Demo](https://brightdata.jp/products/serp-api/duckduckgo-search) でソリューションを体験できます。

<img width="800" alt="bright-data-serp-api-playground" src="https://github.com/luminati-io/duckduckgo-api/blob/main/images/428471522-fc60e165-e4db-41d2-93eb-2b6a01398353.png" />

### Getting Started

1. [Bright Dataアカウントを作成](https://brightdata.jp/) します（新規ユーザーには$5クレジットが付与されます）。
2. [API key](https://docs.brightdata.com/general/account/api-token) を生成します。
3. [step-by-step configuration guide](https://github.com/triposat/DuckDuckGo-Search-Scraper/blob/main/setup-serp-api.md) に従ってSERP APIを統合します。

## Implementation Methods

以下の2つの方法のいずれかで、DuckDuckGo SERP APIをワークフローに統合できます：

### Direct API Access

Bright DataのAPIエンドポイントへ直接リクエストします。

#### cURL Example

```bash
curl https://api.brightdata.com/request \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer API_TOKEN" \
  -d '{
        "zone": "ZONE_NAME",
        "url": "https://duckduckgo.com/?q=budget+laptops+under+500+gbp&kl=uk-en&kad=en-gb&df=w",
        "format": "raw"
      }'
```

#### Python Example

```python
import requests

url = "https://api.brightdata.com/request"

headers = {
    "Content-Type": "application/json",
    "Authorization": "Bearer API_TOKEN"
}

payload = {
    "zone": "ZONE_NAME",
    "url": "https://duckduckgo.com/?q=budget+laptops+under+500+gbp&kl=uk-en&kad=en-gb&df=w",
    "format": "raw",
}

response = requests.post(url, headers=headers, json=payload)

with open("duckduckgo-scraper-api-result.html", "w", encoding="utf-8") as file:
    file.write(response.text)

print("Response saved!")
```

### Native Proxy-Based Access

検索結果へ直接アクセスするために、プロキシルーティングを使用します。

#### cURL Example

```bash
curl -i \
  --proxy brd.superproxy.io:33335 \
  --proxy-user brd-customer-<CUSTOMER_ID>-zone-<ZONE_NAME>:<ZONE_PASSWORD> \
  -k \
  "https://duckduckgo.com/?q=budget+laptops+under+500+gbp&kl=uk-en&kad=en-gb&df=w"
```

#### Python Example

```python
import requests
import urllib3

urllib3.disable_warnings(urllib3.exceptions.InsecureRequestWarning)

host = "brd.superproxy.io"
port = 33335
username = "brd-customer-<CUSTOMER_ID>-zone-<ZONE_NAME>"
password = "<ZONE_PASSWORD>"
proxy_url = f"http://{username}:{password}@{host}:{port}"

proxies = {
    "http": proxy_url,
    "https": proxy_url
}

url = "https://duckduckgo.com/?q=budget+laptops+under+500+gbp&kl=uk-en&kad=en-gb&df=w"
response = requests.get(url, proxies=proxies, verify=False)

with open("duckduckgo-scraper-api-result.html", "w", encoding="utf-8") as file:
    file.write(response.text)

print("Response saved!")
```

> Note: ネイティブプロキシ方式を本番運用で使用する場合は、Bright DataのSSL証明書をインストールすることを推奨します。詳細は [SSL Certificate Guide](https://docs.brightdata.com/general/account/ssl-certificate) を参照してください。
> 

👉 HTML出力の完全なプレビューについては、[complete result](https://github.com/triposat/DuckDuckGo-Search-Scraper/blob/main/duckduckgo-scraper-api-output/duckduckgo-scraper-api-result.html) をご覧ください。


## DuckDuckGo Search Query Parameters

さまざまなクエリパラメータを使用して検索結果を微調整できます。

### Localization

#### Country and Language (`kl`)

検索結果の国と言語を指定します。

*Example:*

```bash
curl --proxy brd.superproxy.io:33335 \
     --proxy-user brd-customer-<id>-zone-<zone>:<password> \
     "https://duckduckgo.com/?q=best+coffee+brands&kl=it-it"
```

これはイタリア向けに最適化された検索結果を返します。

#### Interface Language (`kad`)

DuckDuckGoインターフェースの言語を制御します。

*Example:*

```bash
https://duckduckgo.com/?q=photo+editing+tools&kad=de
```

これにより、検索コンテンツは英語のまま、インターフェースがドイツ語で表示されます。

### Safe Search Configuration (`kp`)

成人向けコンテンツに対するフィルタリングを調整します。

#### Values

- `1` – 厳格なSafe Search
- `-1` – 中程度
- `-2` – オフ

*Example:*

```bash
https://duckduckgo.com/?q=swimsuit&kp=1
```

*"swimsuit”* に対してファミリー向けの結果のみを返します。

### Time Range Filtering (`df`)

検索結果を特定の期間に限定します。

#### Values

- `d` – 過去1日
- `w` – 過去1週間
- `m` – 過去1か月
- `y` – 過去1年
- *Custom range:* 例：`2025-03-01..2025-03-10`

*Example:*

```bash
https://duckduckgo.com/?q=iphone+15+review&df=w
```

直近（過去1週間）のレビューのみを表示します。

### Device Targeting (`brd_mobile`)

さまざまなデバイスタイプからの検索をシミュレートします。

#### Options

- `0` – デスクトップ（デフォルト）
- `1` – ランダムなモバイルデバイス
- `ios` or `iphone` – iPhone
- `ipad` or `ios_tablet` – iPad
- `android` – Android phone
- `android_tablet` – Android tablet

 *Example:*

```bash
https://duckduckgo.com/?q=top+travel+apps&brd_mobile=ios
```

これはiPhoneユーザーをシミュレートします。App Storeリンク、モバイル向けコンテンツ、またはAMPページが表示される場合があります。

### Browser Emulation (`brd_browser`)

リクエストに使用するブラウザのuser-agentを指定します。

#### Options

- Default（ランダムなブラウザ）
- `chrome` – Google Chrome
- `safari` – Safari
- `firefox` – Mozilla Firefox *( `brd_mobile=1` とは互換性がありません)*

*Example:*

```bash
https://duckduckgo.com/?q=best+vpn+services&brd_browser=safari
```
これはSafariブラウザをシミュレートし、そのプラットフォームでコンテンツがどのように表示・ランキングされるかの把握に役立ちます。

## Practical Example

英国で *"budget laptops under £500"* の競合の価格ページを監視しており、モバイルユーザーをターゲットにしています。

目的は以下のとおりです：

- 英国ベースのモバイルユーザーをシミュレートする
- ローカライズされた英語の結果を取得する（英国の小売業者、通貨）
- モバイル向けChrome user agentを使用する（AMPページなどモバイル固有の結果を取得するため）
- 最近の製品まとめ記事やセールに注目する

これらの要件を1つのcURLコマンドにまとめます：

```bash
curl --proxy brd.superproxy.io:33335 \
     --proxy-user brd-customer-<CUSTOMER_ID>-zone-<ZONE_NAME>:<ZONE_PASSWORD> \
     "https://duckduckgo.com/?\
q=budget+laptops+under+500+gbp&\
kl=uk-en&\
kad=en-gb&\
df=w&\
brd_mobile=android&\
brd_browser=chrome"
```
🎯 これにより、**モバイルファースト**、**ローカライズ**、かつ**最新**のコンテンツを取得できます。

## Support & Resources

- **Documentation:** [SERP API Documentation](https://docs.brightdata.com/scraping-automation/serp-api/)
- **Related APIs:**
    - [SERP API](https://github.com/luminati-io/serp-api)
    - [Google Search API](https://github.com/luminati-io/google-search-api)
    - [Google News Scraper](https://github.com/luminati-io/Google-News-Scraper)
    - [Google Trends API](https://github.com/luminati-io/google-trends-api)
    - [Google Reviews API](https://github.com/luminati-io/google-reviews-api)
    - [Google Hotels API](https://github.com/luminati-io/google-hotels-api)
    - [Google Flights API](https://github.com/luminati-io/google-flights-api)
    - [Web Unlocker API](https://github.com/luminati-io/web-unlocker-api)
- **Use Cases:**
    - [SEO & SERP Tracking](https://brightdata.jp/use-cases/serp-tracking)
    - [Travel Industry Data](https://brightdata.jp/use-cases/travel)
- **Additional Reading:** [Best SERP APIs](https://brightdata.jp/blog/web-data/best-serp-apis)
- **Contact Support:** [support@brightdata.com](mailto:support@brightdata.com)