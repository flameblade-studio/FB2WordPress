# FB2WordPress v1.1.0-rc.2 Preview release notes

> Windows remains the complete product. The macOS and Linux downloads are clearly bounded Preview migration entry points.

## 繁體中文｜修正「設定」視窗開不起來

v1.1.0-rc.1 的 Windows 完整版在按下右下角「設定」時，會在設定視窗出現前跳出系統錯誤；首次啟動時自動開啟的設定視窗也會同樣當機，使新使用者無法完成網站連線設定。原因是語言選單在選項載入前就被指定選取項目。本版改為直接載入四種語言，四種介面語言與未設定語言時都能正常開啟並預選目前語言，且新增自動稽核實際建立設定視窗，防止再次發生。已設定好的網站、帳號與應用程式密碼不受影響，升級後無需重新設定。

本版另修正發布流程：密鑰外洩掃描改用固定版本並核對 SHA-256 的開源 Gitleaks，Linux 封裝工具 appimagetool 改為固定 1.9.1 版與其 SHA-256。這些只影響建置與安全檢查，不改變程式功能。

Windows EXE、兩種 DMG 與 AppImage 均在相符架構的 GitHub 原生 runner 製作，CI 會從每一份最終成品啟動程式並確認至少存活六秒。只有精確 `v1.1.0-rc.N`（`N > 0`）標籤、版本相符且標籤提交屬於 `origin/main` 時，才會彙整 SHA256、各平台 SPDX SBOM 及來源／SBOM 證明，並以本四語文件建立 prerelease；任一成品或驗證失敗都不發布。macOS／Linux 仍只有 Preview 入口，完整搬家流程只在 Windows 完整版可用；這是雲端建置與啟動證據，不是作者持有 macOS／Linux 實機的驗證，也不是正式相容承諾。macOS 版本支援 Intel x64 與 Apple Silicon arm64，兩者皆未簽章。

## 简体中文｜修复“设置”窗口无法打开

v1.1.0-rc.1 的 Windows 完整版在点击右下角“设置”时，会在设置窗口出现前弹出系统错误；首次启动时自动打开的设置窗口也会同样崩溃，使新用户无法完成网站连接设置。原因是语言菜单在选项加载前就被指定选中项。本版改为直接加载四种语言，四种界面语言与未设置语言时都能正常打开并预选当前语言，并新增自动审计实际创建设置窗口，防止再次发生。已设置好的网站、账号与应用程序密码不受影响，升级后无需重新设置。

本版另修复发布流程：密钥泄露扫描改用固定版本并核对 SHA-256 的开源 Gitleaks，Linux 打包工具 appimagetool 改为固定 1.9.1 版与其 SHA-256。这些只影响构建与安全检查，不改变程序功能。

Windows EXE、两种 DMG 与 AppImage 都在架构匹配的 GitHub 原生 runner 中制作，CI 会从每一份最终成品启动程序并确认至少存活六秒。只有标签严格匹配 `v1.1.0-rc.N`（`N > 0`）、版本一致且标签提交属于 `origin/main` 时，才会汇总 SHA256、各平台 SPDX SBOM 与来源／SBOM 证明，并使用本四语文件创建 prerelease；任一成品或验证失败都不会发布。macOS／Linux 仍只有 Preview 入口，完整迁移流程只在 Windows 完整版中可用；这是云端构建及启动证据，不是作者在 macOS／Linux 实机上的验证，也不是正式兼容承诺。macOS 版本支持 Intel x64 与 Apple Silicon arm64，两者均未签名。

## English | The Settings window opens again

In v1.1.0-rc.1, clicking **Settings** in the full Windows application showed a system error before the settings window appeared, and the settings window opened automatically on first launch crashed the same way, so new users could not finish connecting their site. The language selector was assigned a selection before its items were loaded. This release loads the four languages directly, so the window opens and preselects the current language in all four interface languages and with no language set, and a new automated audit actually constructs the settings window to prevent a recurrence. Existing site, account, and application-password settings are untouched; no reconfiguration is needed after upgrading.

This release also repairs the release pipeline: the secret scan now uses the version-pinned, SHA-256-verified open-source Gitleaks CLI, and the Linux packaging tool appimagetool is pinned to the tagged 1.9.1 release and its SHA-256. These affect only builds and security checks, not application behavior.

The Windows EXE, both DMGs, and the AppImage are produced on matching native GitHub runners. CI launches every final package and requires it to remain alive for at least six seconds. Only an exact `v1.1.0-rc.N` tag (`N > 0`) whose version matches the source and whose commit belongs to `origin/main` can aggregate SHA256, per-platform SPDX SBOMs, and provenance/SBOM attestations, then create a prerelease from this four-language file. Any artifact or verification failure prevents publication. macOS and Linux remain Preview entry points only; the complete migration workflow is available only in the full Windows application. This proves cloud build and startup only. It is not author-owned real-device validation and not a formal compatibility claim. The macOS downloads cover Intel x64 and Apple Silicon arm64, both unsigned.

## 日本語｜「設定」画面が開かない問題を修正

v1.1.0-rc.1 の Windows 完全版では、右下の「設定」を押すと設定画面が表示される前にシステムエラーが出ていました。初回起動時に自動で開く設定画面も同様に落ちるため、新しい利用者はサイト接続の設定を完了できませんでした。原因は、言語選択欄の項目を読み込む前に選択を指定していたことです。本版では4つの言語を直接読み込むため、4つの表示言語と言語未設定のすべてで設定画面が開き、現在の言語が選択されます。設定画面を実際に作成する自動監査も追加し、再発を防ぎます。設定済みのサイト、アカウント、アプリケーションパスワードには影響せず、更新後に設定し直す必要はありません。

本版ではリリース手順も修正しました。シークレット漏えいスキャンは固定版で SHA-256 を照合するオープンソースの Gitleaks を使い、Linux パッケージ作成ツール appimagetool はタグ付き 1.9.1 版とその SHA-256 に固定しました。これらはビルドとセキュリティ検査のみに関わり、アプリの動作は変わりません。

Windows EXE、2種類の DMG、AppImage は、対応するネイティブ GitHub runner で作成します。CI は各最終成果物からアプリを起動し、6秒以上存続することを確認します。`v1.1.0-rc.N`（`N > 0`）に厳密一致し、ソースのバージョンとも一致し、タグの commit が `origin/main` に含まれる場合に限り、SHA256、各プラットフォームの SPDX SBOM、来歴／SBOM 証明をまとめ、この4言語ファイルから prerelease を作成します。成果物または検証のどれか一つでも失敗すれば公開しません。macOS／Linux は引き続き Preview の入口のみで、完全な移行フローは Windows 完全版だけで利用できます。これはクラウド上のビルドと起動の証拠に限られ、作者所有の macOS／Linux 実機検証でも正式な互換性表明でもありません。macOS 版は Intel x64 と Apple Silicon arm64 の両方に対応し、どちらも未署名です。
