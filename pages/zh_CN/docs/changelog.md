---
title: 更新日志
layout: page
---

## v2.0 - 2020.08

GORM 2.0 is a rewrite from scratch, it introduces some incompatible-API change and many improvements

* 性能改进
* 模块化
* Context, Batch Insert, Prepared Statment Mode, DryRun Mode, Join Preload, Find To Map, Create From Map, FindInBatches supports
* Nested Transaction/SavePoint/RollbackTo SavePoint supports
* Named Argument, Group Conditions, Upsert, Locking, Optimizer/Index/Comment Hints supports, SubQuery improvements
* Full self-reference relationships supports, Join Table improvements, Association Mode for batch data
* Multiple fields support for tracking create/update time, which adds support for UNIX (milli/nano) seconds
* 字段级权限控制：只读、只写、只创建、只更新、忽略
* New plugin system: read/write splitting with plugin Database Resolver, prometheus integrations...
* New Hooks API: unified interface with plugins
* New Migrator: allows to create database foreign keys for relationships, constraints/checker support, enhanced index support
* New Logger: context support, improved extensibility
* Unified Naming strategy: table name, field name, join table name, foreign key, checker, index name rules
* Better customized data type support (e.g: JSON)

[GORM 2.0 Release Note](v2_release_note.html)

## v1.0 - 2016.04

[GORM V1 Docs](https://v1.gorm.io)

Breaking Changes:

* `gorm.Open` returns `*gorm.DB` instead of `gorm.DB`
* Updating will only update changed fields
* Soft Delete's will only check `deleted_at IS NULL`
* New ToDBName logic Common initialisms from [golint](https://github.com/golang/lint/blob/master/lint.go#L702) like `HTTP`, `URI` was converted to lowercase, so `HTTP`'s db name is `http`, but not `h_t_t_p`, but for some other initialisms not in the list, like `SKU`, it's db name was `s_k_u`, this change fixed it to `sku`
* `RecordNotFound ` 错误已被重命名为 `ErrRecordNotFound `
* `mssql` dialect has been renamed to `github.com/jinzhu/gorm/dialects/mssql`
* `Hstore` has been moved to package `github.com/jinzhu/gorm/dialects/postgres`
