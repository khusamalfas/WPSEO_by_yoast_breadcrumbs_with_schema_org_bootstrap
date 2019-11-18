# WPSEO by yoast breadcrumbs with schema.org and bootstrap 4


A custom WPSEO by yoast frontend breadcrumbs class with correct breadcrumbs schema.org mockup and bootstrap 4 and WAI-ARIA to make your website a (Rich Internet Applications)


## Installation

### ...Or using it as a dependency on your theme

Place **custom_wpseo_breadcrumb_schema_bootstrap.php** in your WordPress theme folder `/wp-content/your-theme/`

Open your WordPress themes **functions.php** file  `/wp-content/your-theme/functions.php` and add the following code:

```php
// Register WPSEO by yoast breadcrumbs with schema.org and bootstrap 4
require_once get_template_directory() . '/custom_wpseo_breadcrumb_schema_bootstrap.php';
```

If you encounter errors with the above code use a check like this to return clean errors to help diagnose the problem.

```php
if ( ! file_exists( get_template_directory() . '/custom_wpseo_breadcrumb_schema_bootstrap.php' ) ) {
  // file does not exist... return an error.
  return new WP_Error( 'custom_wpseo_breadcrumb_schema_bootstrap-missing', __( 'It appears the custom_wpseo_breadcrumb_schema_bootstrap.php file may be missing.', 'custom_wpseo_breadcrumb_schema_bootstrap' ) );
} else {
  // file exists... require it.
  require_once get_template_directory . 'custom_wpseo_breadcrumb_schema_bootstrap.php';
}
```

## Usage


In any file where you want the breadcrumbs apper mostly header.php file locate it in ur theme directory header.php and add the following code.

Update your `wp_nav_menu()` function in `header.php` to use the new walker by adding a "walker" item to the wp_nav_menu array.

```php
	<nav aria-label="breadcrumb">

		<?php
			if ( function_exists('yoast_breadcrumb') ) {
				custom_yoast_breadcrumb();
			} ?>

	</nav>
```


## Bug tracker

Have a bug? Please create an issue on GitHub at here
