<div class="markdown-body" id="postBody"><p>这几天在论坛里面看到一个免费10年的虚拟主机<a href="https://www.serv00.com/" rel="nofollow">serv00</a>。简单注册了一下就可以使用了，账号和密码会直接发到注册的邮箱里，我这里使用了Gmail的邮箱。下面就是记录一下自己搭建的东西。</p>
<h2>配置</h2>
<ol>
<li>【开启权限】第一步需要做的就是开启可以运行自己应用的权限。<code class="notranslate">Additional services -&gt; Run your own applications -&gt; Enabled</code> 如果不开启这一项，自己的用户目录下的所有文件都无法添加可执行权限。</li>
<li>【进入SSH】通过注册邮箱里收到的信息，用<code class="notranslate">MobaXterm</code>登录，就可以看到下面的信息。</li>
</ol>
<pre class="notranslate"><code class="notranslate">  ____                   ___   ___
 / ___|  ___ _ ____   __/ _ \ / _ \  ___ ___  _ __ ___
 \___ \ / _ \ '__\ \ / / | | | | | |/ __/ _ \| '_ ` _ \
  ___) |  __/ |   \ V /| |_| | |_| | (_| (_) | | | | | |
 |____/ \___|_|    \_/  \___/ \___(_)___\___/|_| |_| |_|
  Revolutionary Free Hosting

 =[ Basic account info ]=
         Username: Meekdai
             Plan: FREE
  Expiration date: 2034-03-13 02:18:41
</code></pre>
<h2>安装PM2</h2>
<p><a href="https://pm2.io/" rel="nofollow">PM2</a> 是一款非常优秀的<code class="notranslate">node.js</code>进程管理工具。可以通过SSH用下面的指令一键安装。</p>
<pre class="notranslate"><code class="notranslate">bash &lt;(curl -s https://raw.githubusercontent.com/k0baya/alist_repl/main/serv00/install-pm2.sh)
</code></pre>
<p>使用<code class="notranslate">pm2</code>，请直接用路径调用：<code class="notranslate">~/.npm-global/bin/pm2</code>，例如<code class="notranslate">~/.npm-global/bin/pm2 list</code> 就可以看到自己添加的应用。</p>
<p>另外，在<code class="notranslate">SSH</code>中通过下面的指令就可以开启页面监控功能。</p>
<pre class="notranslate"><code class="notranslate">~/.npm-global/bin/pm2 monitor
</code></pre>
<p>如果没有账号可以按照提示创建就可以，然后会给出登录页面的地址。<br>
<a href="https://app.pm2.io/#/bucket/65f3be6efe520b3f5503d9aa" rel="nofollow">https://app.pm2.io/#/bucket/65f3be6efe520b3f5503d9aa</a><br>
用浏览器登录就可以看到了，非常的方便。</p>
<h2>安装Vless</h2>
<p>Vless是一个代理节点应用，可以通过SSH用下面的指令一键安装。</p>
<pre class="notranslate"><code class="notranslate">cd ~/domains &amp;&amp; git clone https://github.com/qwer-search/serv00-vless &amp;&amp; mv -f serv00-vless vless &amp;&amp; cd vless &amp;&amp; rm -f README.md
</code></pre>
<p>在serv00的管理页面上开启一个端口，<code class="notranslate">Port reservation -&gt; Add port</code>添加一个<code class="notranslate">TCP</code>的端口号。再在<code class="notranslate">File Manager</code> 里面找到<code class="notranslate">Vless</code>的文件下的<code class="notranslate">app.js</code>文件，修改里面的端口号为刚刚添加的端口号。类似下面修改为了<code class="notranslate">12345</code></p>
<pre class="notranslate"><code class="notranslate">const port = process.env.PORT || 12345;
</code></pre>
<p>安装依赖</p>
<pre class="notranslate"><code class="notranslate">npm install
</code></pre>
<p>安装完毕后，使用<code class="notranslate">PM2</code>启动并守护vless进程：</p>
<pre class="notranslate"><code class="notranslate">~/.npm-global/bin/pm2 start app.js --name vless
</code></pre>
<p>接着去你的代理客户端软件中手动添加vless配置即可：</p>
<table role="table">
<thead>
<tr>
<th><strong>Key</strong></th>
<th><strong>Value</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>地址</strong></td>
<td>Panel 中 WWW Websites 选项卡里的你的 Domain name</td>
</tr>
<tr>
<td><strong>端口</strong></td>
<td>你放行的端口</td>
</tr>
<tr>
<td><strong>用户 ID</strong></td>
<td>37a0bd7c-8b9f-4693-8916-bd1e2da0a817</td>
</tr>
<tr>
<td><strong>传输协议</strong></td>
<td>ws</td>
</tr>
<tr>
<td><strong>伪装域名</strong></td>
<td>同地址</td>
</tr>
<tr>
<td><strong>ws path</strong></td>
<td>/</td>
</tr>
</tbody>
</table>
<p>上表没有给出的可以不填。</p>
<p>我用的客户端是<a href="https://v2raya.org/docs/prologue/quick-start/" rel="nofollow">v2rayA</a>，按照这个配置就行。目前测试下来连接不是很稳定，延迟比较高，有<code class="notranslate">1000ms</code>以上。</p>
<h2>自动化</h2>
<p>听说<code class="notranslate">serv00</code>会不定时重启机器，所以我们把<code class="notranslate">PM2</code>添加开机自启。而且<code class="notranslate">serv00</code>每三个月内必须要有一次登录面板或者<code class="notranslate">SSH</code>连接，不然会删号，也可以通过一个脚本解决问题，接下来我会详细说明。</p>
<h3>自动续期</h3>
<p>新建 auto-renew.sh 脚本：</p>
<pre class="notranslate"><code class="notranslate">cat &gt; auto-renew.sh &lt;&lt; EOF
#!/bin/bash

while true; do
  sshpass -p '密码' ssh -o StrictHostKeyChecking=no -o UserKnownHostsFile=/dev/null -tt 用户名@地址 "exit" &amp;
  sleep 259200  #30天为259200秒
done
EOF
</code></pre>
<p>我是新建了一个<code class="notranslate">opt</code>目录，在<code class="notranslate">opt</code>目录下创建这个脚本。另外记得把其中的密码、用户名、ssh的地址修改为你自己的。</p>
<p>给 <code class="notranslate">auto-renew.sh</code>添加可执行权限：</p>
<pre class="notranslate"><code class="notranslate">chmod +x auto-renew.sh
</code></pre>
<p>使用PM2启动：</p>
<pre class="notranslate"><code class="notranslate">~/.npm-global/bin/pm2 start ./auto-renew.sh
</code></pre>
<p>这样就会每隔一个月自动执行一次<code class="notranslate">SSH</code>连接，自己<code class="notranslate">SSH</code>自己进行续期。</p>
<h3>自动启动</h3>
<p>在serv00的管理页面上找到<code class="notranslate">Cron jobs</code>选项卡，使用<code class="notranslate">Add cron job</code>功能添加任务，<code class="notranslate">Specify time</code>选择<code class="notranslate">After reboot</code>，即为重启后运行。<code class="notranslate">Form type</code>选择<code class="notranslate">Advanced</code>，<code class="notranslate">Command</code>写：</p>
<pre class="notranslate"><code class="notranslate">/home/你的用户名/.npm-global/bin/pm2 resurrect
</code></pre>
<p>添加完之后，在<code class="notranslate">SSH</code>窗口保存<code class="notranslate">PM2</code>的当前任务列表快照：</p>
<pre class="notranslate"><code class="notranslate">~/.npm-global/bin/pm2 save
</code></pre>
<p>这样每次<code class="notranslate">serv00</code>不定时重启任务时，都能自动调用<code class="notranslate">PM2</code>读取保存的任务列表快照，恢复任务列表。如果在保存了任务列表快照后又改变了任务<code class="notranslate">PM2</code>的任务列表，需要重新执行<code class="notranslate">pm2 save</code>以更新任务列表。</p>
<p>参考链接：<a href="https://docs.serv00.com/" rel="nofollow">https://docs.serv00.com/</a><br>
参考链接：<a href="https://blog.rappit.site/2024/01/27/serv00_logs/" rel="nofollow">https://blog.rappit.site/2024/01/27/serv00_logs/</a></p></div>