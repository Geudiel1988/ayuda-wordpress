# ayuda-wordpress
ayudas codigo wordpres php

#header1
<div class="social-media">
		<?php if( have_rows('redes_sociales','option') ): ?>
            <ul id="social-media">
            <?php while( have_rows('redes_sociales','option') ): the_row(); ?>
                <li class="item-social-media">
                    <a href="<?php the_sub_field('link') ?>" target="_blank"> <?php the_sub_field('icono'); ?>a </a>
                </li>
            <?php endwhile; ?>
            </ul>
        <?php endif; ?> 
		</div>

#header
	</div><!-- .site-branding -->
		<div class="social-media">
		<?php if( have_rows('redes_sociales','option') ): ?>
            <ul id="social-media">
            <?php while( have_rows('redes_sociales','option') ): the_row(); ?>
                <li class="item-social-media">
                    <a href="<?php the_sub_field('link') ?>" target="_blank"> <?php the_sub_field('icono'); ?>a </a>
                </li>
            <?php endwhile; ?>
            </ul>
        <?php endif; ?> 
		</div>
		<nav id="site-navigation" class="main-navigation">
			<button class="menu-toggle" aria-controls="primary-menu" aria-expanded="false"><?php esc_html_e( 'Primary Menu', 'rosa' ); ?></button>
			<?php
			wp_nav_menu(
				array(
					'theme_location' => 'menu-1',
					'menu_id'        => 'primary-menu',
				)
			);
			?>
		</nav><!-- #site-navigation -->
		<div class="user">

                        <div class="dropdown">

                            <a class="dropdown-toggle" id="dropdownUser" data-toggle="dropdown" aria-haspopup="true"

                               aria-expanded="true">

                                User

                            </a>

                            <ul class="dropdown-menu pull-right" aria-labelledby="dropdownUser">

                               <?php if (is_user_logged_in()): ?>

                                   <li class="menu-item menu-item-type-post_type menu-item-object-page menu-item-9683">

                                       <a href="<?php echo esc_url(home_url('/')); ?>mi-cuenta/"><?php _e('Mi cuenta', 'wpfelix'); ?></a>

                                   </li>

                                   <li class="menu-item menu-item-type-post_type menu-item-object-page menu-item-9682">

                                       <a href="<?php echo esc_url(home_url('/')); ?>finalizar-compra/"><?php _e('Finalizar compra', 'wpfelix'); ?></a>

                                   </li>

                                   <li class="menu-item menu-item-type-post_type menu-item-object-page menu-item-9682">

                                       <a href="<?php echo esc_url(home_url('/')); ?>mi-cuenta/customer-logout/?_wpnonce=04217afda8"><?php _e('Cerrar sesión', 'wpfelix'); ?></a>

                                   </li>

                               <?php else: ?>

                                   <li class="menu-item menu-item-type-post_type menu-item-object-page menu-item-9682">

                                       <a href="<?php echo esc_url(home_url('/')); ?>mi-cuenta"><?php _e('Iniciar sesión', 'wpfelix'); ?></a>

                                   </li>
                                   <li class="menu-item menu-item-type-post_type menu-item-object-page menu-item-9682">

                                       <a href="<?php echo esc_url(home_url('/')); ?>mi-cuenta#crear_cuenta"><?php _e('Crear cuenta', 'wpfelix'); ?></a>

                                   </li>

                               <?php endif ?>

                            </ul>

                        </div>

                    </div>
		<div class="language">
			<?php echo do_shortcode('[polylang_langswitcher]'); ?>
		</div>
    
    #footer
		<div class="container-info-footer headerMargenes">
			<div class="info-footer-img">
				<?php $image = get_field('logo_footer', 'option'); ?> 
				<?php echo wp_get_attachment_image($image, 'full' ); ?>
				</div>
				<div class="iconos-info-footer">
				<?php if( have_rows('contactos', 'option') ): ?>
					<div id="iconos-info-footer">
					<?php while( have_rows('contactos','option') ): the_row(); ?>
						<div class="icon-social">
						<h3><span class="icon <?php the_sub_field('icon_contacto')?>"></span><?php the_sub_field('dato_contacto')?></h3>
						</div>
						<?php endwhile; ?>
						<p><?php the_field('ciudad', 'option')?></p>
					</div>
					<?php endif; ?> 
				</div>
				<div class="info-footer-text">
					<h3><?php the_field('horarios_atencion', 'option')?></h3>
					<p><?php the_field('info_atencion_telefono', 'option')?></p>
					<h3><?php the_field('horario_atencion_whatsapp', 'option')?></h3>
					<p><?php the_field('info_atenion_whatsapp', 'option')?></p>
				</div>
				<div class="info-footer">
					<h3><?php the_field('politicas', 'option')?> <span></span></h3>
				</div>
			</div>
		<div class="social-media-footer">
		<?php if( have_rows('redes_footer','option') ): ?>
            <ul id="social-media-footer">
            <?php while( have_rows('redes_footer','option') ): the_row(); ?>
                <li class="item-social-media">
                    <a href="<?php the_sub_field('link') ?>" target="_blank"> <?php the_sub_field('icono'); ?>a </a>
                </li>
            <?php endwhile; ?>
            </ul>
        	<?php endif; ?> 
		</div>

		<div class="info-footer-agencia">
			<div class="info-agencia">
				<h3 class="title-agencia"><?php the_field('titulo_agencia', 'option')?></h3>
				<h4 class="registro">
				<?php the_field('registro', 'option')?> 
				</h4>
			</div>
			<div class="copyright">
			<?php the_field('pie_pagina', 'option'); ?>
			</div>
		</div>
    
    #template home
    
    get_header();
