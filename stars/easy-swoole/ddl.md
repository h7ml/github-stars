---
project: ddl
stars: 5
description: null
url: https://github.com/easy-swoole/ddl
---

DDL
===

数据库模式定义语言DDL(Data Definition Language)，是用于描述数据库中要存储的现实世界实体的语言。  
其实就是我们在创建表的时候用到的一些sql，比如说：CREATE、ALTER、DROP等。

测试代码
----

#### CreateTable

use EasySwoole\\DDL\\Blueprint\\Create\\Table as CreateTable;
use EasySwoole\\DDL\\DDLBuilder;
use EasySwoole\\DDL\\Enum\\Character;
use EasySwoole\\DDL\\Enum\\Engine;
use EasySwoole\\DDL\\Enum\\Foreign;

$sql = DDLBuilder::create('user', function (CreateTable $table) {
    $table\->setIfNotExists()->setTableComment('用户表');   //设置表名称/
    $table\->setTableEngine(Engine::MYISAM);                //设置表引擎
    $table\->setTableCharset(Character::UTF8MB4\_GENERAL\_CI);//设置表字符集
    $table\->int('user\_id', 10)->setColumnComment('用户ID')->setIsAutoIncrement()->setIsPrimaryKey();  //创建user\_id设置主键并自动增长
    $table\->varchar('username', 30)->setIsNotNull()->setColumnComment('用户名')->setDefaultValue('');
    $table\->char('sex', 1)->setIsNotNull()->setColumnComment('性别：1男，2女')->setDefaultValue(1);
    $table\->tinyint('age')->setIsNotNull()->setColumnComment('年龄')->setIsUnsigned();
    $table\->text('intro')->setIsNotNull()->setColumnComment('简介');
    $table\->date('birthday')->setIsNotNull()->setColumnComment('出生日期');
    $table\->decimal('money', 10, 2)->setIsNotNull()->setColumnComment('金额')->setDefaultValue(0);
    $table\->int('created\_at', 10)->setIsNotNull()->setColumnComment('创建时间');
    $table\->int('updated\_at', 10)->setIsNotNull()->setColumnComment('更新时间');
    $table\->unique('username\_index', 'username')->setIndexComment('用户名唯一索引');//设置索引
    $table\->normal('username\_age\_index', \['username', 'age'\])->setIndexComment('用户名-年龄');
});
//以下是生成的sql的语句
CREATE TABLE IF NOT EXISTS \`user\` (
  \`user\_id\` int(10) NOT NULL PRIMARY KEY AUTO\_INCREMENT COMMENT '用户ID',
  \`username\` varchar(30) NOT NULL DEFAULT '' COMMENT '用户名',
  \`sex\` char(1) NOT NULL DEFAULT 1 COMMENT '性别：1男，2女',
  \`age\` tinyint UNSIGNED NOT NULL COMMENT '年龄',
  \`intro\` text NOT NULL COMMENT '简介',
  \`birthday\` date NOT NULL COMMENT '出生日期',
  \`money\` decimal(10,2) NOT NULL DEFAULT 0 COMMENT '金额',
  \`created\_at\` int(10) NOT NULL COMMENT '创建时间',
  \`updated\_at\` int(10) NOT NULL COMMENT '更新时间',
  UNIQUE INDEX \`username\_index\` (\`username\`) COMMENT '用户名唯一索引',
  INDEX \`username\_age\_index\` (\`username\`,\`age\`) COMMENT '用户名-年龄'
)
ENGINE = MYISAM DEFAULT COLLATE = 'utf8mb4\_general\_ci' COMMENT = '用户表';
 
------------------------------------------------------------------------------------
 
$stuSql = DDLBuilder::create('student', function (CreateTable $table) {
    $table\->setIfNotExists()->setTableComment('学生表');          //设置表名称
    $table\->setTableCharset(Character::UTF8MB4\_GENERAL\_CI);     //设置表字符集
    $table\->setTableEngine(Engine::INNODB);                     //设置表引擎
    $table\->setTableAutoIncrement(100);                    //设置表起始自增数
    $table\->int('stu\_id')->setIsAutoIncrement()->setIsPrimaryKey()->setIsUnsigned()->setColumnComment('学生ID');  //创建stu\_id设置主键并自动增长
    $table\->varchar('stu\_name', 30)->setColumnComment('学生姓名');
    $table\->char('sex', 1)->setColumnComment('性别：1男，2女')->setDefaultValue(1);
    $table\->int('age', 2)->setColumnComment('年龄')->setDefaultValue(0);
    $table\->date('birthday')->setIsNotNull(false)->setColumnComment('出生日期');
    $table\->int('created\_at', 10)->setColumnComment('创建时间');
    $table\->int('updated\_at', 10)->setColumnComment('更新时间');
    $table\->normal('ind\_stu\_name', 'stu\_name')->setIndexComment('学生姓名--普通索引');//设置索引
    $table\->normal('ind\_age', 'age')->setIndexComment('学生年龄--普通索引');//设置索引
});

CREATE TABLE IF NOT EXISTS \`student\` (
  \`stu\_id\` int UNSIGNED NOT NULL PRIMARY KEY AUTO\_INCREMENT COMMENT '学生ID',
  \`stu\_name\` varchar(30) NOT NULL COMMENT '学生姓名',
  \`sex\` char(1) NOT NULL DEFAULT 1 COMMENT '性别：1男，2女',
  \`age\` int(2) NOT NULL DEFAULT 0 COMMENT '年龄',
  \`birthday\` date NULL DEFAULT NULL COMMENT '出生日期',
  \`created\_at\` int(10) NOT NULL COMMENT '创建时间',
  \`updated\_at\` int(10) NOT NULL COMMENT '更新时间',
  INDEX \`ind\_stu\_name\` (\`stu\_name\`) COMMENT '学生姓名--普通索引',
  INDEX \`ind\_age\` (\`age\`) COMMENT '学生年龄--普通索引'
)
ENGINE = INNODB AUTO\_INCREMENT = 100 DEFAULT COLLATE = 'utf8mb4\_general\_ci' COMMENT = '学生表';

------------------------------------------------------------------------------------
 
$courseSql = DDLBuilder::create('course', function (CreateTable $table) {
    $table\->setIfNotExists()->setTableComment('课程表');          //设置表名称
    $table\->setTableCharset(Character::UTF8MB4\_GENERAL\_CI);     //设置表字符集
    $table\->setTableEngine(Engine::INNODB);                     //设置表引擎
    $table\->int('id', 3)->setIsPrimaryKey()->setIsAutoIncrement()->setIsUnsigned()->setZeroFill()->setColumnComment('课程id');
    $table\->varchar('course\_name', 100)->setColumnComment('课程名称');
    $table\->char('status', 1)->setDefaultValue(1)->setColumnComment('课程状态：1正常，0隐藏');
    $table\->int('created\_at', 10)->setColumnComment('创建时间');
    $table\->int('updated\_at', 10)->setColumnComment('更新时间');
    $table\->unique('uni\_course\_name', 'course\_name')->setIndexComment('课程名称--唯一索引');//设置索引
});

CREATE TABLE IF NOT EXISTS \`course\` (
  \`id\` int(3) UNSIGNED ZEROFILL NOT NULL PRIMARY KEY AUTO\_INCREMENT COMMENT '课程id',
  \`course\_name\` varchar(100) NOT NULL COMMENT '课程名称',
  \`status\` char(1) NOT NULL DEFAULT 1 COMMENT '课程状态：1正常，0隐藏',
  \`created\_at\` int(10) NOT NULL COMMENT '创建时间',
  \`updated\_at\` int(10) NOT NULL COMMENT '更新时间',
  UNIQUE INDEX \`uni\_course\_name\` (\`course\_name\`) COMMENT '课程名称--唯一索引'
)
ENGINE = INNODB DEFAULT COLLATE = 'utf8mb4\_general\_ci' COMMENT = '课程表';
 
------------------------------------------------------------------------------------
 
$scoreSql = DDLBuilder::create('score', function (CreateTable $table) {
    $table\->setIfNotExists()->setTableComment('成绩表');          //设置表名称
    $table\->setTableCharset(Character::UTF8MB4\_GENERAL\_CI);     //设置表字符集
    $table\->setTableEngine(Engine::INNODB);                     //设置表引擎
    $table\->int('id')->setIsUnsigned()->setIsAutoIncrement()->setIsPrimaryKey()->setColumnComment('自增ID');
    $table\->int('stu\_id')->setIsUnsigned()->setColumnComment('学生id');
    $table\->int('course\_id')->setIsUnsigned()->setZeroFill()->setColumnComment('课程id');
    $table\->float('score', 3, 1)->setColumnComment('成绩');
    $table\->int('created\_at', 10)->setColumnComment('创建时间');
    $table\->foreign('fk\_stu\_id', 'stu\_id', 'student', 'stu\_id')
        ->setOnDelete(Foreign::CASCADE)->setOnUpdate(Foreign::CASCADE);
    $table\->foreign('fk\_course\_id', 'course\_id', 'course', 'id')
        ->setOnDelete(Foreign::CASCADE)->setOnUpdate(Foreign::CASCADE);
});

CREATE TABLE IF NOT EXISTS \`score\` (
  \`id\` int UNSIGNED NOT NULL PRIMARY KEY AUTO\_INCREMENT COMMENT '自增ID',
  \`stu\_id\` int UNSIGNED NOT NULL COMMENT '学生id',
  \`course\_id\` int UNSIGNED ZEROFILL NOT NULL COMMENT '课程id',
  \`score\` float(3,1) NOT NULL COMMENT '成绩',
  \`created\_at\` int(10) NOT NULL COMMENT '创建时间',
  CONSTRAINT \`fk\_stu\_id\` FOREIGN KEY (\`stu\_id\`) REFERENCES \`student\` (\`stu\_id\`) ON DELETE CASCADE ON UPDATE CASCADE,
  CONSTRAINT \`fk\_course\_id\` FOREIGN KEY (\`course\_id\`) REFERENCES \`course\` (\`id\`) ON DELETE CASCADE ON UPDATE CASCADE
)
ENGINE = INNODB DEFAULT COLLATE = 'utf8mb4\_general\_ci' COMMENT = '成绩表';

#### AlterTable

use EasySwoole\\DDL\\Blueprint\\Alter\\Table as AlterTable;
use EasySwoole\\DDL\\DDLBuilder;

$alterStuInfoSql = DDLBuilder::alter('student', function (AlterTable $table) {
    $table\->setRenameTable('student\_info')->setTableComment('学生信息表');
    $table\->dropColumn('age');
    $table\->dropIndex('ind\_age');
    $table\->modifyColumn()->varchar('stu\_name', 50)->setColumnComment('学生姓名');
    $table\->changeColumn('sex')->tinyint('gender', 1)->setDefaultValue('2')->setColumnComment('性别：1男，2未知');
    $table\->modifyIndex('ind\_stu\_name')->normal('ind\_stu\_name', 'stu\_name')->setIndexComment('学生姓名--普通索引');
    $table\->addColumn()->varchar('phone', 30)->setColumnComment('学生联系方式');
    $table\->addIndex()->normal('ind\_phone', 'phone')->setIndexComment('学生联系方式-普通索引');
});

ALTER TABLE \`student\` RENAME TO \`student\_info\`;
ALTER TABLE \`student\_info\`
COMMENT = '学生信息表',
DROP \`age\`,
CHANGE \`sex\` \`gender\` tinyint(1) NOT NULL DEFAULT '2' COMMENT '性别：1男，2未知',
MODIFY \`stu\_id\` bigint(20) UNSIGNED NOT NULL PRIMARY KEY AUTO\_INCREMENT COMMENT '学生ID',
ADD \`phone\` varchar(30) NOT NULL COMMENT '学生联系方式',
DROP INDEX \`ind\_age\`,
DROP INDEX \`ind\_stu\_name\`,
ADD INDEX \`ind\_stu\_name\` (\`stu\_name\`) COMMENT '学生姓名--普通索引',
ADD INDEX \`ind\_phone\` (\`phone\`) COMMENT '学生联系方式-普通索引';

------------------------------------------------------------------------------------

$alterStuScoreSql = DDLBuilder::alter('score', function (AlterTable $table) {
    $table\->setRenameTable('student\_score')->setTableComment('学生成绩表');
    $table\->dropForeign('fk\_course\_id');
    $table\->addIndex()->normal('ind\_score', 'score')->setIndexComment('学生成绩--普通索引');
    $table\->modifyForeign('fk\_stu\_id')->foreign('fk\_stu\_id', 'stu\_id', 'student\_info', 'stu\_id');
});

ALTER TABLE \`score\` RENAME TO \`student\_score\`;
ALTER TABLE \`student\_score\`
COMMENT = '学生成绩表',
DROP INDEX \`ind\_score\`,
ADD INDEX \`ind\_score\` (\`score\`) COMMENT '学生成绩--普通索引';
ALTER TABLE \`student\_score\` DROP FOREIGN KEY \`fk\_course\_id\`;
ALTER TABLE \`student\_score\` DROP FOREIGN KEY \`fk\_stu\_id\`;
ALTER TABLE \`student\_score\` ADD CONSTRAINT \`fk\_stu\_id\` FOREIGN KEY (\`stu\_id\`) REFERENCES \`student\_info\` (\`stu\_id\`);

#### DropTable

use EasySwoole\\DDL\\DDLBuilder;

$dropStuScoreSql = DDLBuilder::drop('student\_score');

DROP TABLE \`student\_score\`;

------------------------------------------------------------------------------------

$dropStuScoreSql = DDLBuilder::dropIfExists('student\_score');

DROP TABLE IF EXISTS \`student\_score\`;
