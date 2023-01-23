<template>
  <div>
    <div>
      <ul class="types">
        <li class="selected">支出</li>
        <li>收入</li>
      </ul>
    </div>
    <Layout>
      <div class="tags">
        <ul class="current">
          <li>餐饮</li>
          <li>医疗</li>
          <li>购物</li>
          <li>交通</li>
          <li>住宿</li>
          <li>学习</li>
          <li>娱乐</li>
          <li>美妆</li>
          <li>旅游</li>
          <li>通讯</li>
        </ul>
      </div>
      <div class="new">
        <button>新增标签</button>
      </div>
      <div class="numberPad">
        <div class="output">
          <label class="notes">
            <span>备注</span>
            <input type="text">
          </label>
          <div class="number">100</div>
        </div>
        <div class="buttons">
          <button>1</button>
          <button>2</button>
          <button>3</button>
          <button>删除</button>
          <button>4</button>
          <button>5</button>
          <button>6</button>
          <button>清空</button>
          <button>7</button>
          <button>8</button>
          <button>9</button>
          <button>OK</button>
          <button>0</button>
          <button>.</button>
        </div>
      </div>
    </Layout>
  </div>
</template>

<script lang="ts">
export default {
  name: 'Money.vue',
};
</script>
