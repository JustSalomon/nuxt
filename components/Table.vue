<template>
  <div class="table-wrapper">
    <div class="table">

      <div class="row">
        <div class="cell header">#</div>
        <div class="cell header">название</div>
        <div class="cell header">артикул</div>
        <div class="cell header underline">примечание</div>
      </div>


      <div v-for="(row, index) in rows" :key="index" class="row" @mouseover="isRowHovered = index">
        <div class="cell" :class="{ 'hovered': isRowHovered === index }">{{ firstColumnValues[index] }}</div>
        <div class="cell" :class="{ 'hovered': isRowHovered === index }">компрессор</div>
        <div class="cell" :class="{ 'hovered': isRowHovered === index }">A 000 180 17 09</div>
        <div class="cell" :class="{ 'hovered': isRowHovered === index }">Ts фильтрующий элемент</div>
      </div>


      <div class="show-more">
        <span class="show-more-text">показать ещё</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      rows: [1, 2, 3, 4, 5, 6, 7],
      firstColumnValues: [80, 23, 15, 6, 38, 6, 38],
      isRowHovered: null
    };
  }
};
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@300&family=Ubuntu&display=swap');

.table-wrapper {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

.table {
  display: table;
  width: 50%;
  font-family: 'Ubuntu', sans-serif;
  border-collapse: separate; 
  border-spacing: 5px 10px; 
}

.row {
  display: table-row;
  cursor: pointer; 
}

.cell {
  display: table-cell;
  position: relative;
  padding: 8px;
  text-align: center;
  color: #555555; 
  transition: color 0.3s; 
  font-weight: bold;
}

.cell.hovered {
  color: #1c58b1; 
}

.cell:not(:last-child)::before {
  content: "";
  position: absolute;
  top: 50%;
  right: -10px;
  transform: translateY(-50%);
  height: 50%;
  width: 2px;
  background-color: #aaaaaa; 
}

.row:hover .cell:not(:last-child)::before {
  background-color: #1c58b1; 
}

.header {
  font-weight: bold;
  background-color: white;
  border-top: none;
  position: relative;
  top: -10px; 
  color: #1c58b1; 
}

.underline::after {
  content: "";
  position: absolute;
  left: -13.3cm;
  bottom: 0px;
  height: 2px;
  width: 20.5cm;
  background-color: #1c58b1; 
}

.show-more {
  display: flex;
  justify-content: center;
  margin-top: 20px;
}

.show-more-text {
  font-weight: bold; 
  color: #1c58b1; 
}
</style>
