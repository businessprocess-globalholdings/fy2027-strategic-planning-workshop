# FY2027 Strategic Planning Workshop

A Streamlit workshop workspace organized around the participant flow in the 2027 deck:

1. Identify a department and enter SWOT factors, which receive sequential S/W/O/T codes.
2. Use the TOWS intersections to create strategic objectives and assign perspectives.
3. Arrange objectives by perspective and add upward or sideways map connections.
4. Complete FY2027 scorecard rows, including actuals, review frequency, and owner.
5. Present the scorecard with cross-department support needed and incoming KPI dependencies.
6. Export a Day 2 Excel workbook with blank initiative, budget, and schedule worksheets.

## Run locally

```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
pip install -r requirements.txt
streamlit run app.py
```

The app creates `workshop.db` in its working directory. Set `WORKSHOP_DB` to change its location. The default department labels can be replaced by setting `WORKSHOP_DEPARTMENTS` to a comma-separated list of five department names.

This prototype uses local SQLite and does not yet connect to Supabase or provide participant sign-in. In the TOWS matrix, a button opens the new-objective form; the adjacent “Link existing” control assigns existing objectives to an intersection. Streamlit does not provide the requested browser right-click action, so the same action is available through that control. Strategy-map arrows are added and removed through explicit controls.

Objectives are used as the scorecard KPI labels in this first pass because the participant flow does not specify a separate KPI-name field. Day 2 initiatives, budgets, and implementation schedules remain Excel worksheets rather than app workflows.
