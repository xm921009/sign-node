# sign-node

网易云签到独立产品的跑批薄壳节点。本仓**不含任何代码、CK 或买家数据**：

- 每日北京 00:40 自动跑（或手动 dispatch）：运行时从 public 的
  [xm921016/cron-relay](https://github.com/xm921016/cron-relay) 拉取 `signin.py`，
  以 `SIGN_USERS=1` 买家池模式从 worker API 分片领号 → 签到 → 回传。
- 结果落库在 worker 侧 D1（sign_users / sign_logs），本仓 Actions 日志只有统计行。

改签到口径/邮件模板/判定逻辑：只改主仓 xm921016/cron-relay，本仓不动。