$idPage = get_the_ID();
?>

	<main id="primary" class="site-main">
        <div class="container">
        <?php if( have_rows('carusel') ): ?>
            <section id="carrousel">
            <?php while( have_rows('carusel') ): the_row(); 
                $image = get_sub_field('imagen');
                ?>
                <div class="item-carr">
                    <?php echo wp_get_attachment_image( $image, 'full' ); ?>
                    <div class="caption-carrousel">
                        <h4><?php the_sub_field('ubicacion'); ?></h4>
                        <h2><?php the_sub_field('titulo'); ?></h2>
                    </div>
                </div>
            <?php endwhile; ?>
            </section>
        <?php endif; ?>   
        </div>

       <!-- content reservas -->
       <section class="container-reservas">
        <div class="ubicacion">
            <?php 
            $argDestinos = array(
                'taxonomy' => 'destinos','hide_empty' => false,
            );
            $termDestinos = get_categories($argDestinos);
            ?>
            <select name="ubicacion" id="ubicacion">
                <option value="" selected>Destino</option>
                <?php foreach ($termDestinos as $term) : ?>
                    <option value="<?php echo $term->slug ?>"> <?php echo $term->name; ?> </option>
                <?php endforeach; ?>
           </select>
        </div>
        <div class="duracion">
            <input type="date" id="start" name="Duracion"
             value="Duración"
             min="2018-01-01" max="2030-12-31">
        </div>
           <div class="botonReserva">
               <button class="Buscar" type="Buscar">Buscar</button>
           </div>
        
            
       </section>
        <!-- 
            <div class="reservas">
			<?php echo do_shortcode('[reservas]'); ?>
		</div>
        -->
        <!-- end content reservas -->
        <div class="mensaje">
            <h4>
            <?php the_field('banner'); ?>
            </h4>
        </div>
        <?php 
        $argPlanes = array(
            'taxonomy' => 'categorias_planes','hide_empty' => false,
        );
        $termPlanes = get_categories($argPlanes);
        ?>
        
        <?php if( $termPlanes ): ?>
        <section class="container-planes headerMargenes">
            <h2 class="title-planes">
                <?php the_field('title_planes'); ?>
            </h2>
            <div id="my-accordion" class="accordion-slider overflow-hidden position-relative">
                
                <?php foreach ($termPlanes as $term) : ?>
                    <div class="as-panel">
                        <?php $idImagen = get_field('imagen', $term);
                            echo wp_get_attachment_image($idImagen,'full',false,['class'=>'as-background']);
                        ?>
                        <div class="panel-caption" >
                            <h2 class="title-tarjeta"
                            data-horizontal="center" >
                                <?php echo $term->name; ?>
                            </h2>
                            <button class="button-tarjeta" type="submit">reserva ya</button>
                        </div>
                        
                    </div>
                <?php endforeach; ?>
                </div>
        </section>
        <?php endif; ?> 
    

        <section class="container-circulos">
            <?php if( have_rows('circles') ): ?>
            <section id="circulos">
            <?php while( have_rows('circles') ): the_row();
                $image = get_sub_field('icon_circle');
                ?>
                <div class="circulos">
                    <div class="img">
                        <?php echo wp_get_attachment_image( $image, 'full' ); ?>
                    </div>     
                        <h3 class="title-circle"><?php the_sub_field('title_circle'); ?></h3>
                        <p class="text-circle"><?php the_sub_field('text_circle'); ?></p>
                </div>
            <?php endwhile; ?>
            </section>
        <?php endif; ?> 
        </section>

        <section class="destinos headerMargenes">
            <h2 class="title-destinos">
            <?php the_field('title_destinos'); ?>
            </h2>
            <div class="container-destinos">
            <?php 

                $args = array(
                    'post_type' => 'planes',
                    'post_status'=>'publish',
                    'posts_per_page'=> 5,
                    'order'=> 'DESC'

                );
                // the query
                $the_query = new WP_Query( $args ); 
                $cont = 1;
                $postPlanes = [];
                ?>
                
                 <?php if ( $the_query->have_posts() ) : ?>
                    <?php while ( $the_query->have_posts() ) : $the_query->the_post(); ?>
                    <?php 
                        $idPos = get_the_ID(); 
                        $terms = get_the_terms($idPos,'destinos');
                        $postPlanes[] = array(
                            'title' => get_the_title(),
                            'terms'=>$terms,
                            'dias'=> get_field('dias'),
                            'precio'=> get_field('precio'),
                            'imagen'=> get_the_post_thumbnail($idPos,'full'),
                        );
                    ?>
                    <?php endwhile; ?>

                        <div class="imgGrande">
                            <?php if ( $postPlanes[0]['imagen']) : ?>
                                <?php echo $postPlanes[0]['imagen']; ?>
                                
                            <?php endif; ?>

                                
                            <div class="infoDestinos">
                                
                                    <h1 class="info-title-destinos1">
                                    <?php if ($postPlanes[0]['terms'] ) : ?>
                                        <?php foreach ($postPlanes[0]['terms']  as $term) : ?>
                                            <?php echo $term->name; ?>
                                        <?php endforeach; ?>
                                    <?php endif; ?>
                                    </h1>
                                    <h3 class="time-detino1"><?php echo $postPlanes[0]['dias'];  ?> <br> <?php echo $postPlanes[0]['precio']  ?> </h3>
                            </div>
                        </div>
                        <div class="containerGrupo">
                            <?php unset($postPlanes[0]); ?>

                            <?php if (count($postPlanes)>0) : ?>
                            <?php foreach ($postPlanes as $plan) : ?>
                                <div class="imgPequeña">
                                    <?php if ( $plan['imagen']) : ?>
                                
                                        <?php echo $plan['imagen']; ?>

                                    <?php endif; ?>
                                    <div class="infoDestinos">
                                        <h1 class="info-title-destinos1">
                                            <?php if ($plan['terms'] ) : ?>
                                                <?php foreach ($plan['terms']  as $term) : ?>
                                                    <?php echo $term->name; ?>
                                                <?php endforeach; ?>
                                            
                                            <?php endif; ?>
                                            </h1>
                                            <h3 class="time-detino1"><?php echo $plan['dias'];  ?> <br> <?php echo $plan['precio']  ?> </h3>
                                    </div>
                                
                                </div>
                            <?php endforeach; ?>
                            <?php endif; ?>
                        </div>
                        

        
                <?php endif; ?>
            </div>
        </section>


        <?php 

        $args = array(
            'post_type' => 'blog',
            'post_status'=>'publish',
            'posts_per_page'=> 4,
            'order'=> 'DESC'

        );
        // the query
        $the_query = new WP_Query( $args ); ?>
        
        <?php if ( $the_query -> have_posts() ) : ?>
        
            <!-- pagination here -->
            <section class="blog-viajes headerMargenes">
                <h2 class="title-blog"><?php the_field("title_blogs",$idPage); ?></h2>
            <div class="container-cards">
            <!-- the loop -->
            <?php $cont = 1; ?>
            <?php while ( $the_query->have_posts() ) : $the_query->the_post(); ?>
                
                <div class="card<?php echo $cont?> cards">
                    <?php the_post_thumbnail('full', ['class' => 'img-responsive', 'title' => get_the_title()]); ?>
                    <div class="info-card">
                        <h4 class="info-title"><?php the_title() ?></h4>
                        <p class="info-fecha"><?php echo get_the_date() ?></p>
                    </div>  
                </div>
                <?php $cont++ ?>
            <?php endwhile; ?>
            <!-- end of the loop -->
            </div>
            </section>
            <!-- pagination here -->
        
            <?php wp_reset_postdata(); ?>
        
        <?php else : ?>
            <p><?php _e( 'Sorry, no posts matched your criteria.' ); ?></p>
        <?php endif; ?>
        

        <?php 

        $args = array(
            'post_type' => 'testimonios',
            'post_status'=>'publish',
            'posts_per_page'=> 4,
            'order'=> 'DESC'

        );
        // the query
        $the_query = new WP_Query( $args ); ?>
        
        <?php if ( $the_query -> have_posts() ) : ?>    

        <section class="testimonios headerMargenes">
            <h2 class="title-testimonios"><?php the_field('title_testimonios'); ?></h2>
            <div class="slider__tetimony">
              <?php $cont = 1; ?>  
            <?php while ( $the_query->have_posts() ) : $the_query->the_post(); ?>
                <div class="item__testimony card-testimonios<?php echo $cont?>">
                        <div class="content_item__testimony">
                            <div class="image__testimony">
                            <?php the_post_thumbnail('full', ['class' => 'img-responsive', 'title' => get_the_title()]); ?>
                            </div>
                            <div class="description__testimony">
                                <h3><?php the_title() ?></h3> 
                                <p><?php the_content() ?></p>
                            </div>
                        </div>
                    </div>
                    <?php $cont++ ?>
                <?php endwhile; ?>
            </div>
        </section>
        <!-- pagination here -->
        <?php wp_reset_postdata(); ?>
        
        <?php else : ?>
            <p><?php _e( 'Sorry, no posts matched your criteria.' ); ?></p>
        <?php endif; ?>
	</main><!-- #main -->

