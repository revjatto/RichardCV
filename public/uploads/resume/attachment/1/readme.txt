<div id="prayer_content">
	<h1 class="title"><%= @prayer.user_name %></h1>
	<p class="date">
		Submitted <%= time_ago_in_words(@prayer.created_at) %> Ago
		<% if user_signed_in? %>
		| <%= link_to 'Edit', edit_prayer_path(@prayer) %> |
		  <%= link_to 'Delete', prayer_path(@prayer), method: :delete, data: { confirm: 'Are you sure?' } %>
	  <% end %>
	</p>
	<p class="body"><%= @prayer.body %></p>

	<div id="comments">
		<h2><%= @prayer.comments.count %> Comments</h2>
		<%= render @prayer.comments %>

		<h3>Add a comment:</h3>
		<%= render "comments/form" %>
	</div>
</div>


<link rel="stylesheet" href="//railsgirls.com/assets/bootstrap.css">
<link rel="stylesheet" href="//railsgirls.com/assets/bootstrap-theme.css">
