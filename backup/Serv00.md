<div class="post-content"><h1 id="-免费虚拟主机---serv00">🌟 免费虚拟主机 - Serv00<a hidden="" class="anchor" aria-hidden="true" href="#-免费虚拟主机---serv00">#</a></h1>
<ul>
<li>Serv00 是一家提供免费虚拟主机的厂商。它的免费套餐包含:</li>
<li>3GB 存储空间</li>
<li>512MB 内存</li>
<li>不限流量</li>
<li>支持PHP、MySQL等网站开发语言和数据库</li>
<li>提供免费的二级域名</li>
<li>可自定义开放端口</li>
<li>支持SSH访问</li>
<li>要求是每3个月需登录一次控制面板或SSH,避免账号被回收</li>
</ul>
<p>访问官网➡️: <a href="https://www.serv00.com/" target="_blank" rel="noopener">https://www.serv00.com/</a>
<img loading="lazy" src="img_1.png" alt="img_1.png">
</p>
<h2 id="一注册serv00账户名额有限快来注册吧">一、注册serv00账户【⚠️名额有限，快来注册吧！】<a hidden="" class="anchor" aria-hidden="true" href="#一注册serv00账户名额有限快来注册吧">#</a></h2>
<p><img loading="lazy" src="img.png" alt="img.png">

点击「Register an account」进入注册页面,注册之前需要注意三点</p>
<ul>
<li>邮箱必须是真实邮箱，需要激活验证</li>
<li>用户名(Username)自己设置英文就可以，同时也代表域名比如<code>yixiu</code>,域名就是<code>yixiu.serv00.com</code></li>
<li>答案(Answer)不要空着，可填写<code>free</code>
<img loading="lazy" src="img_2.png" alt="img_2.png">

输好之后点击「Create account」,如果用户名被占用了，换一个就行，如果没有被占用就会给你输入的邮箱发送消息。如果页面上方出现以下绿色提示信息，就代表账户注册成功了，去检查邮箱就可以
<img loading="lazy" src="img_3.png" alt="img_3.png">

Serv00欢迎邮件包括所有的重要信息，包括后台管理面板和ssh登录的用户名密码，以及ssh主机名等，邮件千万记得保存，或者复制下来保存都可以。
<img loading="lazy" src="img_4.png" alt="img_4.png">

