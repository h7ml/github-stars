---
project: juice
stars: 88
description: Like Mybatis but for golang.
url: https://github.com/go-juicedev/juice
---

Juice SQL Mapper Framework For Golang
-------------------------------------

Juice is a SQL mapper framework for Golang, inspired by MyBatis. It is simple, lightweight, and easy to use and extend. This document provides a brief introduction to Juice and its usage.

-   Installation
-   Example
-   API Documentation
-   License
-   Support Me

### Installation

To install Juice, use the following command:

go get github.com/go-juicedev/juice

### Example

touch config.xml

add the following content to config.xml

<?xml version\="1.0" encoding\="UTF-8"?>
<!DOCTYPE configuration PUBLIC "-//juice.org//DTD Config 1.0//EN"
        "https://raw.githubusercontent.com/eatmoreapple/juice/main/config.dtd">

<configuration\>
    <environments default\="prod"\>
        <environment id\="prod"\>
            <dataSource\>root:qwe123@tcp(localhost:3306)/database</dataSource\>
            <driver\>mysql</driver\>
        </environment\>
    </environments\>

    <mappers\>
        <mapper resource\="mappers.xml"/>
    </mappers\>
</configuration\>

touch mappers.xml

add the following content to mappers.xml

<?xml version\="1.0" encoding\="utf-8" ?>
<!DOCTYPE mapper PUBLIC "-//juice.org//DTD Config 1.0//EN"
        "https://raw.githubusercontent.com/eatmoreapple/juice/main/mapper.dtd">

<mapper namespace\="main.Repository"\>
    <select id\="HelloWorld"\>
        <if test\="1 == 1"\>  <!-- always be true \-->
            select "hello world"
        </if\>
    </select\>
</mapper\>

touch main.go

add the following content to main.go

package main

import (
	"context"
	"fmt"
	
	"github.com/go-juicedev/juice"
	\_ "github.com/go-sql-driver/mysql"
)

type Repository interface {
	HelloWorld(ctx context.Context) (string, error)
}

type RepositoryImpl struct{}

func (r RepositoryImpl) HelloWorld(ctx context.Context) (string, error) {
	manager := juice.ManagerFromContext(ctx)
	var iface Repository \= r
	executor := juice.NewGenericManager\[string\](manager).Object(iface.HelloWorld)
	return executor.QueryContext(ctx, nil)
}

func main() {
	cfg, err := juice.NewXMLConfiguration("config.xml")
	if err != nil {
		panic(err)
	}
	
	engine, err := juice.Default(cfg)
	if err != nil {
		panic(err)
	}
	defer engine.Close()
	
	ctx := juice.ContextWithManager(context.Background(), engine)
	repo := RepositoryImpl{}
	result, err := repo.HelloWorld(ctx)
	fmt.Println(result, err) // hello world <nil>
}

go run main.go

### API Documentation

English 简体中文

### License

Juice is licensed under the Apache License, Version 2.0. See LICENSE for the full license text.

Support Me
----------

If you like my work, please consider supporting me by buying me a coffee.
