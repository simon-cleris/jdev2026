<template>
  <div class="table-wrap card-navy">
    <div class="table-label">Consommation mondiale — IEA (optimiste) </div>
    <table>
      <thead>
        <tr>
          <th>Catégorie</th>
          <th>2024</th>
          <th>2030</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>Electricité mondiale</td>
          <td>~28 000 TWh</td>
          <td>~33 000 TWh</td>
        </tr>
        <tr>
          <td>Numérique total</td>
          <td>1,5–2 %</td>
          <td>3–4 %</td>
        </tr>
        <tr>
          <td>Data centers seuls</td>
          <td>~1,5 %</td>
          <td>~3 %</td>
        </tr>
        <tr>
          <td>IA dans data centers</td>
          <td>5–15 %</td>
          <td>35–50 %</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<style scoped>
.table-wrap {
  padding: 0.75rem 1rem;
}

.table-label {
  font-size: 0.65rem;
  font-family: monospace;
  text-transform: uppercase;
  letter-spacing: 0.08em;
  color: var(--orange-light);
  margin-bottom: 0.5rem;
}

table {
  width: 100%;
  border-collapse: collapse;
  font-size: 0.75rem;
  color: var(--text-muted);
}

thead tr {
  border-bottom: 1px solid var(--navy-border);
}

th {
  text-align: left;
  font-weight: 600;
  color: var(--text-strong);
  padding: 0.25rem 0.5rem 0.4rem 0;
  font-size: 0.7rem;
}

td {
  padding: 0.3rem 0.5rem 0.3rem 0;
  border-bottom: 1px solid rgba(255,255,255,0.06);
}

tr:last-child td {
  border-bottom: none;
}
</style>
