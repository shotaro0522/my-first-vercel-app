<h1>Hello Vercel! 🚀</h1>
<p>私の最初のVercelデプロイです</p>
<p>SvelteKit + Vercel = 最高の組み合わせ！</p>

<div class="info">
	<h2>✅ デプロイ成功！</h2>
	<p>このページがVercelで表示されていれば、デプロイが成功しています。</p>
</div>

<div class="tech-stack">
	<h2>🛠️ 技術スタック</h2>
	<ul>
		<li><strong>SvelteKit</strong> - モダンなフルスタックフレームワーク</li>
		<li><strong>Vercel</strong> - 高速デプロイ＆ホスティングプラットフォーム</li>
		<li><strong>GitHub</strong> - ソースコード管理</li>
		<li><strong>Node.js</strong> - JavaScript ランタイム</li>
	</ul>
</div>

<div class="features">
	<h2>🎯 このプロジェクトの特徴</h2>
	<div class="feature-grid">
		<div class="feature-card">
			<h3>⚡ 高速</h3>
			<p>VercelのCDNで世界中に高速配信</p>
		</div>
		<div class="feature-card">
			<h3>🔄 自動デプロイ</h3>
			<p>GitHubプッシュで自動的に更新</p>
		</div>
		<div class="feature-card">
			<h3>🆓 無料</h3>
			<p>個人プロジェクトなら無料で利用可能</p>
		</div>
		<div class="feature-card">
			<h3>🔒 HTTPS</h3>
			<p>SSL証明書が自動で設定される</p>
		</div>
	</div>
</div>

<div class="stats">
	<h2>📊 プロジェクト情報</h2>
	<div class="stats-grid">
		<div class="stat">
			<span class="stat-number">2025</span>
			<span class="stat-label">作成年</span>
		</div>
		<div class="stat">
			<span class="stat-number">5min</span>
			<span class="stat-label">デプロイ時間</span>
		</div>
		<div class="stat">
			<span class="stat-number">100%</span>
			<span class="stat-label">成功率</span>
		</div>
	</div>
</div>

<style>
	:global(body) {
		font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
		line-height: 1.6;
		margin: 0;
		padding: 2rem;
		background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
		min-height: 100vh;
	}
	
	:global(*) {
		box-sizing: border-box;
	}
	
	h1 {
		color: white;
		font-size: 3rem;
		margin-bottom: 1rem;
		text-align: center;
		text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
	}
	
	p {
		font-size: 1.2rem;
		margin-bottom: 0.5rem;
		color: white;
		text-align: center;
	}
	
	.info, .tech-stack, .features, .stats {
		background: white;
		padding: 2rem;
		border-radius: 12px;
		margin: 2rem 0;
		box-shadow: 0 8px 32px rgba(0,0,0,0.1);
	}
	
	.info h2, .tech-stack h2, .features h2, .stats h2 {
		color: #333;
		margin-top: 0;
		margin-bottom: 1rem;
	}
	
	.tech-stack ul {
		list-style: none;
		padding: 0;
	}
	
	.tech-stack li {
		padding: 0.8rem;
		margin: 0.5rem 0;
		background: #f8f9fa;
		border-radius: 8px;
		border-left: 4px solid #ff3e00;
	}
	
	.feature-grid {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
		gap: 1.5rem;
		margin-top: 1rem;
	}
	
	.feature-card {
		background: #f8f9fa;
		padding: 1.5rem;
		border-radius: 8px;
		text-align: center;
		border: 1px solid #e9ecef;
		transition: transform 0.2s;
	}
	
	.feature-card:hover {
		transform: translateY(-2px);
		box-shadow: 0 4px 12px rgba(0,0,0,0.1);
	}
	
	.feature-card h3 {
		margin: 0 0 0.5rem 0;
		color: #0070f3;
	}
	
	.stats-grid {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
		gap: 1rem;
	}
	
	.stat {
		text-align: center;
		background: linear-gradient(135deg, #667eea, #764ba2);
		padding: 1.5rem;
		border-radius: 12px;
		color: white;
	}
	
	.stat-number {
		display: block;
		font-size: 2rem;
		font-weight: bold;
		margin-bottom: 0.5rem;
	}
	
	.stat-label {
		font-size: 0.9rem;
		opacity: 0.9;
	}
	
	@media (max-width: 768px) {
		h1 {
			font-size: 2rem;
		}
		
		.feature-grid {
			grid-template-columns: 1fr;
		}
	}
</style>