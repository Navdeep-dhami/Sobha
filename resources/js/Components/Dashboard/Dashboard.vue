<script>
export default {
  data() {
    return {
      projects: [
        {
          name: 'The Crest',
          stats: [
            { icon: 'split_scene_left', value: '4', label: 'Divisions', color: '#8b5cf6' },
            { icon: 'list', value: '245', label: 'Activities', color: '#f59e0b' },
            { icon: 'event_note', value: '98', label: 'Apontmets', color: '#f59e0b' }
          ]
        },
        {
          name: 'Crest Grande',
          stats: [
            { icon: 'view_agenda', value: '10', label: 'Sub-divisions', color: '#06b6d4' },
            { icon: 'clear_all', value: '384', label: 'Sub-activities', color: '#ef4444' },
            { icon: 'text_format', value: '420', label: 'Typologies', color: '#10b981' }
          ]
        },
        {
          name: 'Waves Opulence',
          stats: [
            { icon: 'domain', value: '4', label: 'Towers', color: '#3b82f6' },
            { icon: 'home_work', value: '96', label: 'Apartments', color: '#06b6d4' },
            { icon: 'widgets', value: '25', label: '% Configured', color: '#8b5cf6' }
          ]
        }
      ],
      tableData: [
        {
          id: 1,
          tower: 'A',
          unit: '1',
          apartment: 'A101',
          typology: '2 BHK Type B',
          quantity: '95 m²',
          priority: 'High',
          configured: true,
          lastUpdated: '08-Apr-2025'
        },
        {
          id: 2,
          tower: 'A',
          unit: '2',
          apartment: 'A208',
          typology: '3 BHK Type A',
          quantity: '125 m²',
          priority: 'Medium',
          configured: false,
          lastUpdated: ''
        },
        {
          id: 3,
          tower: 'B',
          unit: '1',
          apartment: 'B204',
          typology: '1 BHK Type A',
          quantity: '55 m²',
          priority: 'Low',
          configured: true,
          lastUpdated: '07-Apr-2025'
        }
      ]
    }
  }
}
</script>

<style scoped>
.dashboard {
  padding: 40px;
  flex: 1;
}

.stats-grid {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.stat-item {
  display: flex;
  align-items: flex-start;
  flex-direction: column;
  gap: 16px;
}

.stat-icon {
  width: 48px;
  height: 48px;
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 20px;
  color: white;
}

.stat-content {
  display: flex;
  gap: 16px;
  align-items: center;
}

.stat-number {
  font-size: 32px;
  font-weight: 700;
  color: #333;
  line-height: 1;
}

.stat-label {
  font-size: 14px;
  color: #666;
  margin-top: 4px;
}

.progress-card {
  background: white;
  border-radius: 12px;
  padding: 24px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  display: flex;
  align-items: center;
  justify-content: center;
}

.progress-circle {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
}

.progress-text {
  position: absolute;
  text-align: center;
}

.progress-percentage {
  font-size: 32px;
  font-weight: 700;
  color: #333;
  line-height: 1;
}

.progress-label {
  font-size: 14px;
  color: #666;
  margin-top: 4px;
}

.table-section h3 {
  font-size: 20px;
  font-weight: 600;
  margin-bottom: 20px;
  color: #333;
}

.table-container {
  overflow-x: auto;
    background: #fff;
    border: 1px solid lightgray;
    border-radius: 12px;
}

.data-table {
  width: 100%;
  border-collapse: collapse;
}

.data-table th {
  background-color: #f8f9fa;
  padding: 12px 16px;
  text-align: left;
  font-weight: 600;
  color: #666;
  border-bottom: 1px solid #e5e5e5;
}

.data-table td {
  padding: 12px 16px;
  border-bottom: 1px solid #f0f0f0;
}

.priority-badge {
  padding: 4px 12px;
  border-radius: 16px;
  font-size: 12px;
  font-weight: 500;
}

.priority-badge.high {
  background-color: #fee2e2;
  color: #dc2626;
}

.priority-badge.medium {
  background-color: #fef3c7;
  color: #d97706;
}

.priority-badge.low {
  background-color: #dcfce7;
  color: #16a34a;
}

.status-indicator.configured {
  color: #10b981;
}

.status-indicator.not-configured {
  color: #ef4444;
}

@media (max-width: 1200px) {
}

@media (max-width: 768px) {

  .dashboard {
    padding: 20px;
  }
}
</style>
<template>
  <div class="dashboard">
    <div class="grid grid-cols-1 lg:grid-cols-3 gap-6 mb-6">
        <div class="bg-white rounded-lg border border-gray-200 p-6" v-for="project in projects" :key="project.name">
            <h3 class="text-lg font-semibold text-gray-900 ">{{ project.name }}</h3>
        </div>
    </div>
    <div class="grid grid-cols-1 lg:grid-cols-4 gap-4 mb-6">
        <div class="stats-grid" v-for="project in projects" :key="project.name">
          <div class="stat-item bg-white rounded-lg border border-gray-200 p-6" v-for="stat in project.stats" :key="stat.label">
            <div class="stat-content">
                <div class="stat-icon" :style="{ backgroundColor: stat.color }">
                    <span class="material-symbols-outlined">{{ stat.icon }}</span>
                </div>
              <div class="stat-number">{{ stat.value }}</div>
            </div>
              <div class="stat-label text-lg font-semibold text-gray-900">{{ stat.label }}</div>
          </div>
        </div>

      <div class="progress-card">
        <div class="progress-circle">
          <svg width="120" height="120" viewBox="0 0 120 120">
            <circle cx="60" cy="60" r="50" fill="none" stroke="#e5e5e5" stroke-width="8"/>
            <circle cx="60" cy="60" r="50" fill="none" stroke="#4285f4" stroke-width="8"
                    stroke-dasharray="314" stroke-dashoffset="69" stroke-linecap="round"/>
          </svg>
          <div class="progress-text">
            <div class="progress-percentage">78%</div>
            <div class="progress-label">Configured</div>
          </div>
        </div>
      </div>
    </div>

    <div class="table-section">
      <h3>Table Preview</h3>
      <div class="table-container">
        <table class="data-table">
          <thead>
            <tr>
              <th>Tower</th>
              <th>Unit</th>
              <th>Apartment</th>
              <th>Typology</th>
              <th>Quantity</th>
              <th>Priority</th>
              <th>Configured</th>
              <th>Last Updated</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="row in tableData" :key="row.id">
              <td>{{ row.tower }}</td>
              <td>{{ row.unit }}</td>
              <td>{{ row.apartment }}</td>
              <td>{{ row.typology }}</td>
              <td>{{ row.quantity }}</td>
              <td>
                <span class="priority-badge" :class="row.priority.toLowerCase()">
                  {{ row.priority }}
                </span>
              </td>
              <td>
                <span class="status-indicator" :class="row.configured ? 'configured' : 'not-configured'">
                  {{ row.configured ? '●' : '●' }}
                </span>
              </td>
              <td>{{ row.lastUpdated }}</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>
</template>
