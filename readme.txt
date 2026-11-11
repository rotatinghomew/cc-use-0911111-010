临床试验站点联合采集服务

该项目用于联合多个试验站点的本地数据批次，统一处理站点版本、重复记录和字段差异，并保留可恢复的同步进度。演示入口读取 fixtures/demo.json，将联合处理结果与状态写入本地 SQLite 数据库。

测试：python3 -m unittest discover -s tests/federated_trials -p 'test_*.py'
构建：python3 -m compileall -q trial_site_federator
验收：python3 -m trial_site_federator.console.federate fixtures/demo.json --db /tmp/trial_site_federator-acceptance.sqlite3
