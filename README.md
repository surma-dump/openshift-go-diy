This is a cartridge for Red Hat's [OpenShift](https://openshift.redhat.com) to enable [Go](http://golang.org) support.

Usage
=====

* Create a DIY cartridge for your OpenShift app
* (Fork and) Clone this repository
* Add a folder named like your app to the root of this repository
* Add all your code in this directory, you can have subpackages and multiple executables. Keep in mind that you *have* to bind your webserver to `$OPENSHIFT_INTERNAL_IP:8080`
* Optional: Adjust cron scripts (See OpenShift's [documentation](http://docs.redhat.com/docs/en-US/OpenShift/2.0/html/User_Guide/index.html) for details)
* Commit and push

Example
=======

Assuming I created an OpenShift app named "testapp":

	.
	├── testapp
	│   ├── subpackage
	│   │   └── really_hard_math.go
	│   ├── cronjob
	│   │   └── main.go
	│   └── main.go
	├── README
	└── static

Both `main.go` contain simple "Hello World" go apps. Since the `go` tool is used for building, the executables will be named `testapp` and `cronjob`. `subpackage` has the import path `testapp/subpackage`.