<?php
get_footer();

#functions
add_action( 'widgets_init', 'rosa_widgets_init' );

if( function_exists('acf_add_options_page') ) {
	
	acf_add_options_page(array(
		'page_title' 	=> 'Opciones generales',
		'menu_title'	=> 'Opciones generales',
		'menu_slug' 	=> 'opciones',
		'capability'	=> 'edit_posts',
		'redirect'		=> false
	));

}
/**
 * Polylang Shortcode - https://wordpress.org/plugins/polylang/
 * Add this code in your functions.php
 * Put shortcode [polylang_langswitcher] to post/page for display flags
 *
 * @return string
 */
function custom_polylang_langswitcher() {
	$output = '';
	if ( function_exists( 'pll_the_languages' ) ) {
		$args   = [
			'show_flags' => 0,
			'show_names' => 1,
			'echo'       => 0,
		];
		$output = '<ul class="polylang_langswitcher">'.pll_the_languages( $args ). '</ul>';
	}

	return $output;
}

add_shortcode( 'polylang_langswitcher', 'custom_polylang_langswitcher' );

/**
 * Enqueue scripts and styles.
 */
function rosa_scripts() {
	wp_enqueue_style( 'rosa-style', get_stylesheet_uri(), array(), _S_VERSION );
	wp_enqueue_style( 'rosa-bootstrap-css', get_template_directory_uri().'/vendor/bootstrap/css/bootstrap.min.css', array(), _S_VERSION );
	wp_enqueue_style( 'rosa-acordion-css', get_template_directory_uri().'/assets/js/acordion/dist/css/accordion-slider.min.css', array(), _S_VERSION );

	wp_enqueue_style( 'rosa-main-slick-css', get_template_directory_uri().'/assets/js/slick/slick.css', array(), _S_VERSION );
	wp_enqueue_style( 'anv-style-slick-theme', get_template_directory_uri().'/assets/js/slick/slick-theme.css' );
	wp_enqueue_style( 'rosa-main-css', get_template_directory_uri().'/assets/css/main.css', array(), _S_VERSION );
	wp_enqueue_style( 'rosa-main-responsive-css', get_template_directory_uri().'/assets/css/main-responsive.css', array(), _S_VERSION );

	
	wp_style_add_data( 'rosa-style', 'rtl', 'replace' );


	wp_enqueue_script( 'rosa-jquery', 'https://ajax.googleapis.com/ajax/libs/jquery/3.6.0/jquery.min.js', array(), _S_VERSION, true );
	wp_enqueue_script( 'rosa-navigation', get_template_directory_uri() . '/js/navigation.js', array(), _S_VERSION, true );
	wp_enqueue_script( 'rosa-bootstrap-js', get_template_directory_uri() . '/vendor/bootstrap/js/bootstrap.min.js', array(), _S_VERSION, true );
	wp_enqueue_script( 'rosa-slick-js', get_template_directory_uri() . '/assets/js/slick/slick.min.js', array(), _S_VERSION, true );
	wp_enqueue_script( 'rosa-acordion-js', get_template_directory_uri() . '/assets/js/acordion/dist/js/jquery.accordionSlider.min.js', array(), _S_VERSION, true );
	wp_enqueue_script( 'rosa-main-js', get_template_directory_uri() . '/assets/js/main.js', array(), _S_VERSION, true );

	if ( is_singular() && comments_open() && get_option( 'thread_comments' ) ) {
		wp_enqueue_script( 'comment-reply' );
	}
}

