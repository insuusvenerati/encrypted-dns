[English](https://github.com/paulmillr/encrypted-dns/) | [简体中文](https://github.com/paulmillr/encrypted-dns/blob/master/README.cmn-CN.md) | 繁體中文

# 加密 DNS 配置

[DNS over HTTPS](https://zh.wikipedia.org/zh-tw/DNS_over_HTTPS) 和 [DNS over TLS](https://zh.wikipedia.org/zh-tw/DNS_over_TLS) 的設定描述檔。查看這篇文章以獲取更多訊息：[paulmillr.com/posts/encrypted-dns/](https://paulmillr.com/posts/encrypted-dns/) 以及有關[提交新描述檔](#提交新描述檔)的訊息。

### 注意事項

根據 [Google 這篇文章](https://security.googleblog.com/2022/07/dns-over-http3-in-android.html)的介紹，DoH 似乎比 DoT 的性能更優。

從 iOS 和 iPadOS 15.5 開始，為了簡化咖啡館、飯店、機場等公共場所 Wi-Fi 的身份認證，蘋果將這些 Wi-Fi 的[強制網路門戶](https://zh.wikipedia.org/zh-tw/%E5%BC%BA%E5%88%B6%E9%97%A8%E6%88%B7)加入到了加密 DNS 豁免清單中。這是個好消息，但還有一些其他問題我們無法修復，只有等蘋果來解決：

- 無法啟用加密 DNS：[Little Snitch & Lulu](https://github.com/paulmillr/encrypted-dns/issues/13)、[VPN](https://github.com/paulmillr/encrypted-dns/issues/18)
- 部分流量繞過加密 DNS：[終端機和 App Store](https://github.com/paulmillr/encrypted-dns/issues/22)、[Chrome 瀏覽器](https://github.com/paulmillr/encrypted-dns/issues/19)

如果你需要更進一步的隱私保護，請查看[使用 Tor 網路的加密 DNS](https://github.com/alecmuffett/dohot)。

## 供應商

「`審查=是`」意味著描述檔不會發送某些主機「`主機名=IP`」關係的真實訊息。

| 名稱                                                                                 | 區域  | 審查 | 備註                                                                                 | 安裝連結                                                                                                     |                                                                                                    |
| ------------------------------------------------------------------------------------ | ----- | ---- | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------- |
| [360 安全 DNS][360-dns]                                                              | 🇨🇳    | 是   | 由 360 數位安全集團營運                                                              | [HTTPS][360-dns-profile-https-signed]                                                                        | [HTTPS][360-dns-profile-https]                                                                     |
| [AdGuard DNS 預設][adguard-dns-default]                                              | 🇷🇺    | 是   | 由 AdGuard 營運，阻擋廣告、追蹤器和釣魚網站                                          | [HTTPS][adguard-dns-default-profile-https-signed], [TLS][adguard-dns-default-profile-tls-signed]             | [HTTPS][adguard-dns-default-profile-https], [TLS][adguard-dns-default-profile-tls]                 |
| [AdGuard DNS 家庭保護][adguard-dns-family]                                           | 🇷🇺    | 是   | 由 AdGuard 營運，除預設規則外，額外阻擋惡意軟體和成人內容                            | [HTTPS][adguard-dns-family-profile-https-signed], [TLS][adguard-dns-family-profile-tls-signed]               | [HTTPS][adguard-dns-family-profile-https], [TLS][adguard-dns-family-profile-tls]                   |
| [AdGuard DNS 預設][adguard-dns-self]                                                 |       | 是   | 由 AdGuard 營運，阻擋廣告、追蹤器和釣魚網站                                          |                                                                                                              | [HTTPS][adguard-dns-self-profile-https], [TLS][adguard-dns-self-profile-tls]                       |
| [AdGuard DNS 無過濾][adguard-dns-unfiltered]                                         | 🇷🇺    | 否   | 由 AdGuard 營運，無過濾                                                              | [HTTPS][adguard-dns-unfiltered-profile-https-signed], [TLS][adguard-dns-unfiltered-profile-tls-signed]       | [HTTPS][adguard-dns-unfiltered-profile-https], [TLS][adguard-dns-unfiltered-profile-tls]           |
| [Alekberg 加密 DNS][alekberg-dns]                                                    | 🇳🇱    | 否   | 由個人提供                                                                           | [HTTPS][alekberg-dns-profile-https-signed]                                                                   | [HTTPS][alekberg-dns-profile-https]                                                                |
| [阿里雲公共 DNS][aliyun-dns]                                                         | 🇨🇳    | 否   | 由阿里雲計算營運                                                                     | [HTTPS][aliyun-dns-profile-https-signed], [TLS][aliyun-dns-profile-tls-signed]                               | [HTTPS][aliyun-dns-profile-https], [TLS][aliyun-dns-profile-tls]                                   |
| [BlahDNS CDN 過濾][blahdns]                                                          | 🇺🇸    | 是   | 由個人提供，阻擋廣告、追蹤器和惡意軟體                                               | [HTTPS][blahdns-cdn-filtered-profile-https-signed]                                                           | [HTTPS][blahdns-cdn-filtered-profile-https]                                                        |
| [BlahDNS CDN 無過濾][blahdns]                                                        | 🇺🇸    | 否   | 由個人提供，無過濾                                                                   | [HTTPS][blahdns-cdn-unfiltered-profile-https-signed]                                                         | [HTTPS][blahdns-cdn-unfiltered-profile-https]                                                      |
| [BlahDNS 德國][blahdns]                                                              | 🇩🇪    | 是   | 由個人提供，阻擋廣告、追蹤器和惡意軟體                                               | [HTTPS][blahdns-germany-profile-https-signed]                                                                | [HTTPS][blahdns-germany-profile-https]                                                             |
| [BlahDNS 新加坡][blahdns]                                                            | 🇸🇬    | 是   | 由個人提供，阻擋廣告、追蹤器和惡意軟體                                               | [HTTPS][blahdns-singapore-profile-https-signed]                                                              | [HTTPS][blahdns-singapore-profile-https]                                                           |
| [Canadian Shield 私人][canadian-shield]                                              | 🇨🇦    | 否   | 由加拿大網際網路註冊管理局 (CIRA) 營運                                               | [HTTPS][canadian-shield-private-profile-https-signed], [TLS][canadian-shield-private-profile-tls-signed]     | [HTTPS][canadian-shield-private-profile-https], [TLS][canadian-shield-private-profile-tls]         |
| [Canadian Shield 保護][canadian-shield]                                              | 🇨🇦    | 是   | 由加拿大網際網路註冊管理局 (CIRA) 營運，阻擋惡意軟體和釣魚網站                       | [HTTPS][canadian-shield-protected-profile-https-signed], [TLS][canadian-shield-protected-profile-tls-signed] | [HTTPS][canadian-shield-protected-profile-https], [TLS][canadian-shield-protected-profile-tls]     |
| [Canadian Shield 家庭][canadian-shield]                                              | 🇨🇦    | 是   | 由加拿大網際網路註冊管理局 (CIRA) 營運，阻擋惡意軟體、釣魚和成人內容                 | [HTTPS][canadian-shield-family-profile-https-signed], [TLS][canadian-shield-family-profile-tls-signed]       | [HTTPS][canadian-shield-family-profile-https], [TLS][canadian-shield-family-profile-tls]           |
| [Cleanbrowsing 家庭過濾器][cleanbrowsing]                                            | 🇺🇸    | 是   | 過濾惡意軟體、成人內容和混合內容                                                     |                                                                                                              | [HTTPS][cleanbrowsing-family-https], [TLS][cleanbrowsing-family-tls]                               |
| [Cleanbrowsing 成人過濾器][cleanbrowsing]                                            | 🇺🇸    | 是   | 過濾惡意軟體和成人內容                                                               |                                                                                                              | [HTTPS][cleanbrowsing-adult-https], [TLS][cleanbrowsing-adult-tls]                                 |
| [Cleanbrowsing 安全過濾器][cleanbrowsing]                                            | 🇺🇸    | 是   | 過濾惡意軟體                                                                         |                                                                                                              | [HTTPS][cleanbrowsing-security-https], [TLS][cleanbrowsing-security-tls]                           |
| [Cloudflare 1.1.1.1][cloudflare-dns]                                                 | 🇺🇸    | 否   | 由 Cloudflare 公司營運                                                               | [HTTPS][cloudflare-dns-profile-https-signed], [TLS][cloudflare-dns-profile-tls-signed]                       | [HTTPS][cloudflare-dns-profile-https], [TLS][cloudflare-dns-profile-tls]                           |
| [Cloudflare 1.1.1.1 安全][cloudflare-dns-family]                                     | 🇺🇸    | 是   | 由 Cloudflare 公司營運，阻擋惡意軟體和釣魚網站                                       | [HTTPS][cloudflare-dns-security-profile-https-signed]                                                        | [HTTPS][cloudflare-dns-security-profile-https]                                                     |
| [Cloudflare 1.1.1.1 家庭][cloudflare-dns-family]                                     | 🇺🇸    | 是   | 由 Cloudflare 公司營運，阻擋惡意軟體、釣魚和成人內容                                 | [HTTPS][cloudflare-dns-family-profile-https-signed]                                                          | [HTTPS][cloudflare-dns-family-profile-https]                                                       |
| [DNS4EU][dns4eu]                                                                     | 🇨🇿    | 否   | Operated by a consortium lead by Whalebone.                                          |                                                                                                              | [HTTPS][dns4eu-profile-https], [TLS][dns4eu-profile-tls]                                           |
| [DNS4EU Protective][dns4eu-malware]                                                  | 🇨🇿    | 是   | Operated by a consortium lead by Whalebone. Blocks Malware.                          |                                                                                                              | [HTTPS][dns4eu-profile-malware-https], [TLS][dns4eu-profile-malware-tls]                           |
| [DNS4EU Protective ad-blocking][dns4eu-protective-ads]                               | 🇨🇿    | 是   | Operated by a consortium lead by Whalebone. Blocks Malware and Ads                   |                                                                                                              | [HTTPS][dns4eu-profile-protective-ads-https], [TLS][dns4eu-profile-protective-ads-tls]             |
| [DNS4EU Protective with child protection][dns4eu-protective-child]                   | 🇨🇿    | 是   | Operated by a consortium lead by Whalebone. Blocks malware and explicit content.     |                                                                                                              | [HTTPS][dns4eu-profile-protective-child-https], [TLS][dns4eu-profile-protective-child-tls]         |
| [DNS4EU Protective with child protection & ad-blocking][dns4eu-protective-child-ads] | 🇨🇿    | 是   | Operated by a consortium lead by Whalebone. Blocks Malware, Ads and explicit content |                                                                                                              | [HTTPS][dns4eu-profile-protective-child-ads-https], [TLS][dns4eu-profile-protective-child-ads-tls] |
| [DNSPod 公共 DNS][dnspod-dns]                                                        | 🇨🇳    | 否   | 由騰訊公司 DNSPod 營運                                                               | [HTTPS][dnspod-dns-profile-https-signed], [TLS][dnspod-dns-profile-tls-signed]                               | [HTTPS][dnspod-dns-profile-https], [TLS][dnspod-dns-profile-tls]                                   |
| [FDN][fdn-dns]                                                                       | 🇫🇷    | 否   | 由法國資料網路營運                                                                   |                                                                                                              | [HTTPS][fdn-https], [TLS][fdn-tls]                                                                 |
| [FFMUC-DNS][ffmucdns]                                                                | 🇩🇪    | 否   | FFMUC free DNS servers provided by Freifunk München.                                 |                                                                                                              | [HTTPS][ffmuc-profile-https], [TLS][ffmuc-profile-tls]                                             |
| [Google 公共 DNS][google-dns]                                                        | 🇺🇸    | 否   | 由谷歌公司營運                                                                       | [HTTPS][google-dns-profile-https-signed], [TLS][google-dns-profile-tls-signed]                               | [HTTPS][google-dns-profile-https], [TLS][google-dns-profile-tls]                                   |
| [keweonDNS][keweondns]                                                               | 🇩🇪    | 否   | 由 Aviontex 營運，阻擋廣告和追蹤器                                                   | [HTTPS][keweondns-profile-https-signed], [TLS][keweondns-profile-tls-signed]                                 | [HTTPS][keweondns-profile-https], [TLS][keweondns-profile-tls]                                     |
| [Mullvad DNS][mullvad-dns]                                                           | 🇸🇪    | 是   | 由 Mullvad VPN AB 營運                                                               | [HTTPS][mullvad-dns-profile-https-signed]                                                                    | [HTTPS][mullvad-dns-profile-https]                                                                 |
| [Mullvad DNS 廣告阻擋][mullvad-dns]                                                  | 🇸🇪    | 是   | 由 Mullvad VPN AB 營運，阻擋廣告和追蹤器                                             | [HTTPS][mullvad-dns-adblock-profile-https-signed]                                                            | [HTTPS][mullvad-dns-adblock-profile-https]                                                         |
| [OpenDNS 標準版][opendns]                                                            | 🇺🇸    | 否   | 由思科 OpenDNS 營運                                                                  | [HTTPS][opendns-standard-profile-https-signed]                                                               | [HTTPS][opendns-standard-profile-https]                                                            |
| [OpenDNS 家庭盾][opendns]                                                            | 🇺🇸    | 是   | 由思科 OpenDNS 營運，阻擋惡意軟體和成人內容                                          | [HTTPS][opendns-familyshield-profile-https-signed]                                                           | [HTTPS][opendns-familyshield-profile-https]                                                        |
| [Quad9][quad9]                                                                       | 🇨🇭    | 是   | 由 Quad9 基金會營運，阻擋惡意軟體                                                    | [HTTPS][quad9-profile-https-signed], [TLS][quad9-profile-tls-signed]                                         | [HTTPS][quad9-profile-https], [TLS][quad9-profile-tls]                                             |
| [Quad9 帶 ECS][quad9]                                                                | 🇨🇭    | 是   | 由 Quad9 基金會營運，支援 ECS，阻擋惡意軟體                                          | [HTTPS][quad9-ecs-profile-https-signed], [TLS][quad9-ecs-profile-tls-signed]                                 | [HTTPS][quad9-ecs-profile-https], [TLS][quad9-ecs-profile-tls]                                     |
| [Quad9 無過濾][quad9]                                                                | 🇨🇭    | 否   | 由 Quad9 基金會營運                                                                  |                                                                                                              | [HTTPS][quad9-profile-unfiltered-https], [TLS][quad9-profile-unfiltered-tls]                       |
| [Tiarap][tiarap]                                                                     | 🇸🇬 🇺🇸 | 是   | 由 Tiarap 公司營運，阻擋廣告、追蹤器、釣魚和惡意軟體                                 | [HTTPS][tiarap-profile-https-signed], [TLS][tiarap-profile-tls-signed]                                       | [HTTPS][tiarap-profile-https], [TLS][tiarap-profile-tls]                                           |

## 安裝

要使設置在 **iOS**、**iPadOS** 和 **macOS** 中所有的應用程式上生效，你需要安裝設定描述檔。此文件將指引操作系統使用 DoH 或 DoT。注意：僅在系統 Wi-Fi 設定中設置 DNS 伺服器 IP 是不夠的——你需要安裝描述檔。

iOS / iPadOS：使用 Safari 瀏覽器（其他瀏覽器只會下載該文件，不會彈出安裝提示）打開 GitHub 上的 mobileconfig 文件，然後點擊「允許」按鈕，描述檔將完成下載。打開 **系統設定 => 一般 => VPN、DNS 與裝置管理**，選擇已下載的描述檔並點擊「安裝」按鈕。

macOS [（官方文檔）](https://support.apple.com/zh-tw/guide/mac-help/mh35561/)：

1. 下載並保存描述檔，將其重命名為 `NAME.mobileconfig`，而不是 txt 之類的副檔名。
2. 選擇「蘋果」選單 >「系統設定」，按一下側邊欄中的「隱私權和安全性」，然後按一下右側的「描述檔」。（你可能需要向下捲動。）
   安裝期間，系統可能會要求你提供密碼或其他資訊。
3. 在「已下載」區域中，按兩下描述檔。
4. 檢視描述檔內容然後按一下「繼續」、「安裝」或「註冊」來安裝描述檔。

   若 Mac 上已安裝描述檔的較早版本，則以上版本中的設定會取代先前的設定。

## 範圍

這條[額外選項](https://github.com/paulmillr/encrypted-dns/issues/22)似乎可以讓描述文件在系統全域範圍生效。如果有興趣嘗試，請將下面的內容添加到 mobileconfig 文件中：

```xml
<key>PayloadScope</key>
<string>System</string>
```

## 簽署版描述檔

在 `signed` 文件夾中，存放了*稍微過時的*簽署版描述檔。這些描述檔已由 [@Candygoblen123](https://github.com/Candygoblen123) 簽署，因此當你安裝時，介面上會有「已驗證」的提示，此舉還可確保這些描述檔未被篡改。但由於這些描述檔是交由第三方簽署的，因此可能會稍微落後於未簽署的版本。

[備註]: <> (我們建議安裝簽署版的描述檔，因為數位簽章可以確保文件在下載時沒有被修改。)

如要驗證 DNS 解析器的 IP 和主機名，請將描述檔內容與其官方網站的文檔進行比對，描述檔內部結構和屬性在[蘋果開發人員網站](https://developer.apple.com/documentation/devicemanagement/dnssettings)上有詳細講解。如要驗證簽署版的描述檔，請將其下載到本地後用文字編輯器打開，因為 GitHub 會將簽署版描述檔視為二進位檔案而無法直接查看。

## 提交新描述檔

描述檔本質上是文字檔案，將現有的描述檔複製一份並修改其 UUID 即可，請確保在本 README 文件中更新描述檔的相關訊息。

隨機 UUID 除了可以通過網站在線生成，還有很多其他獲取方法：

- 在瀏覽器中按下 `F12` 打開“開發人員工具”，在主控台中執行這段程式碼

```javascript
crypto.randomUUID();
```

- 在 macOS / Linux 終端機中執行此指令

```sh
# 適用於 macOS 和 Linux
uuidgen

# 適用於 Linux
cat /proc/sys/kernel/random/uuid
```

- 在 Powershell 中執行此指令

```powershell
New-Guid
```

[360-dns]: https://sdns.360.net/dnsPublic.html
[360-dns-profile-https]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/360-https.mobileconfig
[adguard-dns-default]: https://adguard-dns.io/kb/general/dns-providers/#default
[adguard-dns-default-profile-https]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/adguard-default-https.mobileconfig
[adguard-dns-default-profile-tls]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/adguard-default-tls.mobileconfig
[adguard-dns-self]: https://adguard-dns.io/kb/general/dns-providers/#default
[adguard-dns-self-profile-https]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/adguard-self-https.mobileconfig
[adguard-dns-self-profile-tls]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/adguard-self-tls.mobileconfig
[adguard-dns-family]: https://adguard-dns.io/kb/general/dns-providers/#family-protection
[adguard-dns-family-profile-https]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/adguard-family-https.mobileconfig
[adguard-dns-family-profile-tls]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/adguard-family-tls.mobileconfig
[adguard-dns-unfiltered]: https://adguard-dns.io/kb/general/dns-providers/#non-filtering
[adguard-dns-unfiltered-profile-https]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/adguard-nofilter-https.mobileconfig
[adguard-dns-unfiltered-profile-tls]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/adguard-nofilter-tls.mobileconfig
[alekberg-dns]: https://alekberg.net
[alekberg-dns-profile-https]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/alekberg-https.mobileconfig
[aliyun-dns]: https://www.alidns.com/
[aliyun-dns-profile-https]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/alibaba-https.mobileconfig
[aliyun-dns-profile-tls]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/alibaba-tls.mobileconfig
[blahdns]: https://blahdns.com/
[blahdns-cdn-filtered-profile-https]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/blahdns-cdn-adblock-doh1.mobileconfig
[blahdns-cdn-unfiltered-profile-https]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/blahdns-cdn-unfiltered-doh1.mobileconfig
[blahdns-germany-profile-https]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/blahdns-germany-doh.mobileconfig
[blahdns-singapore-profile-https]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/blahdns-singapore-doh.mobileconfig
[canadian-shield]: https://www.cira.ca/cybersecurity-services/canadian-shield/configure/summary-cira-canadian-shield-dns-resolver-addresses
[canadian-shield-private-profile-https]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/canadianshield-private-https.mobileconfig
[canadian-shield-private-profile-tls]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/canadianshield-private-tls.mobileconfig
[canadian-shield-protected-profile-https]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/canadianshield-protected-https.mobileconfig
[canadian-shield-protected-profile-tls]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/canadianshield-protected-tls.mobileconfig
[canadian-shield-family-profile-https]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/canadianshield-family-https.mobileconfig
[canadian-shield-family-profile-tls]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/canadianshield-family-tls.mobileconfig
[cleanbrowsing]: https://cleanbrowsing.org/filters/
[cleanbrowsing-family-https]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/cleanbrowsing-family-https.mobileconfig
[cleanbrowsing-family-tls]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/cleanbrowsing-family-tls.mobileconfig
[cleanbrowsing-adult-https]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/cleanbrowsing-adult-https.mobileconfig
[cleanbrowsing-adult-tls]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/cleanbrowsing-adult-tls.mobileconfig
[cleanbrowsing-security-https]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/cleanbrowsing-security-https.mobileconfig
[cleanbrowsing-security-tls]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/cleanbrowsing-security-tls.mobileconfig
[cloudflare-dns]: https://developers.cloudflare.com/1.1.1.1/encryption/
[cloudflare-dns-profile-https]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/cloudflare-https.mobileconfig
[cloudflare-dns-profile-tls]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/cloudflare-tls.mobileconfig
[cloudflare-dns-security-profile-https]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/cloudflare-malware-https.mobileconfig
[cloudflare-dns-family]: https://developers.cloudflare.com/1.1.1.1/setup/#1111-for-families
[cloudflare-dns-family-profile-https]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/cloudflare-family-https.mobileconfig
[dnspod-dns]: https://www.dnspod.com/products/public.dns
[dnspod-dns-profile-https]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/dnspod-https.mobileconfig
[dnspod-dns-profile-tls]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/dnspod-tls.mobileconfig
[fdn-dns]: https://www.fdn.fr/actions/dns/
[fdn-https]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/fdn-https.mobileconfig
[fdn-tls]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/fdn-tls.mobileconfig
[google-dns]: https://developers.google.com/speed/public-dns/docs/secure-transports
[google-dns-profile-https]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/google-https.mobileconfig
[google-dns-profile-tls]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/google-tls.mobileconfig
[keweondns]: https://forum.xda-developers.com/t/keweondns-info-facts-and-what-is-keweon-actually.4576651/
[keweondns-profile-https]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/keweondns-doh.mobileconfig
[keweondns-profile-tls]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/keweondns-dot.mobileconfig
[mullvad-dns]: https://mullvad.net/help/dns-over-https-and-dns-over-tls/
[mullvad-dns-profile-https]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/mullvad-doh.mobileconfig
[mullvad-dns-adblock-profile-https]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/mullvad-adblock-doh.mobileconfig
[opendns]: https://support.opendns.com/hc/articles/360038086532
[opendns-standard-profile-https]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/opendns-https.mobileconfig
[opendns-familyshield-profile-https]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/opendns-family-https.mobileconfig
[quad9]: https://www.quad9.net/news/blog/doh-with-quad9-dns-servers/
[quad9-profile-https]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/quad9-https.mobileconfig
[quad9-profile-tls]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/quad9-tls.mobileconfig
[quad9-ecs-profile-https]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/quad9-ECS-https.mobileconfig
[quad9-ecs-profile-tls]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/quad9-ECS-tls.mobileconfig
[quad9-profile-unfiltered-https]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/quad9-nofilter-https.mobileconfig
[quad9-profile-unfiltered-tls]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/quad9-nofilter-tls.mobileconfig
[tiarap]: https://doh.tiar.app
[tiarap-profile-https]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/tiarapp-https.mobileconfig
[tiarap-profile-tls]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/tiarapp-tls.mobileconfig
[dns4eu]: https://www.joindns4.eu/for-public
[dns4eu-profile-https]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/dns4eu-https.mobileconfig
[dns4eu-profile-tls]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/dns4eu-tls.mobileconfig
[dns4eu-malware]: https://www.joindns4.eu/for-public
[dns4eu-profile-malware-https]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/dns4eu-malware-https.mobileconfig
[dns4eu-profile-malware-tls]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/dns4eu-malware-tls.mobileconfig
[dns4eu-protective-ads]: https://www.joindns4.eu/for-public
[dns4eu-profile-protective-ads-https]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/dns4eu-protective-ads-https.mobileconfig
[dns4eu-profile-protective-ads-tls]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/dns4eu-protective-ads-tls.mobileconfig
[dns4eu-protective-child]: https://www.joindns4.eu/for-public
[dns4eu-profile-protective-child-https]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/dns4eu-protective-child-https.mobileconfig
[dns4eu-profile-protective-child-tls]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/dns4eu-protective-child-tls.mobileconfig
[dns4eu-protective-child-ads]: https://www.joindns4.eu/for-public
[dns4eu-profile-protective-child-ads-https]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/dns4eu-protective-child-ads-https.mobileconfig
[dns4eu-profile-protective-child-ads-tls]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/dns4eu-protective-child-ads-tls.mobileconfig
[ffmucdns]: https://ffmuc.net/wiki/knb:dohdot_en
[ffmuc-profile-https]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/ffmucdns-https.mobileconfig
[ffmuc-profile-tls]: https://github.com/paulmillr/encrypted-dns/raw/master/profiles/ffmucdns-tls.mobileconfig
[360-dns-profile-https-signed]: https://github.com/paulmillr/encrypted-dns/raw/master/signed/360-https.mobileconfig
[adguard-dns-default-profile-https-signed]: https://github.com/paulmillr/encrypted-dns/raw/master/signed/adguard-default-https.mobileconfig
[adguard-dns-default-profile-tls-signed]: https://github.com/paulmillr/encrypted-dns/raw/master/signed/adguard-default-tls.mobileconfig
[adguard-dns-family-profile-https-signed]: https://github.com/paulmillr/encrypted-dns/raw/master/signed/adguard-family-https.mobileconfig
[adguard-dns-family-profile-tls-signed]: https://github.com/paulmillr/encrypted-dns/raw/master/signed/adguard-family-tls.mobileconfig
[adguard-dns-unfiltered-profile-https-signed]: https://github.com/paulmillr/encrypted-dns/raw/master/signed/adguard-nofilter-https.mobileconfig
[adguard-dns-unfiltered-profile-tls-signed]: https://github.com/paulmillr/encrypted-dns/raw/master/signed/adguard-nofilter-tls.mobileconfig
[alekberg-dns-profile-https-signed]: https://github.com/paulmillr/encrypted-dns/raw/master/signed/alekberg-https.mobileconfig
[aliyun-dns-profile-https-signed]: https://github.com/paulmillr/encrypted-dns/raw/master/signed/alibaba-https.mobileconfig
[aliyun-dns-profile-tls-signed]: https://github.com/paulmillr/encrypted-dns/raw/master/signed/alibaba-tls.mobileconfig
[blahdns-cdn-filtered-profile-https-signed]: https://github.com/paulmillr/encrypted-dns/raw/master/signed/blahdns-cdn-adblock-doh1.mobileconfig
[blahdns-cdn-unfiltered-profile-https-signed]: https://github.com/paulmillr/encrypted-dns/raw/master/signed/blahdns-cdn-unfiltered-doh1.mobileconfig
[blahdns-germany-profile-https-signed]: https://github.com/paulmillr/encrypted-dns/raw/master/signed/blahdns-germany-doh.mobileconfig
[blahdns-singapore-profile-https-signed]: https://github.com/paulmillr/encrypted-dns/raw/master/signed/blahdns-singapore-doh.mobileconfig
[canadian-shield-private-profile-https-signed]: https://github.com/paulmillr/encrypted-dns/raw/master/signed/canadianshield-private-https.mobileconfig
[canadian-shield-private-profile-tls-signed]: https://github.com/paulmillr/encrypted-dns/raw/master/signed/canadianshield-private-tls.mobileconfig
[canadian-shield-protected-profile-https-signed]: https://github.com/paulmillr/encrypted-dns/raw/master/signed/canadianshield-protected-https.mobileconfig
[canadian-shield-protected-profile-tls-signed]: https://github.com/paulmillr/encrypted-dns/raw/master/signed/canadianshield-protected-tls.mobileconfig
[canadian-shield-family-profile-https-signed]: https://github.com/paulmillr/encrypted-dns/raw/master/signed/canadianshield-family-https.mobileconfig
[canadian-shield-family-profile-tls-signed]: https://github.com/paulmillr/encrypted-dns/raw/master/signed/canadianshield-family-tls.mobileconfig
[cloudflare-dns-profile-https-signed]: https://github.com/paulmillr/encrypted-dns/raw/master/signed/cloudflare-https.mobileconfig
[cloudflare-dns-profile-tls-signed]: https://github.com/paulmillr/encrypted-dns/raw/master/signed/cloudflare-tls.mobileconfig
[cloudflare-dns-security-profile-https-signed]: https://github.com/paulmillr/encrypted-dns/raw/master/signed/cloudflare-malware-https.mobileconfig
[cloudflare-dns-family-profile-https-signed]: https://github.com/paulmillr/encrypted-dns/raw/master/signed/cloudflare-family-https.mobileconfig
[dnspod-dns-profile-https-signed]: https://github.com/paulmillr/encrypted-dns/raw/master/signed/dnspod-https.mobileconfig
[dnspod-dns-profile-tls-signed]: https://github.com/paulmillr/encrypted-dns/raw/master/signed/dnspod-tls.mobileconfig
[google-dns-profile-https-signed]: https://github.com/paulmillr/encrypted-dns/raw/master/signed/google-https.mobileconfig
[google-dns-profile-tls-signed]: https://github.com/paulmillr/encrypted-dns/raw/master/signed/google-tls.mobileconfig
[keweondns-profile-https-signed]: https://github.com/paulmillr/encrypted-dns/raw/master/signed/keweondns-doh.mobileconfig
[keweondns-profile-tls-signed]: https://github.com/paulmillr/encrypted-dns/raw/master/signed/keweondns-dot.mobileconfig
[mullvad-dns-profile-https-signed]: https://github.com/paulmillr/encrypted-dns/raw/master/signed/mullvad-doh.mobileconfig
[mullvad-dns-adblock-profile-https-signed]: https://github.com/paulmillr/encrypted-dns/raw/master/signed/mullvad-adblock-doh.mobileconfig
[opendns-standard-profile-https-signed]: https://github.com/paulmillr/encrypted-dns/raw/master/signed/opendns-https.mobileconfig
[opendns-familyshield-profile-https-signed]: https://github.com/paulmillr/encrypted-dns/raw/master/signed/opendns-family-https.mobileconfig
[quad9-profile-https-signed]: https://github.com/paulmillr/encrypted-dns/raw/master/signed/quad9-https.mobileconfig
[quad9-profile-tls-signed]: https://github.com/paulmillr/encrypted-dns/raw/master/signed/quad9-tls.mobileconfig
[quad9-ecs-profile-https-signed]: https://github.com/paulmillr/encrypted-dns/raw/master/signed/quad9-ECS-https.mobileconfig
[quad9-ecs-profile-tls-signed]: https://github.com/paulmillr/encrypted-dns/raw/master/signed/quad9-ECS-tls.mobileconfig
[tiarap-profile-https-signed]: https://github.com/paulmillr/encrypted-dns/raw/master/signed/tiarapp-https.mobileconfig
[tiarap-profile-tls-signed]: https://github.com/paulmillr/encrypted-dns/raw/master/signed/tiarapp-tls.mobileconfig
