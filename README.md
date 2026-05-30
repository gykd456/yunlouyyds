<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>云篓 - 隐私政策</title>
  <meta name="description" content="云篓浏览器扩展隐私政策。说明云篓如何处理本地素材、WebDAV 同步、浏览器权限和用户数据。" />
  <style>
    :root {
      --bg: #f8fbf3;
      --card: rgba(255, 255, 255, 0.82);
      --text: #1f2a24;
      --muted: #6e7d73;
      --green: #8ad63f;
      --green-dark: #4f8f24;
      --line: rgba(93, 128, 81, 0.16);
      --cream: #fff8e8;
      --danger: #ff7777;
      --shadow: 0 22px 60px rgba(63, 100, 64, 0.12);
      --radius: 28px;
    }

    * { box-sizing: border-box; }

    html { scroll-behavior: smooth; }

    body {
      margin: 0;
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", "PingFang SC", "Microsoft YaHei", Arial, sans-serif;
      color: var(--text);
      line-height: 1.8;
      background:
        radial-gradient(circle at 8% 5%, rgba(169, 230, 255, 0.42), transparent 28%),
        radial-gradient(circle at 90% 12%, rgba(199, 245, 145, 0.48), transparent 30%),
        linear-gradient(180deg, #fffdf7 0%, var(--bg) 44%, #f3faf0 100%);
    }

    .page {
      width: min(1120px, calc(100% - 40px));
      margin: 0 auto;
      padding: 34px 0 64px;
    }

    .hero {
      position: relative;
      overflow: hidden;
      display: grid;
      grid-template-columns: 1.05fr 0.95fr;
      gap: 36px;
      align-items: center;
      padding: 42px;
      border: 1px solid var(--line);
      border-radius: 36px;
      background: rgba(255,255,255,0.72);
      box-shadow: var(--shadow);
      backdrop-filter: blur(18px);
    }

    .hero::before {
      content: "";
      position: absolute;
      inset: auto -80px -120px auto;
      width: 360px;
      height: 260px;
      background: radial-gradient(circle, rgba(138,214,63,.28), transparent 68%);
      pointer-events: none;
    }

    .brand {
      display: flex;
      align-items: center;
      gap: 14px;
      margin-bottom: 28px;
    }

    .logo {
      width: 58px;
      height: 58px;
      border-radius: 18px;
      display: grid;
      place-items: center;
      background: #fff;
      border: 1px solid var(--line);
      box-shadow: 0 10px 26px rgba(49,83,48,.08);
      font-size: 30px;
    }

    .brand-name {
      font-size: 26px;
      font-weight: 800;
      letter-spacing: .02em;
    }

    .tag {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      padding: 7px 13px;
      border-radius: 999px;
      background: #ecffd8;
      color: var(--green-dark);
      font-weight: 700;
      font-size: 14px;
      margin-bottom: 18px;
    }

    h1 {
      margin: 0;
      font-size: clamp(36px, 6vw, 64px);
      line-height: 1.05;
      letter-spacing: -0.05em;
    }

    .hero p {
      margin: 20px 0 0;
      max-width: 620px;
      color: var(--muted);
      font-size: 18px;
    }

    .summary-card {
      position: relative;
      padding: 28px;
      border-radius: 28px;
      background: linear-gradient(180deg, #ffffff, #fbfff5);
      border: 1px solid var(--line);
      box-shadow: 0 18px 42px rgba(70, 105, 65, 0.1);
    }

    .summary-card h2 {
      margin: 0 0 12px;
      font-size: 22px;
    }

    .summary-card ul {
      margin: 0;
      padding-left: 20px;
      color: var(--muted);
    }

    .meta {
      margin-top: 18px;
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
    }

    .pill {
      padding: 7px 12px;
      border-radius: 999px;
      background: var(--cream);
      border: 1px solid rgba(196, 153, 67, .16);
      color: #80683c;
      font-weight: 650;
      font-size: 13px;
    }

    .layout {
      display: grid;
      grid-template-columns: 260px 1fr;
      gap: 28px;
      margin-top: 28px;
      align-items: start;
    }

    nav {
      position: sticky;
      top: 18px;
      padding: 18px;
      border-radius: 24px;
      background: rgba(255,255,255,.72);
      border: 1px solid var(--line);
      box-shadow: 0 14px 40px rgba(62,94,61,.08);
    }

    nav strong {
      display: block;
      margin-bottom: 10px;
      font-size: 15px;
    }

    nav a {
      display: block;
      padding: 9px 11px;
      border-radius: 14px;
      color: var(--muted);
      text-decoration: none;
      font-size: 14px;
    }

    nav a:hover {
      color: var(--green-dark);
      background: #f1fbeb;
    }

    main {
      display: grid;
      gap: 18px;
    }

    section {
      padding: 30px;
      border-radius: var(--radius);
      background: var(--card);
      border: 1px solid var(--line);
      box-shadow: 0 12px 36px rgba(70, 100, 60, .07);
      backdrop-filter: blur(16px);
    }

    section h2 {
      display: flex;
      align-items: center;
      gap: 10px;
      margin: 0 0 14px;
      font-size: 24px;
      letter-spacing: -0.02em;
    }

    section h2 span {
      width: 32px;
      height: 32px;
      flex: 0 0 32px;
      display: grid;
      place-items: center;
      border-radius: 12px;
      background: #ecffd8;
      color: var(--green-dark);
      font-size: 16px;
    }

    p { margin: 0 0 12px; }

    ul { margin: 10px 0 0; padding-left: 22px; }

    li { margin: 6px 0; }

    .notice {
      padding: 16px 18px;
      border-radius: 18px;
      background: #fff8e8;
      border: 1px solid rgba(211, 168, 75, .18);
      color: #665331;
      margin-top: 12px;
    }

    .table-wrap {
      overflow-x: auto;
      border: 1px solid var(--line);
      border-radius: 18px;
      background: #fff;
      margin-top: 14px;
    }

    table {
      width: 100%;
      border-collapse: collapse;
      min-width: 620px;
      font-size: 15px;
    }

    th, td {
      padding: 14px 16px;
      text-align: left;
      border-bottom: 1px solid var(--line);
      vertical-align: top;
    }

    th {
      background: #f3fbea;
      color: #3d5e2b;
      white-space: nowrap;
    }

    tr:last-child td { border-bottom: 0; }

    code {
      padding: 2px 7px;
      border-radius: 8px;
      background: #f2f5ef;
      color: #305222;
      font-family: ui-monospace, SFMono-Regular, Menlo, Consolas, monospace;
      font-size: .92em;
    }

    footer {
      margin-top: 28px;
      padding: 28px;
      border-radius: 28px;
      color: var(--muted);
      text-align: center;
      background: rgba(255,255,255,.62);
      border: 1px solid var(--line);
    }

    .contact {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 8px;
      color: var(--green-dark);
      font-weight: 700;
      text-decoration: none;
      word-break: break-all;
    }

    @media (max-width: 860px) {
      .page {
        width: min(100% - 24px, 720px);
        padding: 18px 0 36px;
      }

      .hero {
        grid-template-columns: 1fr;
        padding: 26px;
        border-radius: 28px;
        gap: 22px;
      }

      .brand { margin-bottom: 18px; }

      .logo {
        width: 50px;
        height: 50px;
        font-size: 26px;
      }

      .brand-name { font-size: 22px; }

      .hero p {
        font-size: 16px;
      }

      .summary-card {
        padding: 22px;
      }

      .layout {
        grid-template-columns: 1fr;
      }

      nav {
        position: static;
        display: grid;
        grid-template-columns: repeat(2, minmax(0, 1fr));
        gap: 6px;
      }

      nav strong {
        grid-column: 1 / -1;
      }

      nav a {
        background: rgba(247, 252, 242, .8);
      }

      section {
        padding: 22px;
        border-radius: 22px;
      }

      section h2 {
        font-size: 21px;
      }
    }

    @media (max-width: 520px) {
      .page {
        width: 100%;
        padding: 0 0 28px;
      }

      .hero {
        border-radius: 0 0 30px 30px;
        border-left: 0;
        border-right: 0;
        padding: 24px 18px 28px;
      }

      h1 {
        font-size: 40px;
      }

      .layout {
        padding: 0 12px;
      }

      nav {
        grid-template-columns: 1fr;
        padding: 14px;
      }

      section {
        padding: 18px;
      }

      .table-wrap {
        margin-left: -4px;
        margin-right: -4px;
      }

      footer {
        margin-left: 12px;
        margin-right: 12px;
      }
    }
  </style>
</head>

<body>
  <div class="page">
    <header class="hero">
      <div>
        <div class="brand">
          <div class="logo" aria-hidden="true">🐟</div>
          <div>
            <div class="brand-name">云篓</div>
            <div style="color:var(--muted);font-size:14px;">Yunlou Browser Extension</div>
          </div>
        </div>
        <div class="tag">隐私政策 · Privacy Policy</div>
        <h1>你的网页素材，<br />默认只在本地。</h1>
        <p>云篓用于收集、暂存、管理和复用网页上的图片、视频、文字和文件。我们不会出售用户数据，不会用于广告追踪，也不会把素材上传到开发者服务器。</p>
        <div class="meta">
          <span class="pill">生效日期：2026-05-31</span>
          <span class="pill">适用于 Chrome / Edge 扩展</span>
          <span class="pill">本地优先 · WebDAV 可选</span>
        </div>
      </div>

      <div class="summary-card">
        <h2>核心隐私原则</h2>
        <ul>
          <li>只处理用户主动保存、复制、下载或同步的素材。</li>
          <li>素材默认保存在用户浏览器本地 IndexedDB。</li>
          <li>WebDAV 为用户自配服务，开发者不会接收账号密码。</li>
          <li>不收集与素材保存功能无关的浏览历史。</li>
        </ul>
      </div>
    </header>

    <div class="layout">
      <nav aria-label="目录">
        <strong>目录</strong>
        <a href="#overview">1. 概述</a>
        <a href="#data">2. 我们处理的数据</a>
        <a href="#storage">3. 本地存储</a>
        <a href="#webdav">4. WebDAV 同步</a>
        <a href="#permissions">5. 权限用途</a>
        <a href="#usage">6. 数据使用限制</a>
        <a href="#sharing">7. 数据共享</a>
        <a href="#security">8. 数据安全</a>
        <a href="#rights">9. 用户权利</a>
        <a href="#contact">10. 联系方式</a>
      </nav>

      <main>
        <section id="overview">
          <h2><span>1</span>概述</h2>
          <p>云篓（Yunlou）是一款 Chrome / Edge MV3 浏览器扩展，定位为网页素材中转站。用户可以把网页上的图片、视频、文字和文件保存到浏览器侧边栏素材库，并在需要时复制、下载或拖拽到其他网页中复用。</p>
          <p>本隐私政策说明云篓如何处理用户数据，以及相关数据如何存储、使用和保护。</p>
        </section>

        <section id="data">
          <h2><span>2</span>我们处理的数据</h2>
          <p>云篓只处理用户主动保存或操作的内容，包括：</p>
          <ul>
            <li>用户主动保存的图片、视频、文字和文件素材；</li>
            <li>素材名称、类型、大小、创建时间、文件夹归属、收藏状态、回收站状态等素材管理信息；</li>
            <li>用户创建的文件夹、分类、界面设置和同步设置；</li>
            <li>用户主动配置的 WebDAV 服务器地址、用户名和密码。</li>
          </ul>
          <div class="notice">云篓不会主动收集用户完整浏览历史，不会记录用户访问网页的列表，也不会将网页内容上传到开发者服务器。</div>
        </section>

        <section id="storage">
          <h2><span>3</span>本地存储</h2>
          <p>默认情况下，云篓保存的素材和素材索引会存储在用户浏览器本地，例如 <code>IndexedDB</code> 和浏览器扩展存储中。</p>
          <p>这些数据不会因为安装云篓而自动上传到开发者服务器。用户更换设备后，默认不会自动同步过去，除非用户主动启用 WebDAV 同步功能。</p>
        </section>

        <section id="webdav">
          <h2><span>4</span>WebDAV 同步</h2>
          <p>云篓提供可选的 WebDAV 同步能力。该功能仅在用户主动配置后启用。</p>
          <ul>
            <li>WebDAV 服务器由用户自行提供和配置。</li>
            <li>WebDAV 用户名和密码仅保存在用户浏览器本地。</li>
            <li>这些凭据仅用于连接用户自行配置的 WebDAV 服务。</li>
            <li>云篓不会将 WebDAV 凭据发送给开发者服务器。</li>
            <li>同步数据会上传到用户自己配置的 WebDAV 服务，而不是云篓开发者服务器。</li>
            <li>用户可以随时删除 WebDAV 配置，删除后云篓将停止访问对应 WebDAV 服务。</li>
          </ul>
        </section>

        <section id="permissions">
          <h2><span>5</span>权限用途</h2>
          <p>云篓请求的浏览器权限仅用于实现扩展的核心功能。</p>
          <div class="table-wrap">
            <table>
              <thead>
                <tr>
                  <th>权限</th>
                  <th>用途说明</th>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <td><code>sidePanel</code></td>
                  <td>用于显示云篓侧边栏主界面，用户可以在侧边栏中查看、分类、收藏、编辑、复制、下载、删除和拖拽复用素材。</td>
                </tr>
                <tr>
                  <td><code>storage</code></td>
                  <td>用于保存扩展设置、文件夹信息、素材索引、收藏状态、回收站状态、界面偏好和同步配置等信息。</td>
                </tr>
                <tr>
                  <td><code>downloads</code></td>
                  <td>用于在用户主动触发下载时，将单个素材、选中素材或全部素材下载到本地浏览器下载目录。</td>
                </tr>
                <tr>
                  <td><code>clipboardWrite</code></td>
                  <td>用于支持用户主动复制文字、图片链接或素材内容，便于在其他网页或编辑器中复用。</td>
                </tr>
                <tr>
                  <td><code>alarms</code></td>
                  <td>用于 WebDAV 同步检查、同步队列处理或其他用户主动启用的定时任务。</td>
                </tr>
                <tr>
                  <td><code>&lt;all_urls&gt;</code></td>
                  <td>用于在用户访问的网页中识别用户主动选择或操作的素材内容，例如悬停保存图片/视频、保存选中文字、区域选择保存和拖拽复用。云篓不会用该权限收集与素材保存功能无关的浏览历史。</td>
                </tr>
              </tbody>
            </table>
          </div>
        </section>

        <section id="usage">
          <h2><span>6</span>数据使用限制</h2>
          <p>云篓处理用户数据仅用于提供以下功能：</p>
          <ul>
            <li>保存、分类、收藏和管理网页素材；</li>
            <li>复制、下载和拖拽复用素材；</li>
            <li>在用户启用 WebDAV 时进行同步；</li>
            <li>维持扩展设置和界面偏好。</li>
          </ul>
          <p>云篓不会将用户数据用于广告、用户画像、信用评估、贷款评估或与素材管理无关的用途。</p>
        </section>

        <section id="sharing">
          <h2><span>7</span>数据共享</h2>
          <p>云篓不会出售用户数据，不会向第三方出售、出租或交易用户数据。</p>
          <p>当用户启用 WebDAV 同步时，素材和索引数据会传输到用户自己配置的 WebDAV 服务。该传输是用户主动配置的同步行为，不经过云篓开发者服务器。</p>
        </section>

        <section id="security">
          <h2><span>8</span>数据安全</h2>
          <p>云篓采用本地优先的设计，尽量减少数据离开用户设备的情况。用户应妥善保管自己的设备、浏览器账号和 WebDAV 服务凭据。</p>
          <p>由于 WebDAV 服务由用户自行配置，相关服务器的安全性、可用性和访问控制由用户及其 WebDAV 服务提供方负责。</p>
        </section>

        <section id="rights">
          <h2><span>9</span>用户权利</h2>
          <p>用户可以在云篓扩展中执行以下操作：</p>
          <ul>
            <li>删除已保存的素材；</li>
            <li>恢复或彻底删除回收站中的素材；</li>
            <li>删除文件夹、收藏状态和扩展设置；</li>
            <li>关闭 WebDAV 同步或删除 WebDAV 配置；</li>
            <li>通过卸载扩展移除扩展相关的本地数据。</li>
          </ul>
        </section>

        <section id="children">
          <h2><span>10</span>儿童隐私</h2>
          <p>云篓不是专门面向儿童的产品。我们不会有意收集儿童的个人信息。如果您认为有儿童个人信息被错误保存，请通过联系方式与开发者沟通。</p>
        </section>

        <section id="changes">
          <h2><span>11</span>政策更新</h2>
          <p>我们可能会根据产品功能、法规要求或审核要求更新本隐私政策。更新后的政策会发布在本页面，并以页面显示的生效日期为准。</p>
        </section>

        <section id="contact">
          <h2><span>12</span>联系方式</h2>
          <p>如您对本隐私政策或云篓的数据处理方式有任何问题，可以通过开发者在 Chrome Web Store、Edge Add-ons 或官方网站中公布的联系方式与我们联系。</p>
          <p>联系邮箱：<a class="contact" href="didi0825@aliyun.com">"didi0825@aliyun.com</a></p>
        </section>
      </main>
    </div>

    <footer>
      <strong>云篓 Yunlou</strong><br />
      网页素材中转站 · 收集、暂存、管理和拖拽复用
    </footer>
  </div>
</body>
</html>
