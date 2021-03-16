<script>
  export let segment;
</script>

<h1>Settings</h1>

<div class="submenu">
  <a href="settings/profile">Profile</a>
  <a href="settings/notifications">Notifications</a>
  <a class:selected={segment === 'profile'} href="settings/profile">Profile</a>
  <a class:selected={segment === 'notifications'} href="settings/notifications">Notifications</a>
</div>

<slot></slot>
