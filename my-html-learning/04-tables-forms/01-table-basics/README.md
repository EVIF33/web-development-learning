# HTML Tables

## Main rule

**Use tables only for tabular data, never for layout.** Tables are for data that has logical rows and columns. Use CSS Grid/Flexbox for page layout.

## A bit of theory

### What are HTML tables?

- `<table>` creates a data table with rows and cells.
- **Structure:** Table → Rows → Cells (data or headers).
- **Semantic purpose:** Represent relational data (schedules, prices, stats).
- **Accessibility:** Screen readers navigate tables intelligently.

### Core elements:

- `<table>` - wrapper for entire table.
- `<tr>` - table row (horizontal group of cells).
- `<td>` - table data (regular cell).
- `<th>` - table header (title cell, bold by default).
- `<caption>` - table title/description.

### Advanced grouping:

- `<thead>` - header section (contains column headers).
- `<tbody>` - body section (main data).
- `<tfoot>` - footer section (totals, summaries).
- `<colgroup>`/`<col>` - style columns collectively.

## Rules for work

### Basic table structure

```html
<!-- Minimal semantic table -->
<table>
  <caption>Monthly Savings</caption>
  <tr>
    <th>Month</th>
    <th>Amount</th>
  </tr>
  <tr>
    <td>January</td>
    <td>$100</td>
  </tr>
</table>
```

### Spanning cells (rowspan/colspan)

```html
<!-- Merge cells when data belongs together -->
<table>
  <tr>
    <th colspan="2">Financial Report 2024</th>
  </tr>
  <tr>
    <td rowspan="2">Q1-Q2</td>
    <td>$10,000</td>
  </tr>
  <tr>
    <!-- First cell of this row is spanned from above -->
    <td>$12,000</td>
  </tr>
</table>
```

### Accessibility requirements

- Always use `<th>` for headers.
- Always add `scope="col"` or `scope="row"`.
- Consider `<caption>` for table description.
- Use `<thead>`, `<tbody>`, `<tfoot>` for complex tables.
- Test with screen reader (NVDA, VoiceOver).

## What to remember 

```html
<!-- Complete semantic table example -->
<table>
  <caption>Team Schedule for March 2024</caption>
  
  <colgroup>
    <col style="background-color: #f9f9f9;">
    <col span="2" style="background-color: #e9e9e9;">
  </colgroup>
  
  <thead>
    <tr>
      <th scope="col">Date</th>
      <th scope="col">Event</th>
      <th scope="col">Responsible</th>
    </tr>
  </thead>
  
  <tbody>
    <tr>
      <th scope="row">March 5</th>
      <td>Project Kickoff</td>
      <td>Alex</td>
    </tr>
    <tr>
      <th scope="row">March 12</th>
      <td>Design Review</td>
      <td>Maria</td>
    </tr>
  </tbody>
  
  <tfoot>
    <tr>
      <td colspan="2">Total Meetings</td>
      <td>2</td>
    </tr>
  </tfoot>
</table>
```
