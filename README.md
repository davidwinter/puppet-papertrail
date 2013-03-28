# puppet-papertrail

Sets up `rsyslog` to send logs to papertrail over TLS. Also sets up `remote_syslog` so that other log files can be monitored too.

**Note:** Be sure to change `log_port` parameter to the port number that Papertrail assign you.

## Install

With librarian-puppet, add the following to your Puppetfile:

	mod 'papertrail',
		:git => 'git://github.com/davidwinter/puppet-papertrail.git'

Then run `librarian-puppet install`.

## Usage

	class { 'papertrail':
		log_port   => '12345',
		extra_logs => [
			'/var/log/nginx/error.log',
			'/var/log/php5-fpm.log',
			'/var/log/mysql.err',
		],
	}

You can add as many additional log files to the `extra_logs` parameter array as you want it to monitor.

## Author

David Winter <i@djw.me>

## Licence

MIT
