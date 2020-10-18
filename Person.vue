<template>
  <div>
    <table>
      <tr>
        <td>ID</td>
        <td>NAME</td>
        <td>AGE</td>
      </tr>
      <tr v-for=' item in persons' v-bind:key='item'>
        <td>{{item.pid}}</td>
        <td>{{item.name}}</td>
        <td>{{item.age}}</td>
      </tr>
    </table>
    <div>
      Person Person Person
    </div>
    <div>

      <el-pagination
        background
        layout="prev, pager, next"
        page-size="4"
        :total=total
        @current-change="pageno">
      </el-pagination>

    </div>

  </div>

</template>

<script>
  export default {
    name: 'Person',
    methods:{
      pageno(currentPage) {
        const _this = this
        axios.get('http://localhost:8181/person/findAllPage/'+ currentPage +'/4').then(function (resp) {
          console.log(resp)
          _this.persons = resp.data.content
          _this.total = resp.data.totalElements

        })
      }
    },
    data() {
      return {
        size:4,
        total: 100,
        persons: [{
          pid: 1,
          name: 'jack',
          age: 22
        }
        ]
      }
    },
    created() {
      const _this = this
      // eslint-disable-next-line no-undef
      axios.get('http://localhost:8181/person/findAllPage/1/4').then(function (resp) {
        console.log(resp)
        _this.persons = resp.data.content
        _this.total = resp.data.totalElements
      })

    }

  }
</script>

<style scoped>

</style>
