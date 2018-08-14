# thebindery
<?php
/**
 * Template Name: Sunday Dinners Template
 *
 * @package Bindery
 * @since Bindery 1.0
 */
get_header(); ?>	

	<!--==================== intro-sec Section ====================-->
	<section class="page-sec intro-sec" id="pageTop">
		<div class="scene-trigger"></div><!-- .scene-trigger -->
		<?php if (has_post_thumbnail( $post->ID ) ): ?>
			<?php $image = wp_get_attachment_image_src( get_post_thumbnail_id( $post->ID ), 'single-post-thumbnail' ); ?>
			<div class="bg" style="background-image:url(<?php echo $image[0]; ?>);"></div><!-- .bg -->
		<?php else: ?>
			<div class="bg"></div><!-- .bg -->
		<?php endif; ?>
		<div class="container">
			<div class="row">
				<div class="col-sm-10 col-sm-offset-1 col-md-8 col-md-offset-2 text-center">
					<h3 class="text-gold">Special Offerings</h3>
					<?php if( get_field('headline') ) { ?>
						<h1 class="lg text-white"><?php the_field('headline'); ?></h1>
					<?php } else { ?>
						<?php if( get_field('fallback_headline') ) { ?>
							<h1 class="lg text-white"><?php the_field('fallback_headline'); ?></h1>
						<?php } ?>
					<?php } ?>
				</div><!-- .col-sm-12 -->
			</div><!-- .row -->
		</div><!-- .container -->
	</section><!-- .intro-sec -->
	
	<!--==================== start-sec Section ====================-->
	<section class="page-sec start-sec">
		<div class="scene-trigger"></div><!-- .scene-trigger -->
		<div class="container">
			<div class="row">
				<div class="col-md-8 col-md-offset-2 text-center">
					<h1 class="h5">About</h1>
					<div class="hr short"></div>
					<div class="big-breather">
						<div class="h2"><?php the_field('intro_section'); ?></div>
						<div class="p"><?php the_field('second_section'); ?></div>
					</div>
					<!-- .breather -->
					<h5 class="text-gold">reservations by phone only</h5>
					<a class="h2 text-gold" href="tel:303-993-2364">Call 303.993.2364</a>
				</div><!-- .col-sm-12 -->
			</div><!-- .row -->
		</div><!-- .container -->
	</section><!-- .about-sec -->

	
	<!--==================== details-sec Section ====================-->
	<section class="page-sec details-sec">
		<div class="scene-trigger"></div><!-- .scene-trigger -->
		<?php $image = get_field('detail_section_image');?>
		<div class="col-left image" style="background-image:url(<?php echo $image['url']; ?>);">
		</div><!-- .col-left map -->
		<div class="col-right deets">
			<div class="container-fluid">
				<div class="row">
					<div class="col-sm-10 col-sm-offset-1 col-sm-10 col-sm-offset-1"> 
						<h1 class="h5 text-gold">Details</h1>
						<?php the_field('detail_section'); ?>
					</div><!-- .col-sm- -->
				</div><!-- .row -->
			</div><!-- .container-fluid -->
		</div><!-- .col-right-hours -->
	</section><!-- .location-sec -->
	
	




<?php get_footer(); ?>
