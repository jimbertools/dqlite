# GORM Dqlite Driver


We adjusted the SQLite driver to support DQLite



![CI](https://github.com/go-gorm/sqlite/workflows/CI/badge.svg)

## USAGE

```go

import (
"github.com/canonical/go-dqlite/app"
	"github.com/jimbertools/dqlite"
)
dir := filepath.Join("/tmp/dqlite-data/", address)
	if err := os.MkdirAll(dir, 0755); err != nil {
		fmt.Errorf("can't create %s: %v", dir, err)
	}
	// Set own address and specify all existing nodes in the cluster.
	options := []app.Option{app.WithAddress(address), app.WithCluster(peers)} //
	app, err := app.New(dir, options...)
	if err != nil {
		log.Fatal(err)
	}

	gormdb, err := gorm.Open(dqlite.Open(app, "my-database"), &gorm.Config{})

```
