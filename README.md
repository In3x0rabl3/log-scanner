
# Using the scanner

```
$ ./local-log4j-vuln-scanner [--verbose] [--quiet] [--ignore-v1] \
    [--exclude /path/to/exclude …] [--log /path/to/file.log] \
    /path/to/app1 /path/to/app2 …
```

The `--verbose` flag will show every .jar and .war file checked, even if no problem is found.

The `--quiet` flag will supress output except for indicators of a known vulnerability.

The `--ignore-v1` flag will _exclude_ checks for log4j 1.x vulnerabilities.

The `--log` flag allows everythig to be written to a log file instead of stdout/stderr.

Use the `--exclude` flag to exclude subdirectories from being scanned. Can be used multiple times.

If class files indicating one of the vulnerabilities are found,
messages like the following are printed to standard output:
``` console
./local-log4j-vuln-scanner - a simple local log4j vulnerability scanner

indicator for vulnerable component found in /path/to/vuln/log4shell-vulnerable-app-0.0.1-SNAPSHOT.war::WEB-INF/lib/log4j-core-2.14.1.jar (org/apache/logging/log4j/core/net/JndiManager$JndiManagerFactory.class): log4j 2.14.0-2.14.1
indicator for vulnerable component found in /path/to/vuln/log4shell-vulnerable-app-0.0.1-SNAPSHOT.war::WEB-INF/lib/log4j-core-2.14.1.jar (org/apache/logging/log4j/core/net/JndiManager.class): log4j 2.14.0-2.14.1

Scan finished
```

