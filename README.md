# puppet-papertrail

Sets up `rsyslog` to send logs to papertrail over TLS.

Also sets up `remote_syslog` so that other log files can be monitored too.

	class { 'papertrail':
		log_port => '12345',
		extra_logs => [
			'/var/log/nginx/error.log',
			'/var/log/php5-fpm.log',
			'/var/log/mysql.err',
		],
	}

Be sure to change `log_port` to the port number that Papertrail assign you.