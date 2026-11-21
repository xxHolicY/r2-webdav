# r2-webdav

为 R2 存储桶提供 WebDAV 接口的 Worker。

## Language

**存储桶**:
Worker 所服务的那个 R2 桶，名为 `webdav`，和 r2-explorer 共用。
_Avoid_: bucket（行文中）, 仓库, 盘

**健康检查接口**:
只读的 `/health` 路径。需要鉴权，报告服务是否可用，并给出存储桶名称和服务版本。
_Avoid_: ping, status 接口, 探活接口

**服务版本**:
r2-webdav 自身的版本号，取自 `package.json`。
_Avoid_: 部署版本, commit 号

**保留路径**:
被健康检查接口占用的精确路径 `/health`。桶内同名对象无法通过 WebDAV 访问。
_Avoid_: 特殊路径
