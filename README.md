# Java 后端学习 · 进度存档
> 最后更新：2026-08-13 | 当前进度：并发【重讲中·从第1课重新开始】第3课（volatile + 线程池·详细版）已讲、练习通过，下一步第4课（JVM 内存 + GC）

## 一、环境（已全部装好）
| 工具 | 路径 | 说明 |
|------|------|------|
| JDK 25.0.2 LTS | C:\Program Files\Java\jdk-25.0.2 | JAVA_HOME 已设置 |
| Maven 3.9.16 | D:\dev-tools\apache-maven-3.9.16 | 已配阿里云镜像(~/.m2/settings.xml) |
| Git 2.55.0 | D:\dev-tools\Git | |
| MySQL 8.4.11 | D:\dev-tools\mysql-8.4.11-winx64 | root/root，端口3306，库 testdb |
| Redis 8.10.0 | D:\dev-tools\redis\Redis-8.10.0-Windows-x64-msys2 | 端口6379 |
| VS Code | D:\1\Microsoft VS Code | 装了 Java 扩展 |
| IntelliJ IDEA 2024.2 | D:\1\IntelliJ IDEA Community Edition 2024.2.0.1 | 也用（曾因打开错误项目出过问题） |
| DBeaver | 已装 | 数据库图形客户端 |

**启动脚本（重启电脑后手动执行）**：
- MySQL: D:\dev-tools\start-mysql.bat
- Redis: D:\dev-tools\start-redis.bat
- Spring Boot: 在 D:\codex\spring-demo 下 `mvn spring-boot:run`（端口8080）

## 二、学习进度（20天计划，已过约6天）
- ✅ MySQL 基础：建表/增删改查/WHERE/ORDER BY/LIMIT/聚合/GROUP BY/JOIN/索引/事务/ACID/隔离级别(默认REPEATABLE-READ)
- ✅ Spring Boot + MyBatis：项目 D:\codex\spring-demo（Spring Boot 4.1.0 + Java 25 + MyBatis 4.0.1）
  - 接口 GET/POST/PUT/DELETE /api/students，连 MySQL testdb.student 表（5条数据）
  - 注意：Spring Boot 4.1 用 Jackson 3（tools.jackson 包名，不是 com.fasterxml）
- ✅ Redis：5大数据类型/TTL/持久化(RDB/AOF)/缓存三大问题(穿透/击穿/雪崩)
  - 已集成到 spring-demo：旁路缓存（先查Redis→查MySQL→回填60秒，写操作清缓存）
- 🔄 并发+JVM（【重讲中】用户要求从第1课重新从头讲，讲得更细）：
  - 第1课 进程/线程/创建线程、并发vs并行、start vs run、为何推荐Runnable、线程6种状态 ✅（详细版重讲完成，练习 Exp4 通过）
  - 第2课 线程安全：竞态条件(count++丢更新)、synchronized、锁粒度、可重入、白锁坑 ✅（详细版重讲完成，练习 Exp5 卖票通过）
  - 第3课 volatile（可见性）+ 线程池（7参数/执行流程/拒绝策略/Future）✅（详细版重讲完成，练习 Exp6 餐厅出餐通过）
  - 第4课 JVM 内存区域 + GC 🔄 详细版进行中
- ⬜ 秒杀项目（未开始，综合 MySQL+Redis+并发）
- ⬜ 八股+模拟面试（未开始）
- 注：第1~3课此前已讲过一遍，演示代码都在；本次因用户要求从头重讲，重新过一遍加深理解。

## 三、演示代码位置
- D:\codex\javademo\：ThreadDemo1~12(并发各课演示) / ThreadDemo10_LockScope(锁粒度对比) / Exp1~Exp6(各课练习) / JVMDemo1_StackOverflow(栈溢出) / JVMDemo2_OOM(堆溢出,用 java -Xmx64m 跑)
- 运行方式：命令行 `java 文件名.java`（用 JDK25），或 VS Code/IntelliJ（注意类名=文件名）
- 编码坑：Windows 控制台显示中文会乱码（Java默认UTF-8，控制台GBK），演示代码用英文输出，或先 `chcp 65001`

## 四、下一步（新对话从这里继续）
第4课：JVM内存+GC（详细版，进行中）→ 秒杀项目 → 八股+模拟面试

## 五、交接说明（直接粘给新对话）
"用户零基础学 Java 后端，按 20 天计划学习，进度约 6/20 天。环境全部装好（见 D:\codex\学习进度存档.md）。用户要求并发从头重讲，第1、2、3课已重讲并通过练习（Exp4/Exp5/Exp6），正在讲第4课 JVM内存+GC。教学风格：手把手、代码带中文注释、循序渐进、多实操、少废话（用户要求详细版）。演示代码在 D:\codex\javademo\。Spring Boot 项目在 D:\codex\spring-demo\。注意 Windows 控制台中文乱码，代码输出用英文。"
