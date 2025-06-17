<template>
  <header class="header">
    <h1>Welcome to Project Control</h1>
    <div class="header-right">
      <div class="search-box">
        <span class="search-icon">
            <span class="material-symbols-outlined">search</span>
        </span>
        <input type="text" placeholder="The Crest" />
      </div>
      <div class="user-profile">
        <span class="profile-icon">
            <span class="material-symbols-outlined">person</span>
        </span>
      </div>
    </div>
  </header>
</template>

<style scoped>
.header {
  padding: 20px 40px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.header h1 {
  font-size: 32px;
  font-weight: 600;
  color: #333;
}

.header-right {
  display: flex;
  align-items: center;
  gap: 20px;
}

.search-box {
  display: flex;
  align-items: center;
  background-color: #fff;
  border-radius: 50px;
  padding: 8px 16px;
  min-width: 200px;
}

.search-icon {
  margin-right: 8px;
  color: #666;
}

.search-box input {
  border: none;
  background: none;
  outline: none;
  font-size: 14px;
  flex: 1;
}

.user-profile {
  width: 40px;
  height: 40px;
  background-color: #6c757d;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
}

.profile-icon {
  color: white;
  font-size: 18px;
}
</style>
