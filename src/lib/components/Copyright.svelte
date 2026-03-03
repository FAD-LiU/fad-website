<script>
  export let startYear = 2025;

  // Grab the current year from the user's system
  const currentYear = new Date().getFullYear();

  // If a start year is provided and it's older than the current year,
  // format it as a range (e.g., "2023 - 2026"). Otherwise, just use the current year.
  $: yearText =
    startYear && startYear < currentYear ? `${startYear} - ${currentYear}` : currentYear;
</script>

<p {...$$restProps}>
  &copy; {yearText}
  FAD
</p>
