# Docker vs K8s mentioned on hackernews

```k8s_vs_docker
SELECT
    sum(lower(concat_ws(' ', title, url, text)) regexp '\\bk8s\\b|\\bkubernetes\\b') AS k8s_cnt,
    sum(lower(concat_ws(' ', title, url, text)) regexp '\\bdocker\\b') AS docker_cnt,
    DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') AS date
FROM items
WHERE dead = 0 and deleted = 0
GROUP BY 3
ORDER BY 3 ASC;
```

<LineChart data = {k8s_vs_docker} y={["k8s_cnt", "docker_cnt"]} x=date />

# RESTful vs GraphQL vs gRPC mentioned on hackernews

```restful_vs_graphql_vs_grpc
SELECT
    sum(lower(concat_ws(' ', title, url, text)) regexp '\\brestful\\b|\\brest api\\b') AS restful_cnt,
    sum(lower(concat_ws(' ', title, url, text)) regexp '\\bgraphql\\b') AS graphql_cnt,
    sum(lower(concat_ws(' ', title, url, text)) regexp '\\bgrpc\\b') AS grpc_cnt,
    DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') AS date
FROM items
WHERE dead = 0 and deleted = 0
GROUP BY 4
ORDER BY 4 ASC;
```

<LineChart data = {restful_vs_graphql_vs_grpc} y={["restful_cnt", "graphql_cnt", "grpc_cnt"]} x=date />

# MySQL vs Postgres vs MongoDB

```mysql_vs_postgres_vs_mongodb
SELECT
    sum(lower(concat_ws(' ', title, url, text)) regexp '\\bmysql\\b') AS mysql_cnt,
    sum(lower(concat_ws(' ', title, url, text)) regexp '\\bpostgres\\b|\\bpostgresql\\b') AS postgres_cnt,
    sum(lower(concat_ws(' ', title, url, text)) regexp '\\bmongodb\\b') AS mongodb_cnt,
    sum(lower(concat_ws(' ', title, url, text)) regexp '\\bsqlite\\b') AS sqlite_cnt,
    DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') AS date
FROM items
WHERE dead = 0 and deleted = 0
GROUP BY 5
ORDER BY 5 ASC;
```

<LineChart data = {mysql_vs_postgres_vs_mongodb} y={["mysql_cnt", "postgres_cnt", "mongodb_cnt", "sqlite_cnt"]} x=date />

# Rust vs Golang mentioned on hackernews

```rust_vs_golang
SELECT
    sum(lower(concat_ws(' ', title, url, text)) regexp '\\brust\\b') AS rust_cnt,
    sum(concat_ws(' ', title, url, text) COLLATE utf8mb4_bin regexp ('\\bGo\\b|\\bGolang\\b')) AS golang_cnt,
    DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') AS date
FROM items
WHERE dead = 0 and deleted = 0
GROUP BY 3
ORDER BY 3 ASC;
```

<LineChart data = {rust_vs_golang} y={["rust_cnt", "golang_cnt"]} x=date />


# React vs Vuejs vs Angular

```react_vs_vue_vs_angular
SELECT
    sum(lower(concat_ws(' ', title, url, text)) regexp '\\breactjs\\b|\\breact.js\\b') AS react_cnt,
    sum(lower(concat_ws(' ', title, url, text)) regexp '\\bvue\\b|\\bvue.js\\b|\\bvuejs\\b') AS vue_cnt,
    sum(lower(concat_ws(' ', title, url, text)) regexp '\\bangularb\\b|\\bangular.js\\b|\\bangularjs\\b') AS angular_cnt,
    sum(lower(concat_ws(' ', title, url, text)) regexp '\\bsvelte\\b') AS svelte_cnt,
    DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') AS date
FROM items
WHERE dead = 0 and deleted = 0
GROUP BY 5
ORDER BY 5 ASC;
```

<LineChart data = {react_vs_vue_vs_angular} y={["react_cnt", "vue_cnt", "angular_cnt", "svelte_cnt"]} x=date />


# Android vs iOS mentioned on hackernews

```android_vs_ios
SELECT
    sum(lower(concat_ws(' ', title, url, text)) regexp '\\bandroid\\b') AS android_cnt,
    sum(concat_ws(' ', title, url, text) regexp '\\bios\\b') AS ios_cnt,
    DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') AS date
FROM items
WHERE dead = 0 and deleted = 0
GROUP BY 3
ORDER BY 3 ASC;
```

<LineChart data = {android_vs_ios} y={["android_cnt", "ios_cnt"]} x=date />


# Google vs Apple mentioned on hackernews

```google_vs_apple
SELECT
    sum(lower(concat_ws(' ', title, url, text)) regexp '\\bgoogle\\b') AS google_cnt,
    sum(concat_ws(' ', title, url, text) regexp '\\bapple\\b') AS apple_cnt,
    sum(concat_ws(' ', title, url, text) regexp '\\amazon\\b') AS amazon_cnt,
    sum(concat_ws(' ', title, url, text) regexp '\\bfacebook\\b') AS facebook_cnt,
    DATE_FORMAT(FROM_UNIXTIME(time), '%Y-%m-01') AS date
FROM items
WHERE dead = 0 and deleted = 0
GROUP BY 5
ORDER BY 5 ASC;
```

<LineChart data = {google_vs_apple} y={["google_cnt", "apple_cnt", "amazon_cnt", "facebook_cnt"]} x=date />

