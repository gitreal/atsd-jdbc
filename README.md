[![Build Status](https://secure.travis-ci.org/axibase/atsd-jdbc.png?branch=master)](https://travis-ci.org/axibase/atsd-jdbc)  [![Codacy Badge](https://api.codacy.com/project/badge/grade/4cdddfc67ef742818be7d81d8f53aebc)](https://www.codacy.com/app/alexey-reztsov/atsd-jdbc)
[![Dependency Status](https://www.versioneye.com/user/projects/56e93b274e714c003625c322/badge.svg)](https://www.versioneye.com/user/projects) 
[![License](https://img.shields.io/badge/License-Apache%202-blue.svg)](http://www.apache.org/licenses/LICENSE-2.0)
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/com.axibase/atsd-jdbc/badge.svg)](https://maven-badges.herokuapp.com/maven-central/com.axibase/atsd-jdbc)

# JDBC driver

The driver is designed to provide a convenient way to access Axibase Time Series Database via SQL. The internal communication is implemented by means of transferring resultsets in CSV format via HTTP or HTTPS protocols. See the [SQL API Documentation](http://axibase.com/atsd/api/#sql) to find a description of the query format, a list of supported SQL functions, and other useful information.

## Compatibility

Product / Date | 2016-03-15 | 2016-03-29 | TBA
--- | --- | --- | ---
| JDBC Driver  | 1.2.1 | 1.2.6  | 1.3.x
| ATSD Version | 12400 | 12500+ | 


## JDBC Connection Properties Supported by Driver

Property Name | Valid Values | Default
--- | --- | ---
trustServerCertificate | true, false | `false`
strategy | file, stream | `stream`


## Apache Maven

Add dependency to pom.xml.

```xml
<dependency>
    <groupId>com.axibase</groupId>
    <artifactId>atsd-jdbc</artifactId>
    <version>1.2.6</version>
</dependency>
```

Alternatively, you can build the project yourself.

```bash
$ mvn clean install -DskipTests=true
```

## Classpath

If you do not use a build manager such as Maven, you can download a JAR library from Maven Central: [Direct URL](http://search.maven.org/#search%7Cgav%7C1%7Cg%3A%22com.axibase%22%20AND%20a%3A%22atsd-jdbc%22) and add it to the classpath of your application.

```
* Unix: java -cp "atsd-jdbc-1.2.6.jar:lib/*" your.package.MainClass
* Windows java -cp "atsd-jdbc-1.2.6.jar;lib/*" your.package.MainClass
```

## Database Tools

You can also use a universal database manager, for example [DbVisualizer](https://www.dbvis.com). Follow instructions in the manager's user guide to create a custom driver based on the JAR file from the link above.

## JDBC URL

ATSD JDBC driver prefix is "jdbc:axibase:atsd:". Following the prefix is the http/https URL of the ATSD SQL API endpoint. If necessary, add JDBC Connection properties listed above.

```
Examples:

jdbc:axibase:atsd:http://atsd_hostname:8088/api/sql
jdbc:axibase:atsd:http://atsd_hostname:8088/api/sql;strategy=stream
jdbc:axibase:atsd:https://atsd_hostname:8443/api/sql;trustServerCertificate=true;strategy=file
```

## License

The project is released under version 2.0 of the [Apache License](http://www.apache.org/licenses/LICENSE-2.0).

## Requirements

* Java 1.7 and later

## Supported Data Types

| TYPE NAME | CASE SENSITIVE | DATA TYPE | PRECISION  |
|:---------:|---------------:|----------:|-----------:|
| DECIMAL | false | 3 | -1 |
| DOUBLE | false | 8 | 52 |
| FLOAT | false | 6 | 23 |
| INTEGER | false | 4 | 10 |
| LONG | false | -5 | 19 |
| SHORT | false | 5 | 5 |
| STRING | true  | 12 | 2147483647 |
| TIMESTAMP | false | 93 | 23 |

## Database Capabilities

| Feature | Value |
|:--------|:------|
| All Procedures Are Callable |  false  |
| All Tables Are Selectable |  false  |
| Auto Commit Failure Closes All Result Sets |  false  |
| Catalog Separator |  .  |
| Catalog Term |  catalog  |
| Database Major Version |  12500  |
| Database Minor Version |  0  |
| Data Definition Causes Transaction Commit |  false  |
| Data Definition Ignored In Transactions |  false  |
| Default Transaction Isolation |  0  |
| Does Max Row Size Include Blobs |  false  |
| Driver Major Version |  1  |
| Driver Minor Version |  2  |
| Extra Name Characters |    |
| Generated Key Always Returned |  false  |
| Identifier Quote String |  "  |
| Is Catalog At Start |  false  |
| Is Read Only |  true  |
| JDBCMajor Version |  4  |
| JDBCMinor Version |  1  |
| Locators Update Copy |  false  |
| Max Binary Literal Length |  0  |
| Max Catalog Name Length |  0  |
| Max Char Literal Length |  0  |
| Max Column Name Length |  0  |
| Max Columns In Group By |  0  |
| Max Columns In Index |  0  |
| Max Columns In Order By |  0  |
| Max Columns In Select |  0  |
| Max Columns In Table |  0  |
| Max Connections |  0  |
| Max Cursor Name Length |  0  |
| Max Index Length |  0  |
| Max Procedure Name Length |  0  |
| Max Row Size |  0  |
| Max Schema Name Length |  0  |
| Max Statement Length |  0  |
| Max Statements |  0  |
| Max Table Name Length |  0  |
| Max Tables In Select |  0  |
| Max User Name Length |  0  |
| Null Plus Non Null Is Null |  true  |
| Nulls Are Sorted At End |  true  |
| Nulls Are Sorted At Start |  false  |
| Nulls Are Sorted High |  false  |
| Nulls Are Sorted Low |  false  |
| Procedure Term |  procedure  |
| Result Set Holdability |  1  |
| Schema Term |  schema  |
| Search String Escape |  \  |
| SQL State Type |  2  |
| Stores Lower Case Identifiers |  true  |
| Stores Lower Case Quoted Identifiers |  true  |
| Stores Mixed Case Identifiers |  false  |
| Stores Mixed Case Quoted Identifiers |  false  |
| Stores Upper Case Identifiers |  false  |
| Stores Upper Case Quoted Identifiers |  false  |
| Supports Alter Table With Add Column |  false  |
| Supports Alter Table With Drop Column |  false  |
| Supports ANSI92 Entry Level SQL |  false  |
| Supports ANSI92 Full SQL |  false  |
| Supports ANSI92 Intermediate SQL |  false  |
| Supports Batch Updates |  false  |
| Supports Catalogs In Data Manipulation |  false  |
| Supports Catalogs In Index Definitions |  false  |
| Supports Catalogs In Privilege Definitions |  false  |
| Supports Catalogs In Procedure Calls |  false  |
| Supports Catalogs In Table Definitions |  false  |
| Supports Column Aliasing |  true  |
| Supports Convert |  false  |
| Supports Core SQLGrammar |  false  |
| Supports Correlated Subqueries |  false  |
| Supports Data Definition And Data Manipulation Transactions |  false  |
| Supports Data Manipulation Transactions Only |  true  |
| Supports Different Table Correlation Names |  false  |
| Supports Expressions In Order By |  true  |
| Supports Extended SQLGrammar |  false  |
| Supports Full Outer Joins |  true  |
| Supports Get Generated Keys |  false  |
| Supports Group By |  true  |
| Supports Group By Beyond Select |  true  |
| Supports Group By Unrelated |  true  |
| Supports Integrity Enhancement Facility |  false
| Supports Like Escape Clause |  true  |
| Supports Limited Outer Joins |  true  |
| Supports Minimum SQLGrammar |  false  |
| Supports Mixed Case Identifiers |  true  |
| Supports Mixed Case Quoted Identifiers |  true
| Supports Multiple Open Results |  false  |
| Supports Multiple Result Sets |  false  |
| Supports Multiple Transactions |  false  |
| Supports Named Parameters |  false  |
| Supports Non Nullable Columns |  true  |
| Supports Open Cursors Across Commit |  false  |
| Supports Open Cursors Across Rollback |  false  |
| Supports Open Statements Across Commit |  false  |
| Supports Open Statements Across Rollback |  false  |
| Supports Order By Unrelated |  true  |
| Supports Outer Joins |  true  |
| Supports Positioned Delete |  false  |
| Supports Positioned Update |  false  |
| Supports Savepoints |  false  |
| Supports Schemas In Data Manipulation |  false  |
| Supports Schemas In Index Definitions |  false  |
| Supports Schemas In Privilege Definitions |  false  |
| Supports Schemas In Procedure Calls |  false  |
| Supports Schemas In Table Definitions |  false  |
| Supports Select For Update |  false  |
| Supports Statement Pooling |  false  |
| Supports Stored Functions Using Call Syntax |  false  |
| Supports Stored Procedures |  false  |
| Supports Subqueries In Comparisons |  false  |
| Supports Subqueries In Exists |  false  |
| Supports Subqueries In Ins |  false  |
| Supports Subqueries In Quantifieds |  false  |
| Supports Table Correlation Names |  false  |
| Supports Transactions |  false  |
| Supports Union |  false  |
| Supports Union All |  false  |
| Uses Local File Per Table |  false  |
| Uses Local Files |  false  |

## Usage

First, make sure your ATSD instance is started and you have valid credentials to access it. To execute a query, open a connection, create a SQL statement, execute the query and process the resultset:

```java
        Class.forName("com.axibase.tsd.driver.jdbc.AtsdDriver");
	Connection connection = DriverManager.getConnection("jdbc:axibase:atsd:" + 
		<ATDS_URL>, <ATSD_LOGIN>, <ATSD_PASSWORD>);
	Statement statement = connection.createStatement();
	ResultSet resultSet = statement.executeQuery(<SQL_QUERY>);

```

The same pattern applies to prepared statements:

```java
        Class.forName("com.axibase.tsd.driver.jdbc.AtsdDriver");
	Connection connection = DriverManager.getConnection("jdbc:axibase:atsd:" + 
		<ATDS_URL>, <ATSD_LOGIN>, <ATSD_PASSWORD>);
	PreparedStatement prepareStatement = connection.prepareStatement(<SQL_QUERY>);
	ResultSet resultSet = prepareStatement.executeQuery();

}
```

To check how the driver works, run the following example:

```java

	Class.forName("com.axibase.tsd.driver.jdbc.AtsdDriver");
	
	String url = "jdbc:axibase:atsd:https://10.102.0.6:8443/api/sql;trustServerCertificate=true";
	String query = "SELECT entity, datetime, value, tags.mount_point, tags.file_system "
		+ "FROM df.disk_used_percent WHERE entity = 'NURSWGHBS001' AND datetime > now - 1 * HOUR LIMIT 10";
		
	try (Connection connection = DriverManager.getConnection(url, "axibase", "axibase");
		Statement statement = connection.createStatement();
		ResultSet resultSet = statement.executeQuery(query);) {
		
			int rowNumber = 1;
			while (resultSet.next()) {
				System.out.print(rowNumber++);
				System.out.print("\tentity = " + resultSet.getString("entity"));
				System.out.print("\tdatetime = " + resultSet.getTimestamp("datetime").toString());
				System.out.print("\tvalue = " + resultSet.getString("value"));
				System.out.print("\ttags.mount_point = " + resultSet.getString("tags.mount_point"));
				System.out.println("\ttags.file_system = " + resultSet.getString("tags.file_system"));
			}
			
			final SQLWarning warnings = resultSet.getWarnings();
			if (warnings != null)
				warnings.printStackTrace();
	}
	
```

Results:

```

 1 entity = nurswghbs001 datetime = 2016-03-22 12:52:03.0 value = 28.8116 tags.mount_point = / tags.file_system = /dev/md2
 2 entity = nurswghbs001 datetime = 2016-03-22 12:52:04.0 value = 28.8116 tags.mount_point = / tags.file_system = /dev/md2
 3 entity = nurswghbs001 datetime = 2016-03-22 12:52:18.0 value = 28.8116 tags.mount_point = / tags.file_system = /dev/md2
 4 entity = nurswghbs001 datetime = 2016-03-22 12:52:19.0 value = 28.8116 tags.mount_point = / tags.file_system = /dev/md2
 5 entity = nurswghbs001 datetime = 2016-03-22 12:52:33.0 value = 28.8117 tags.mount_point = / tags.file_system = /dev/md2
 6 entity = nurswghbs001 datetime = 2016-03-22 12:52:34.0 value = 28.8117 tags.mount_point = / tags.file_system = /dev/md2
 7 entity = nurswghbs001 datetime = 2016-03-22 12:52:48.0 value = 28.8117 tags.mount_point = / tags.file_system = /dev/md2
 8 entity = nurswghbs001 datetime = 2016-03-22 12:52:49.0 value = 28.8117 tags.mount_point = / tags.file_system = /dev/md2
 9 entity = nurswghbs001 datetime = 2016-03-22 12:53:03.0 value = 28.8117 tags.mount_point = / tags.file_system = /dev/md2
10 entity = nurswghbs001 datetime = 2016-03-22 12:53:04.0 value = 28.8117 tags.mount_point = / tags.file_system = /dev/md2

```

The following example shows how to extract metadata from the ATSD database:

```java

	Class.forName("com.axibase.tsd.driver.jdbc.AtsdDriver");
	
	String url = "jdbc:axibase:atsd:https://10.102.0.6:8443/api/sql;trustServerCertificate=true";
	
	try (Connection connection = DriverManager.getConnection(url, "axibase", "axibase");
		Statement statement = connection.createStatement();) {
		
		DatabaseMetaData metaData = connection.getMetaData();
		String databaseProductName = metaData.getDatabaseProductName();
		String databaseProductVersion = metaData.getDatabaseProductVersion();
		String driverName = metaData.getDriverName();
		String driverVersion = metaData.getDriverVersion();
		System.out.println("Product Name:   \t" + databaseProductName);
		System.out.println("Product Version:\t" + databaseProductVersion);
		System.out.println("Driver Name:    \t" + driverName);
		System.out.println("Driver Version: \t" + driverVersion);
		System.out.println("\nTypeInfo:");
		
		ResultSet rs = metaData.getTypeInfo();
		while (rs.next()) {
			String name = rs.getString("TYPE_NAME");
			int type = rs.getInt("DATA_TYPE");
			int precision = rs.getInt("PRECISION");
			boolean isCS = rs.getBoolean("CASE_SENSITIVE");
			System.out.println(String.format(
				"\tName:%s \tCS: %s \tType: %s \tPrecision: %s", name, isCS, type, precision));
		}
		System.out.println("\nTableTypes:");
		
		rs = metaData.getTableTypes();
		while (rs.next()) {
			String type = rs.getString(1);
			System.out.println('\t' + type);
		}
		rs = metaData.getCatalogs();
		
		while (rs.next()) {
			String catalog = rs.getString(1);
			System.out.println("\nCatalog: \t" + catalog);
			ResultSet rs1 = metaData.getSchemas(catalog, null);
			while (rs1.next()) {
				String schema = rs1.getString(1);
				System.out.println("Schema: \t" + schema);
			}
		}
	}
		
```

Results:

```
Product Name:   	Axibase
Product Version:	Axibase Time Series Database, <ATSD_EDITION>, Revision: <ATSD_REVISION_NUMBER>
Driver Name:    	ATSD JDBC driver
Driver Version: 	<DRIVER_VERSION>

TypeInfo:
	Name: DECIMAL      	CS: false 	Type: 3    	Precision: -1
	Name: DOUBLE      	CS: false 	Type: 8    	Precision: 52
	Name: FLOAT      	CS: false 	Type: 6    	Precision: 23
	Name: INTEGER      	CS: false 	Type: 4    	Precision: 10
	Name: LONG      	CS: false 	Type: -5    Precision: 19
	Name: SHORT      	CS: false 	Type: 5    	Precision: 5
	Name: STRING      	CS: true 	Type: 12    Precision: 2147483647
	Name: TIMESTAMP     CS: false 	Type: 93    Precision: 23

TableTypes:
	TABLE
	VIEW
	SYSTEM
	
Catalog: 	ATSD
Schema: 	Axibase

```

## Spring Framework Integration

We recommend [Spring Data JDBC](https://github.com/nurkiewicz/spring-data-jdbc-repository) library to integrate ATSD JDBC driver. You can find an example on how to use it [here](https://github.com/axibase/atsd-jdbc-test/tree/master/src/main/java/com/axibase/tsd/driver/jdbc/spring).

[config file](https://github.com/axibase/atsd-jdbc-test/blob/master/src/main/java/com/axibase/tsd/driver/jdbc/spring/AtsdRepositoryConfig.java) gist:

```java

	@Configuration
	public class AtsdRepositoryConfig {

	@Bean
	public SqlGenerator sqlGenerator() {
		return new AtsdSqlGenerator();
	}

	@Bean
	public DataSource dataSource() {
		final HikariDataSource dataSource = new HikariDataSource();
		dataSource.setJdbcUrl(url);
		dataSource.setUsername(login);
		dataSource.setPassword(password);
		dataSource.setReadOnly(true);
		return dataSource;
	}

	@Bean
	public EntityValueDoubleRepository entityRepository() {
		return new EntityValueDoubleRepository(table);
	}

}
```

[repository file](https://github.com/axibase/atsd-jdbc-test/blob/master/src/main/java/com/axibase/tsd/driver/jdbc/spring/EntityValueDoubleRepository.java) gist:

```java

	@Repository
	public class EntityValueDoubleRepository extends JdbcRepository<EntityValueDouble, Double> {

	public EntityValueDoubleRepository(String table) {
		super(ROW_MAPPER, new MissingRowUnmapper<EntityValueDouble>(), table);
	}

	public static final RowMapper<EntityValueDouble> ROW_MAPPER = new RowMapper<EntityValueDouble>() {
		@Override
		public EntityValueDouble mapRow(ResultSet rs, int rowNum) throws SQLException {
			return new EntityValueDouble(rs.getString("entity"), rs.getLong("time"), rs.getDouble("value"));
		}
	};

}
```

There is a sample how to use it with 
[Spring Boot](https://github.com/axibase/atsd-jdbc-test/blob/master/src/main/java/com/axibase/tsd/driver/jdbc/spring/SampleDriverApplication.java):

```java

	@Resource
	private EntityValueDoubleRepository entityRepository;

	@Override
	public void run(String... args) throws Exception {
		PageRequest page = new PageRequest(0, 1000, Direction.DESC, "time", "value");
		Page<EntityValueDouble> result = entityRepository.findAll(page);
		List<EntityValueDouble> list = result.getContent();
		assert list != null && !list.isEmpty();
	}

```
