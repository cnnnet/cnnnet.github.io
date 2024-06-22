<div class="markdown-body" id="postBody"><div class="markdown-alert markdown-alert-tip"><p class="markdown-alert-title"><svg class="octicon octicon-light-bulb mr-2" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="M8 1.5c-2.363 0-4 1.69-4 3.75 0 .984.424 1.625.984 2.304l.214.253c.223.264.47.556.673.848.284.411.537.896.621 1.49a.75.75 0 0 1-1.484.211c-.04-.282-.163-.547-.37-.847a8.456 8.456 0 0 0-.542-.68c-.084-.1-.173-.205-.268-.32C3.201 7.75 2.5 6.766 2.5 5.25 2.5 2.31 4.863 0 8 0s5.5 2.31 5.5 5.25c0 1.516-.701 2.5-1.328 3.259-.095.115-.184.22-.268.319-.207.245-.383.453-.541.681-.208.3-.33.565-.37.847a.751.751 0 0 1-1.485-.212c.084-.593.337-1.078.621-1.489.203-.292.45-.584.673-.848.075-.088.147-.173.213-.253.561-.679.985-1.32.985-2.304 0-2.06-1.637-3.75-4-3.75ZM5.75 12h4.5a.75.75 0 0 1 0 1.5h-4.5a.75.75 0 0 1 0-1.5ZM6 15.25a.75.75 0 0 1 .75-.75h2.5a.75.75 0 0 1 0 1.5h-2.5a.75.75 0 0 1-.75-.75Z"></path></svg>Tip</p>
<h3>节点：</h3>
</div>
<p><a href="https://github.com/3Kmfi6HP/EDtunnel">3K 大佬改写的项目</a><br>
<a href="https://github.com/zizifn/edgetunnel/blob/main/src/worker-vless.js">Zizifn 大佬原创项目</a><br>
<a href="https://github.com/mjjonone/sub-worker/blob/main/_worker.js">部署自定义订阅服务</a></p>
<h3>建站：</h3>
<p><strong>通过 Workers 搭建博客</strong><br>
方案一：利用 worker 的 KV 作为数据库搭建博客：<a href="https://github.com/gdtool/cloudflare-workers-blog">源码</a>，<a href="https://cfblog.661212.xyz/article/000003/cfblog-plus.html" rel="nofollow">安装教程</a><br>
方案二：利用 workers+github 搭建博客系统:<a href="https://github.com/kasuganosoras/cloudflare-worker-blog">源码</a></p>
<p><strong>通过 Workers 搭建导航站：</strong><br>
利用 worker 搭建导航站：<a href="https://github.com/sleepwood/CF-Worker-Dir">源码</a></p>
<p><strong>利用 Workers 搭建图床：</strong><br>
<a href="https://github.com/iiop123/workers-image-hosting">源码</a><br>
<a href="https://img.231516.xyz/" rel="nofollow">示例</a></p>
<p><strong>通过 Workers 搭建短网址服务：</strong><br>
<a href="https://github.com/igengdu/short/">源码 1 </a>（推荐，<a href="https://d.igdu.xyz/" rel="nofollow">示例</a>免费短网址服务即是基于此开源项目）<br>
<a href="https://github.com/crazypeace/Url-Shorten-Worker">源码 2</a>，<a href="https://zelikk.blogspot.com/2022/07/url-shorten-worker-hide-tutorial.html" rel="nofollow">教程</a><br>
<a href="https://github.com/xyTom/Url-Shorten-Worker/">源码 3</a><br>
<a href="https://github.com/Closty/duanwangzhi">源码 4</a><br>
<a href="https://github.com/Likenttt/eastlake-cloudflare-worker-short-url">源码 5</a>，<a href="https://blog.661212.xyz/index.php/archives/4/" rel="nofollow">教程</a></p>
<p><strong>通过 workers 等监控网站状态：</strong><br>
<a href="https://github.com/eidam/cf-workers-status-page">源码</a>（也可以通过 Uptimerobot 实现网站健康状态监控，<a href="https://github.com/yb/uptime-status">源码</a>）<br>
<a href="https://linux.do/t/topic/10601" rel="nofollow">教程</a></p>
<p><strong>通过 workers 等搭建临时邮箱：</strong><br>
<a href="https://github.com/dreamhunter2333/cloudflare_temp_email">源码</a></p>
<p><strong>通过 workers 等搭建 RSS 订阅生成器：</strong><br>
<a href="https://github.com/yllhwa/RSSWorker">源码</a>内含教程</p>
<p><strong>通过 workers 等部署 Copilot 服务：</strong><br>
Copilot（原 New Bing）可以试用 ChatGPT４，目前通过 Workers 就可以部署本地可用的 Copilot 服务。<br>
<a href="https://github.com/Harry-zklcdc/go-proxy-bingai">源码</a>　内含教程<br>
<a href="https://bingai-cfwk.zklcdc.xyz/web/#/" rel="nofollow">试用示例</a><br>
<a href="https://github.com/Harry-zklcdc/go-proxy-bingai/wiki/%E6%BC%94%E7%A4%BA%E7%AB%99">其他方式部署 Copilot 的试用网址</a></p>
<p><strong>通过 workers 等部署 Telegram Bot 服务：</strong><br>
<a href="https://github.com/Tsuk1ko/cfworker-telegraf-template">源码</a><br>
<a href="https://moe.best/tutorial/cfworker-telegraf-tgbot.html" rel="nofollow">教程</a></p>
<h3>中转</h3>
<p><a href="https://github.com/hunshcn/gh-proxy">Gh-proxy: Github 项目加速</a><br>
<a href="https://github.com/EtherDream/jsproxy/tree/master/cf-worker">Jsproxy</a><br>
<a href="https://github.com/klightso/Workers-Proxy-1">Workers-Proxy</a>，<a href="https://www.locmjj.com/274.html" rel="nofollow">参考教程</a></p>
<h3>网盘文件列表</h3>
<p><strong>利用 Workers 搭建 Google Drive 列表服务：</strong><br>
<a href="https://github.com/xunyixiangchao/goindex%EF%BC%9B">源码 1</a><br>
<a href="https://github.com/yanzai/goindex%EF%BC%9B">源码 2</a><br>
<a href="https://github.com/Aicirou/goindex-theme-acrou">源码 3</a><br>
<a href="https://github.com/maple3142/GDIndex">源码 4</a></p>
<p><strong>OneDrive-index:</strong><br>
<strong>利用 Workers 搭建 OneDrive 列表服务：</strong><br>
<a href="https://github.com/spencerwooo/onedrive-cf-index">源码 1</a><br>
<a href="https://github.com/Eggsmemory/OneDrive-Index-Cloudflare-Worker-Cht">源码 2</a></p>
<p>转自<a href="https://igdux.com/workers" rel="nofollow">Cloudflare Workers优秀项目收集（持续更新）</a></p></div>