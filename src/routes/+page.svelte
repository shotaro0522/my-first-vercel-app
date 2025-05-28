<script>
	import { onMount } from 'svelte';
	
	let isAuthenticated = false;
	let password = '';
	let error = '';
	
	const correctPassword = '0318';
	
	onMount(() => {
		// ローカルストレージから認証状態を確認
		const savedAuth = localStorage.getItem('authenticated');
		if (savedAuth === 'true') {
			isAuthenticated = true;
		}
	});
	
	function handleLogin() {
		if (password === correctPassword) {
			isAuthenticated = true;
			localStorage.setItem('authenticated', 'true');
			error = '';
		} else {
			error = 'パスワードが間違っています';
			password = '';
		}
	}
	
	function handleLogout() {
		isAuthenticated = false;
		localStorage.removeItem('authenticated');
		password = '';
	}
	
	function handleKeydown(event) {
		if (event.key === 'Enter') {
			handleLogin();
		}
	}
</script>

{#if !isAuthenticated}
	<!-- ログイン画面 -->
	<div class="login-container">
		<div class="login-box">
			<div class="lock-icon">🔒</div>
			<h1>認証が必要です</h1>
			<p>パスワードを入力してください</p>
			
			<div class="input-group">
				<input 
					type="password" 
					bind:value={password}
					on:keydown={handleKeydown}
					placeholder="パスワードを入力"
					class="password-input"
					autofocus
				/>
				<button on:click={handleLogin} class="login-btn">
					ログイン
				</button>
			</div>
			
			{#if error}
				<div class="error">{error}</div>
			{/if}
			
			<div class="hint">
				<small>ヒント: 8桁の数字です 🔢</small>
			</div>
		</div>
	</div>
{:else}
	<!-- メインページ -->
	<div class="main-container">
		<div class="logout-header">
			<button on:click={handleLogout} class="logout-btn">
				🔓 ログアウト
			</button>
		</div>

		<h1>Hello Vercel! 🚀</h1>
		<p>私の最初のVercelデプロイです</p>
		<p>SvelteKit + Vercel = 最高の組み合わせ！</p>

		<div class="info">
			<h2>✅ デプロイ成功！</h2>
			<p>このページがVercelで表示されていれば、デプロイが成功しています。</p>
			<p><strong>🔒 パスワード保護機能付き！</strong></p>
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
					<h3>🔒 パスワード保護</h3>
					<p>簡単な認証機能でプライベートアクセス</p>
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
	</div>
{/if}

<style>
	/* ログイン画面のスタイル */
	.login-container {
		min-height: 100vh;
		background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
		display: flex;
		align-items: center;
		justify-content: center;
		padding: 2rem;
		margin: 0;
		font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
	}

	.login-box {
		background: white;
		padding: 3rem;
		border-radius: 20px;
		box-shadow: 0 20px 60px rgba(0,0,0,0.2);
		text-align: center;
		max-width: 400px;
		width: 100%;
	}

	.lock-icon {
		font-size: 4rem;
		margin-bottom: 1rem;
	}

	.login-box h1 {
		color: #333;
		margin-bottom: 0.5rem;
		font-size: 2rem;
	}

	.login-box p {
		color: #666;
		margin-bottom: 2rem;
	}

	.input-group {
		display: flex;
		gap: 1rem;
		margin-bottom: 1rem;
	}

	.password-input {
		flex: 1;
		padding: 1rem;
		border: 2px solid #e0e0e0;
		border-radius: 10px;
		font-size: 1.1rem;
		text-align: center;
		letter-spacing: 0.2em;
	}

	.password-input:focus {
		outline: none;
		border-color: #667eea;
		box-shadow: 0 0 0 3px rgba(102, 126, 234, 0.1);
	}

	.login-btn {
		padding: 1rem 2rem;
		background: linear-gradient(135deg, #667eea, #764ba2);
		color: white;
		border: none;
		border-radius: 10px;
		font-size: 1rem;
		font-weight: 600;
		cursor: pointer;
		transition: transform 0.2s;
	}

	.login-btn:hover {
		transform: translateY(-2px);
	}

	.error {
		background: #ffe6e6;
		color: #d32f2f;
		padding: 0.75rem;
		border-radius: 8px;
		margin-bottom: 1rem;
		border: 1px solid #ffcdd2;
	}

	.hint {
		color: #888;
		margin-top: 1rem;
	}

	/* メインページのスタイル */
	.main-container {
		font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
		line-height: 1.6;
		margin: 0;
		padding: 2rem;
		background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
		min-height: 100vh;
		box-sizing: border-box;
	}

	.logout-header {
		text-align: right;
		margin-bottom: 2rem;
	}

	.logout-btn {
		background: rgba(255, 255, 255, 0.2);
		color: white;
		border: 1px solid rgba(255, 255, 255, 0.3);
		padding: 0.75rem 1.5rem;
		border-radius: 25px;
		cursor: pointer;
		font-size: 0.9rem;
		transition: all 0.2s;
		backdrop-filter: blur(10px);
	}

	.logout-btn:hover {
		background: rgba(255, 255, 255, 0.3);
		transform: translateY(-2px);
	}

	.main-container h1 {
		color: white;
		font-size: 3rem;
		margin-bottom: 1rem;
		text-align: center;
		text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
	}

	.main-container p {
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
		.main-container h1 {
			font-size: 2rem;
		}

		.feature-grid {
			grid-template-columns: 1fr;
		}

		.input-group {
			flex-direction: column;
		}
	}
</style>