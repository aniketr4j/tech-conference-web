<script>
  import Navbar from "../../components/Navbar.svelte";
  import Footer from "../../components/Footer.svelte";
  import { schedule } from "../../lib/data.js";

  let days = [...new Set(schedule.map(session => session.day))];
  let tracks = ["All", ...new Set(schedule.map(session => session.track))];

  let selectedDay = days.length > 0 ? days[0] : null;
  let selectedTrack = "All";

  $: filteredSessions = schedule.filter(session =>
      (!selectedDay || session.day === selectedDay) &&
      (selectedTrack === "All" || session.track === selectedTrack)
  );

  function resetFilters() {
      selectedDay = days.length > 0 ? days[0] : null;
      selectedTrack = "All";
  }
</script>

<Navbar />

<div class="container my-5">
  <h2 class="text-center mb-4">Conference Schedule</h2>

  <!-- Day Filter -->
  <div class="filter-container">
      <strong>Filter by Day:</strong>
      <div class="btn-group">
          {#each days as day}
              <button 
                  class="btn filter-btn {selectedDay === day ? 'active' : ''}"
                  on:click={() => selectedDay = day}
              >
                  {day}
              </button>
          {/each}
      </div>
  </div>

  <!-- Track Filter -->
  <div class="filter-container">
      <strong>Filter by Track:</strong>
      <div class="btn-group">
          {#each tracks as track}
              <button 
                  class="btn filter-btn {selectedTrack === track ? 'active' : ''}"
                  on:click={() => selectedTrack = track}
              >
                  {track}
              </button>
          {/each}
      </div>
  </div>

  <!-- Reset Button -->
  <div class="text-center mb-4">
      <button class="btn btn-danger reset-btn" on:click={resetFilters}>Reset Filters</button>
  </div>

  <!-- Schedule Table -->
  {#if filteredSessions.length > 0}
      <div class="table-responsive">
          <table class="table table-hover shadow-sm">
              <thead class="thead-dark">
                  <tr>
                      <th>Time</th>
                      <th>Session</th>
                      <th>Speaker</th>
                      <th>Track</th>
                  </tr>
              </thead>
              <tbody>
                  {#each filteredSessions as session}
                      <tr>
                          <td>{session.time}</td>
                          <td>{session.topic}</td>
                          <td>{session.speaker}</td>
                          <td>{session.track}</td>
                      </tr>
                  {/each}
              </tbody>
          </table>
      </div>
  {:else}
      <p class="text-center mt-3 text-danger">No sessions available for the selected filters.</p>
  {/if}
</div>
<Footer/>
<style>
/* Responsive Filter Section */
.filter-container {
    text-align: center;
    margin-bottom: 15px;
}

.btn-group {
    display: inline-flex; /* Ensures buttons take only necessary space */
    flex-wrap: wrap;
    justify-content: center;
    gap: 5px; /* Reduces space between buttons */
}

/* Uniform Filter Buttons */
.filter-btn {
    background-color: #f8f9fa;
    color: #333;
    border: 1px solid #ccc;
    padding: 10px 15px; /* Uniform Padding */
    border-radius: 5px;
    cursor: pointer;
    transition: all 0.2s ease-in-out;
    font-size: 16px; /* Consistent Font */
    min-width: 100px; /* Ensures all buttons are same width */
    text-align: center;
}

.filter-btn:hover {
    background-color: #e2e6ea;
}

.filter-btn.active {
    background-color: #007bff !important;
    color: white;
    font-weight: bold;
    border-color: #007bff;
}

/* Reset Button */
.reset-btn {
    padding: 10px 15px;
    font-weight: bold;
}

/* Responsive Table */
.table-responsive {
    overflow-x: auto;
}

table {
    border-radius: 10px;
    overflow: hidden;
    min-width: 600px;
    width: 100%;
}

/* Table Header */
th {
    background-color: #343a40;
    color: white;
    text-align: center;
    white-space: nowrap;
}

/* Table Data */
td {
    text-align: center;
    white-space: nowrap;
}

/* Row Hover Effect */
tbody tr:hover {
    background-color: #f1f1f1;
}

/* Mobile Adjustments */
@media (max-width: 576px) {
    .filter-btn {
        padding: 6px 10px;
        font-size: 14px;
    }

    .reset-btn {
        font-size: 14px;
    }

    table {
        min-width: 100%;
    }
}
</style>
