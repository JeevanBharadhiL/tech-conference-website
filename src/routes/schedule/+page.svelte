<script lang="ts">
  import { Container, Table } from 'sveltestrap';
  import { schedule } from '$lib/data/schedule';
</script>

<Container>
  <div class="schedule-container">
    <h1 class="page-title">Conference Schedule</h1>
    <div class="schedule-card">
      <div class="table-responsive">
        <Table class="schedule-table table table-hover">
          <thead>
            <tr>
              <th>Date</th>
              <th>Time</th>
              <th>Topic</th>
              <th>Speaker</th>
            </tr>
          </thead>
          <tbody>
            {#each schedule as event}
              <tr>
                <td><div class="cell-content">{event.date}</div></td>
                <td><div class="cell-content">{event.time}</div></td>
                <td><div class="cell-content">{event.topic}</div></td>
                <td><div class="cell-content">{event.speaker}</div></td>
              </tr>
            {/each}
          </tbody>
        </Table>
      </div>
    </div>
  </div>
</Container>

<style>
  /* Main Container */
  .schedule-container {
    max-width: 1200px;
    margin: 2rem auto;
    padding: 2rem;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  /* Title */
  .page-title {
    font-size: 2.5rem;
    font-weight: bold;
    text-align: center;
    margin-bottom: 1.5rem;
    color: var(--text-primary);
  }

  /* Schedule Card */
  .schedule-card {
    width: 100%;
    max-width: 1000px;
    background: white;
    border-radius: 16px;
    box-shadow: 0px 6px 20px rgba(0, 0, 0, 0.1);
    padding: 2rem;
    overflow: hidden;
  }

  /* Table */
  .schedule-table {
    width: 100%;
    border-collapse: collapse;
  }

  /* Header Styling */
  .schedule-table thead {
    background: #2c3e50;
    color: white;
    font-size: 1.1rem;
    text-align: center;
  }

  .schedule-table th {
    padding: 1rem;
    font-weight: bold;
    border-radius: 8px 8px 0 0;
  }

  /* Table Cells */
  .schedule-table td {
    padding: 1rem;
    text-align: center;
  }

  /* Cell Content */
  .cell-content {
    background: #f8f9fa;
    padding: 12px;
    border-radius: 8px;
    font-size: 1rem;
    font-weight: 500;
    color: #333;
    text-align: center;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
    transition: all 0.3s ease-in-out;
  }

  .cell-content:hover {
    background: #ecf0f1;
    transform: translateY(-2px);
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.15);
  }

  /* Responsive */
  @media (max-width: 768px) {
    .schedule-container {
      padding: 1rem;
    }

    .page-title {
      font-size: 2rem;
    }

    .schedule-card {
      padding: 1rem;
    }

    .schedule-table th, .schedule-table td {
      padding: 0.8rem;
      font-size: 0.9rem;
    }

    .cell-content {
      font-size: 0.85rem;
      padding: 10px;
    }
  }
</style>
