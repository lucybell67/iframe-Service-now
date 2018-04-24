# iframe-Service-now
simple web site
link to site: https://lucybell67.github.io/iframe-Service-now/

test
<meta http-equiv="X-Frame-Options" content="ALLOW-FROM https://dev48352.service-now.com/nav_to.do?uri=%2Fhome.do%3F" height="500px" width="500px" />

<iframe src="https://dev48352.service-now.com/nav_to.do?uri=%2Fhome.do%3F" height="500px" width="500px"></iframe>


function($location, $rootScope) {
	var c = this;
	
	function format(value) {		
		return value.toLowerCase()
			.replace(/[^a-z0-9\-]/gi,'_')
			.replace(/^-|-$/g, '');		
	}
	
	c.submit = function() {
		c.server.update().then(function(response) {
			$rootScope.$broadcast('$sp.widget-close-modal');
			var s = $location.search();
			s.sys_id = c.data.sys_id;
			$location.search(s).replace();
		});
	}
	c.fixID = function(id) {
		if (!id) return;
		c.data.id = format(id.toString());
	}
	
	c.fixPageID = function(id) {
		if (!id) return;
		c.data.test_page_id = format(id.toString());
	}

	// Automatically provide an ID that is based on the name of the widget
	c.updateID = function() {
		c.data.id = format(c.data.name);		
		c.data.test_page_id = format(c.data.name);
	}
		
}

