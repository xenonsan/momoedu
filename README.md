# Bloxd Direct SW Proxy v0.5.1

VPS上の1006調査用安定化版です。

- `closedBy=client|upstream`で切断元を記録
- client/upstream双方の終了コードを記録
- 最終送受信から切断までの時間を記録
- TCP keepalive 15秒とTCP_NODELAYを双方へ設定
- phpinfo、WordPress、`.env`、`.git`等のスキャンパスをローカル404
- メッセージ単位ログは復活させず軽量性を維持
- Code 3対策のCookie/User-Agent/Origin/Referer転送を維持

更新後:

```bash
cd /opt/apps/dloxd
npm install
npm run check
docker compose up -d --force-recreate
```

確認対象ログ:

```text
websocket-session-ended
closedBy=client
closedBy=upstream
lastClientAgoMs
lastUpstreamAgoMs
```
