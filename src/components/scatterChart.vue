<script>
import { Scatter } from 'vue-chartjs'

export default {
  extends: Scatter,
  name: 'ScatterChart',
  components: {
    Scatter
  },
  props: ['coordsData'],
  data() {
    return {
      chartData: {
        datasets: [
          {
            label: '磁石',
            fill: false,
            borderColor: '#f87979',
            backgroundColor: '#f87979',
            data: []
          },
          {
            label: '穴',
            fill: false,
            borderColor: '#7acbf9',
            backgroundColor: '#7acbf9',
            data: []
          },
        ]
      },
      chartOptions: {
        responsive: true,
        maintainAspectRatio: false,
        scales: {
          xAxes: [{
            ticks: {
              max: 12,
              min: 0
            }
          }],
          yAxes: [{
            ticks: {
              max: 12,
              min: 0
            }
          }]
        }
      }
    }
  },
  methods: {
    showGraph() {
      this.chartData.datasets[0].data = this.coordsData['magnet']
      this.chartData.datasets[1].data = this.coordsData['holl']
      this.renderChart(this.chartData, this.chartOptions)
    }
  },
  mounted () {
    this.showGraph()
  },
  watch: {
    coordsData: function() {
      this.showGraph()
    }
  }
}
</script>
