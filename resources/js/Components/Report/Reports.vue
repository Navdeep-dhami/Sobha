
<script>
import { Chart, registerables } from 'chart.js'

Chart.register(...registerables)

export default {
  name: 'ConfigurationReports',
  data() {
    return {
      tableData: [
        {
          id: 1,
          date: '08.04.2025',
          project: 'The Crest',
          activity: 'External Painting - Primer',
          typology: '1 BHK Type A',
          action: 'Added',
          quantity: '50',
          priority: '70',
          user: 'Mohan K.'
        },
        {
          id: 2,
          date: '08.04.2025',
          project: 'The Crest',
          activity: 'Shadow Angle Fixing - Dry',
          typology: '2 BHK Type A',
          action: 'Modified',
          quantity: '60 >',
          priority: '70',
          user: 'Rajesh N.'
        },
        {
          id: 3,
          date: '08.04.2025',
          project: 'Waves Opulence',
          activity: 'Final Coat Paint',
          typology: '3 BHK Type A',
          action: 'Added',
          quantity: '120',
          priority: '30',
          user: 'Anju R.'
        },
        {
          id: 4,
          date: '08.04.2025',
          project: 'Crest Grande',
          activity: 'Gypsum Ceiling Framing -We',
          typology: '2 BHK Type A',
          action: 'Removed',
          quantity: '—',
          priority: '—',
          user: 'Akshat P.'
        },
        {
          id: 5,
          date: '08.04.2025',
          project: 'Crest Grande',
          activity: 'Floor Tiling',
          typology: '1 BHK Type B',
          action: 'Added',
          quantity: '140',
          priority: '140',
          user: 'Akshat P.'
        }
      ]
    }
  },
  mounted() {
    this.initCharts()
  },
  methods: {
    getActionClass(action) {
      switch (action) {
        case 'Added':
          return 'bg-green-100 text-green-800'
        case 'Modified':
          return 'bg-yellow-100 text-yellow-800'
        case 'Removed':
          return 'bg-red-100 text-red-800'
        default:
          return 'bg-gray-100 text-gray-800'
      }
    },
    initCharts() {
      // Pie Chart
      const pieCtx = this.$refs.pieChart.getContext('2d')
      new Chart(pieCtx, {
        type: 'doughnut',
        data: {
          labels: ['Config', 'Modified', 'Pending'],
          datasets: [{
            data: [30, 60, 10],
            backgroundColor: ['#3B82F6', '#F59E0B', '#10B981'],
            borderWidth: 0
          }]
        },
        options: {
          responsive: false,
          maintainAspectRatio: false,
          plugins: {
            legend: {
              display: false
            }
          },
          cutout: '60%'
        }
      })

      // Bar Chart 1
      const barCtx1 = this.$refs.barChart1.getContext('2d')
      new Chart(barCtx1, {
        type: 'bar',
        data: {
          labels: ['The Crest', 'Crest Grande', 'Waves Opulence'],
          datasets: [{
            data: [250, 200, 100],
            backgroundColor: '#3B82F6',
            borderRadius: 4
          }]
        },
        options: {
          responsive: true,
          maintainAspectRatio: false,
          plugins: {
            legend: {
              display: false
            }
          },
          scales: {
            y: {
              beginAtZero: true,
              max: 300,
              ticks: {
                stepSize: 100
              }
            },
            x: {
              grid: {
                display: false
              }
            }
          }
        }
      })

      // Bar Chart 2
      const barCtx2 = this.$refs.barChart2.getContext('2d')
      new Chart(barCtx2, {
        type: 'bar',
        data: {
          labels: ['Gypsum Ceiling', 'Final Coat Paint', 'External painting', 'Floor Tiling', 'Floor Tiling'],
          datasets: [{
            data: [350, 250, 230, 190, 170],
            backgroundColor: '#3B82F6',
            borderRadius: 4
          }]
        },
        options: {
          responsive: true,
          maintainAspectRatio: false,
          plugins: {
            legend: {
              display: false
            }
          },
          scales: {
            y: {
              beginAtZero: true,
              max: 400,
              ticks: {
                stepSize: 100
              }
            },
            x: {
              grid: {
                display: false
              }
            }
          }
        }
      })
    }
  }
}
</script>
<template>
  <div class="space-y-6">
    <!-- Filters -->
    <div class=" rounded-lg p-6">
      <div class="grid grid-cols-1 md:grid-cols-5 gap-4 items-end">
        <div>
          <label class="block text-sm font-medium text-gray-700 mb-2">Project</label>
          <select class="w-full border border-gray-300 rounded-lg px-3 py-2 text-sm focus:outline-none focus:ring-2 focus:ring-blue-500">
            <option>The Crest</option>
          </select>
        </div>

        <div>
          <label class="block text-sm font-medium text-gray-700 mb-2">Date Range</label>
          <input type="text" value="1/1/2025" class="w-full border border-gray-300 rounded-lg px-3 py-2 text-sm focus:outline-none focus:ring-2 focus:ring-blue-500">
        </div>

        <div>
          <label class="block text-sm font-medium text-gray-700 mb-2">Division, Sub-Division</label>
          <select class="w-full border border-gray-300 rounded-lg px-3 py-2 text-sm focus:outline-none focus:ring-2 focus:ring-blue-500">
            <option>Any -</option>
          </select>
        </div>

        <div>
          <label class="block text-sm font-medium text-gray-700 mb-2">Activity / Sub-Activity</label>
          <select class="w-full border border-gray-300 rounded-lg px-3 py-2 text-sm focus:outline-none focus:ring-2 focus:ring-blue-500">
            <option>Any -</option>
          </select>
        </div>

        <div>
          <label class="block text-sm font-medium text-gray-700 mb-2">Typology</label>
          <div class="flex space-x-2">
            <select class="flex-1 border border-gray-300 rounded-lg px-3 py-2 text-sm focus:outline-none focus:ring-2 focus:ring-blue-500">
              <option>All</option>
            </select>
            <button class="bg-blue-900 text-white px-6 py-2 rounded-lg text-sm font-medium hover:bg-blue-800">
              Download PDF
            </button>
          </div>
        </div>
      </div>
    </div>

    <!-- Charts Section -->
    <div class="grid grid-cols-1 lg:grid-cols-3 gap-6">
      <!-- Pie Chart -->
      <div class="bg-white rounded-lg border border-gray-200 p-6">
        <h3 class="text-lg font-semibold text-gray-900 mb-4">% Typologies Configured</h3>
        <div class="relative w-48 h-48 mx-auto">
          <canvas ref="pieChart" width="192" height="192"></canvas>
        </div>
        <div class="flex justify-center space-x-6 mt-4">
          <div class="flex items-center space-x-2">
            <div class="w-3 h-3 bg-blue-500 rounded-full"></div>
            <span class="text-sm text-gray-600">Config</span>
          </div>
          <div class="flex items-center space-x-2">
            <div class="w-3 h-3 bg-yellow-400 rounded-full"></div>
            <span class="text-sm text-gray-600">Modified</span>
          </div>
          <div class="flex items-center space-x-2">
            <div class="w-3 h-3 bg-green-500 rounded-full"></div>
            <span class="text-sm text-gray-600">Pending</span>
          </div>
        </div>
      </div>

      <!-- Bar Chart 1 -->
      <div class="bg-white rounded-lg border border-gray-200 p-6">
        <h3 class="text-lg font-semibold text-gray-900 mb-4">Configured Typologies per Project</h3>
        <div class="h-48">
          <canvas ref="barChart1"></canvas>
        </div>
      </div>

      <!-- Bar Chart 2 -->
      <div class="bg-white rounded-lg border border-gray-200 p-6">
        <h3 class="text-lg font-semibold text-gray-900 mb-4">Quantity Configured per Activity</h3>
        <div class="h-48">
          <canvas ref="barChart2"></canvas>
        </div>
      </div>
    </div>

    <!-- Data Table -->
    <div class="bg-white rounded-lg border border-gray-200 overflow-hidden">
      <div class="overflow-x-auto">
        <table class="w-full">
          <thead class="bg-gray-50">
            <tr>
              <th class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Date</th>
              <th class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Project</th>
              <th class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Activity</th>
              <th class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Typology</th>
              <th class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Action</th>
              <th class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Quantity</th>
              <th class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Priority</th>
              <th class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">User</th>
            </tr>
          </thead>
          <tbody class="bg-white divide-y divide-gray-200">
            <tr v-for="row in tableData" :key="row.id" class="hover:bg-gray-50">
              <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-900">{{ row.date }}</td>
              <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-900">{{ row.project }}</td>
              <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-900">{{ row.activity }}</td>
              <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-900">{{ row.typology }}</td>
              <td class="px-6 py-4 whitespace-nowrap">
                <span :class="getActionClass(row.action)" class="px-2 py-1 text-xs font-medium rounded-full">
                  {{ row.action }}
                </span>
              </td>
              <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-900">{{ row.quantity }}</td>
              <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-900">{{ row.priority }}</td>
              <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-900">{{ row.user }}</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>
</template>
