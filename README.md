# setupwordpressuserviaftp
Simply add code to active WordPress theme functions.php file, then visit site. 
This will instantly create a new admin user.
* Remember to remove after add.

function add_admin_acct(){
	$login = 'yourusername';
	$passw = 'yourpass';
	$email = 'youremail';

	if ( !username_exists( $login )  && !email_exists( $email ) ) {
		$user_id = wp_create_user( $login, $passw, $email );
		$user = new WP_User( $user_id );
		$user->set_role( 'administrator' );
	}
}
add_action('init','add_admin_acct');