Serv00后台面板为DevilWeb，用起来还是很方便的，登录的账户密码就是邮件里面的Login和Password，这个账号同样适用其他服务，比如ssh、mysql等。如果没有安装第三方的ssh客户端可以使用windows自带的openssh，mac的终端来登录</li>
</ul>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4;"><code class="language-shell hljs" data-lang="shell"><span style="display:flex;"><span>ssh xxxx@sx.serv00.com
</span></span><span style="display:flex;"><span><span style="color:#75715e"><span class="hljs-meta">#</span><span class="bash">将 xxxx 换成自己的用户名，sx为s1-s4，依照欢迎邮件中的主机名</span></span>
</span></span><span style="display:flex;"><span><span style="color:#75715e"><span class="hljs-meta">#</span><span class="bash">命令行在输入密码的时候是看不到的，输完之后直接点回车就可以</span></span>
</span></span></code></pre><button class="copy-code">复制</button><div class="mac-tool"><div class="mac bb1"></div><div class="mac bb2"></div><div class="mac bb3"></div><div class="language-type">shell</div></div></div><p><strong>⚠️到目前位置serv00账号已经注册好了</strong></p>
<h2 id="二cloudns域名托管到serv00">二、ClouDNS域名托管到serv00<a hidden="" class="anchor" aria-hidden="true" href="#二cloudns域名托管到serv00">#</a></h2>
<ul>
<li>打开<a href="https://www.cloudns.net/" target="_blank" rel="noopener">ClouDNS官网</a>和DevilWEB 网络面板（在邮件里面找面板的链接，用账号密码登录）</li>
<li>删除ClouDNS中域名所有的DNS记录</li>
<li>托管域名到serv00</li>
<li>域名会有双向解析的问题，把托管到serv00之后自动生成的DNS记录全部添加到ClouDNS中</li>
<li>后续如果有新的耳机域名解析也需要添加到ClouDNS</li>
</ul>
<h2 id="三利用freessl生成免费证书">三、利用FreeSSL生成免费证书<a hidden="" class="anchor" aria-hidden="true" href="#三利用freessl生成免费证书">#</a></h2>
<ul>
<li>打开<a href="https://freessl.cn/" target="_blank" rel="noopener">FreeSSL官网</a>(有账号登录，没账号注册，非常简单)</li>
<li>解析的时候注意serv00和ClouDNS都需要解析</li>
</ul>
<h2 id="四搭建vless节点">四、🔗搭建vless节点<a hidden="" class="anchor" aria-hidden="true" href="#四搭建vless节点">#</a></h2>
<h3 id="1配置开启权限">1，配置【开启权限】<a hidden="" class="anchor" aria-hidden="true" href="#1配置开启权限">#</a></h3>
<ul>
<li>第一步需要做的就是开启可以运行自己应用的权限。Additional services -&gt; Run your own applications -&gt; Enabled 如果不开启这一项，自己的用户目录下的所有文件都无法添加可执行权限。</li>
</ul>
<h3 id="2安装pm2">2，安装PM2<a hidden="" class="anchor" aria-hidden="true" href="#2安装pm2">#</a></h3>
<p><a href="https://pm2.io/" target="_blank" rel="noopener">PM2</a> 是一款非常优秀的node.js进程管理工具。可以通过SSH用下面的指令一键安装。</p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4;"><code class="language-shell hljs" data-lang="shell"><span style="display:flex;"><span>bash &lt;<span style="color:#f92672">(</span>curl -s https://raw.githubusercontent.com/k0baya/alist_repl/main/serv00/install-pm2.sh<span style="color:#f92672">)</span>
</span></span></code></pre><button class="copy-code">复制</button><div class="mac-tool"><div class="mac bb1"></div><div class="mac bb2"></div><div class="mac bb3"></div><div class="language-type">shell</div></div></div><p>使用pm2，请直接用路径调用：<code>~/.npm-global/bin/pm2</code>，例如<code>~/.npm-global/bin/pm2 list</code> 就可以看到自己添加的应用。</p>
<details>
<summary><code><strong>「 另外，在`SSH`中通过下面的指令就可以开启页面监控功能！不需要可以不开 」</strong></code></summary>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4;"><code class="language-shell hljs" data-lang="shell"><span style="display:flex;"><span>~/.npm-global/bin/pm2 monitor
</span></span></code></pre><button class="copy-code">复制</button><div class="mac-tool"><div class="mac bb1"></div><div class="mac bb2"></div><div class="mac bb3"></div><div class="language-type">shell</div></div></div><p>如果没有账号可以按照提示创建就可以，然后会给出登录页面的地址。
<a href="https://app.pm2.io/#/bucket/65f3be6efe520b3f5503d9aa" target="_blank" rel="noopener">https://app.pm2.io/#/bucket/65f3be6efe520b3f5503d9aa</a>
用浏览器登录就可以看到了，非常的方便。</p>
</details>
<h3 id="3安装vless">3，安装Vless<a hidden="" class="anchor" aria-hidden="true" href="#3安装vless">#</a></h3>
<p>Vless是一个代理节点应用，可以通过SSH用下面的指令一键安装。</p>
<p>进入项目操作目录,以下命令行中<code>&lt;Your-domain&gt;</code>换成你的域名</p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4;"><code class="language-shell hljs" data-lang="shell"><span style="display:flex;"><span>cd ~/domains/&lt;Your-domain&gt;
</span></span></code></pre><button class="copy-code">复制</button><div class="mac-tool"><div class="mac bb1"></div><div class="mac bb2"></div><div class="mac bb3"></div><div class="language-type">shell</div></div></div><p>克隆serv00-vless项目到</p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4;"><code class="language-shell hljs" data-lang="shell"><span style="display:flex;"><span>git clone https://github.com/qwer-search/serv00-vless <span style="color:#f92672">&amp;&amp;</span> mv -f serv00-vless vless <span style="color:#f92672">&amp;&amp;</span> cd vless <span style="color:#f92672">&amp;&amp;</span> rm -f README.md
</span></span></code></pre><button class="copy-code">复制</button><div class="mac-tool"><div class="mac bb1"></div><div class="mac bb2"></div><div class="mac bb3"></div><div class="language-type">shell</div></div></div><p>在serv00的管理页面上开启一个端口，<code>Port reservation -&gt; Add port</code>添加一个<code>TCP</code>的端口号。再在<code>File Manager</code> 里面找到Vless的文件下的<code>app.js</code>文件，修改里面的端口号为刚刚添加的端口号。类似下面修改为了<code>12345</code></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4;"><code class="language-shell hljs" data-lang="shell"><span style="display:flex;"><span>const port <span style="color:#f92672">=</span> process.env.PORT <span style="color:#f92672">||</span> 12345;
</span></span></code></pre><button class="copy-code">复制</button><div class="mac-tool"><div class="mac bb1"></div><div class="mac bb2"></div><div class="mac bb3"></div><div class="language-type">shell</div></div></div><p>安装依赖</p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4;"><code class="language-shell hljs" data-lang="shell"><span style="display:flex;"><span>npm install
</span></span></code></pre><button class="copy-code">复制</button><div class="mac-tool"><div class="mac bb1"></div><div class="mac bb2"></div><div class="mac bb3"></div><div class="language-type">shell</div></div></div><p>安装完毕后，使用<code>PM2</code>启动并守护vless进程：</p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4;"><code class="language-shell hljs" data-lang="shell"><span style="display:flex;"><span>~/.npm-global/bin/pm2 start app.js --name vless
</span></span></code></pre><button class="copy-code">复制</button><div class="mac-tool"><div class="mac bb1"></div><div class="mac bb2"></div><div class="mac bb3"></div><div class="language-type">shell</div></div></div><p>接着去你的代理客户端软件中手动添加vless配置即可：</p>
<table>
<thead>
<tr>
<th>Key</th>
<th>Value</th>
</tr>
</thead>
<tbody>
<tr>
<td>地址</td>
<td>Panel 中 WWW Websites 选项卡里的你的 Domain name</td>
</tr>
<tr>
<td>端口</td>
<td>你放行的端口</td>
</tr>
<tr>
<td>用户 ID</td>
<td>37a0bd7c-8b9f-4693-8916-bd1e2da0a817</td>
</tr>
<tr>
<td>传输协议</td>
<td>ws</td>
</tr>
<tr>
<td>伪装域名</td>
<td>同地址</td>
</tr>
<tr>
<td>ws path</td>
<td>/</td>
</tr>
</tbody>
</table>
<p>也可以复制以下vless节点信息，修改<code>&lt;域名地址&gt;</code>为Panel 中 <code>WWW Websites</code> 选项卡里的你的 <code>Domain name</code>，<code>&lt;端口&gt;</code>为你放行的端口即可</p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4;"><code class="language-shell hljs" data-lang="shell"><span style="display:flex;"><span>vless://37a0bd7c-8b9f-4693-8916-bd1e2da0a817@&lt;域名地址&gt;:&lt;端口&gt;?flow<span style="color:#f92672">=</span>&amp;security<span style="color:#f92672">=</span>none&amp;encryption<span style="color:#f92672">=</span>none&amp;type<span style="color:#f92672">=</span>ws&amp;host<span style="color:#f92672">=</span>&lt;域名地址&gt;&amp;path<span style="color:#f92672">=</span>/&amp;sni<span style="color:#f92672">=</span>&amp;fp<span style="color:#f92672">=</span>&amp;pbk<span style="color:#f92672">=</span>&amp;sid<span style="color:#f92672">=</span><span style="color:#75715e">#%E4%B8%80%E4%BC%91vless%EF%BC%8CTG%E7%BE%A4%EF%BC%9Ahttps://t.me/yxjsjl</span>
</span></span></code></pre><button class="copy-code">复制</button><div class="mac-tool"><div class="mac bb1"></div><div class="mac bb2"></div><div class="mac bb3"></div><div class="language-type">shell</div></div></div><p>上表没有给出的可以不填。</p>
<p>我用的客户端是v2rayU，按照这个配置就行。目前测试下来连接不是很稳定，延迟忽高忽低，有300ms左右。</p>
<p><a href="https://scamalytics.com/" target="_blank" rel="noopener">纯净度检测</a></p>
<h3 id="4自动化">4，自动化<a hidden="" class="anchor" aria-hidden="true" href="#4自动化">#</a></h3>
<p>听说serv00会不定时重启机器，所以我们把PM2添加开机自启。而且serv00每三个月内必须要有一次登录面板或者SSH连接，不然会删号，也可以通过一个脚本解决问题，接下来我会详细说明。</p>
<h4 id="自动续期">自动续期<a hidden="" class="anchor" aria-hidden="true" href="#自动续期">#</a></h4>
<p>新建<code>opt</code>目录,并进入目录</p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4;"><code class="language-shell hljs" data-lang="shell"><span style="display:flex;"><span>mkdir ~/opt
</span></span></code></pre><button class="copy-code">复制</button><div class="mac-tool"><div class="mac bb1"></div><div class="mac bb2"></div><div class="mac bb3"></div><div class="language-type">shell</div></div></div><p>新建 auto-renew.sh 脚本：</p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4;"><code class="language-shell hljs" data-lang="shell"><span style="display:flex;"><span>cat &gt; auto-renew.sh <span style="color:#e6db74">&lt;&lt; EOF
</span></span></span><span style="display:flex;"><span><span style="color:#e6db74"><span class="hljs-meta">#</span><span class="bash">!/bin/bash</span>
</span></span></span><span style="display:flex;"><span><span style="color:#e6db74">
</span></span></span><span style="display:flex;"><span><span style="color:#e6db74">while true; do
</span></span></span><span style="display:flex;"><span><span style="color:#e6db74">  sshpass -p '密码' ssh -o StrictHostKeyChecking=no -o UserKnownHostsFile=/dev/null -tt 用户名@地址 "exit" &amp;
</span></span></span><span style="display:flex;"><span><span style="color:#e6db74">  sleep 259200  #30天为259200秒
</span></span></span><span style="display:flex;"><span><span style="color:#e6db74">done
</span></span></span><span style="display:flex;"><span><span style="color:#e6db74">EOF</span>
</span></span></code></pre><button class="copy-code">复制</button><div class="mac-tool"><div class="mac bb1"></div><div class="mac bb2"></div><div class="mac bb3"></div><div class="language-type">shell</div></div></div><p>另外记得把其中的密码、用户名、ssh的地址修改为你自己的。</p>
<p>给 <code>auto-renew.sh</code>添加可执行权限：</p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4;"><code class="language-shell hljs" data-lang="shell"><span style="display:flex;"><span>chmod +x auto-renew.sh
</span></span></code></pre><button class="copy-code">复制</button><div class="mac-tool"><div class="mac bb1"></div><div class="mac bb2"></div><div class="mac bb3"></div><div class="language-type">shell</div></div></div><p>使用PM2启动：</p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4;"><code class="language-shell hljs" data-lang="shell"><span style="display:flex;"><span>~/.npm-global/bin/pm2 start ./auto-renew.sh
</span></span></code></pre><button class="copy-code">复制</button><div class="mac-tool"><div class="mac bb1"></div><div class="mac bb2"></div><div class="mac bb3"></div><div class="language-type">shell</div></div></div><p>这样就会每隔一个月自动执行一次<code>SSH</code>连接，自己SSH自己进行续期。</p>
<h4 id="自动启动">自动启动<a hidden="" class="anchor" aria-hidden="true" href="#自动启动">#</a></h4>
<p>在<code>serv00</code>的管理页面上找到<code>Cron jobs</code>选项卡，使用<code>Add cron job</code>功能添加任务，<code>Specify time</code>选择<code>After reboot</code>，即为重启后运行。<code>Form type</code>选择<code>Advanced，Command</code>写：</p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4;"><code class="language-shell hljs" data-lang="shell"><span style="display:flex;"><span>/home/你的用户名/.npm-global/bin/pm2 resurrect
</span></span></code></pre><button class="copy-code">复制</button><div class="mac-tool"><div class="mac bb1"></div><div class="mac bb2"></div><div class="mac bb3"></div><div class="language-type">shell</div></div></div><p>添加完之后，在<code>SSH</code>窗口保存<code>PM2</code>的当前任务列表快照：</p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4;"><code class="language-shell hljs" data-lang="shell"><span style="display:flex;"><span>~/.npm-global/bin/pm2 save
</span></span></code></pre><button class="copy-code">复制</button><div class="mac-tool"><div class="mac bb1"></div><div class="mac bb2"></div><div class="mac bb3"></div><div class="language-type">shell</div></div></div><p>这样每次<code>serv00</code>不定时重启任务时，都能自动调用<code>PM2</code>读取保存的任务列表快照，恢复任务列表。如果在保存了任务列表快照后又改变了任务<code>PM2</code>的任务列表，需要重新执行<code>pm2 save</code>以更新任务列表。</p>

