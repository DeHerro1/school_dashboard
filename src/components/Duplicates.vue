<template>
  <div class="duplicates">
    <div class="choice">
      <div class="iconsHome">
        <img src="../assets/copy.png" class="duplicateIcon" />
        <img src="../assets/delete.png" class="duplicateIcon" />
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style>
.duplicates {
  background: white;
}

.iconsHome {
  display: flex;
  flex-direction: column;
}

.duplicateIcon {
  width: 20px;
  padding: 10px 0;
  height: 20px;
}
</style>
