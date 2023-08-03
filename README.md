
[![Netlify Status](https://api.netlify.com/api/v1/badges/ebd12782-20e2-4816-816c-5534dbefdbe9/deploy-status)](https://app.netlify.com/sites/webclear/deploys)

https://webclear.netlify.app

# Dialysis Simulator

`calcClearanceTable()` - goalseek function iterates to find a starting Cd value that approaches 0 as x (the position in the dialyzer) approaches 1. The inputs from the website run through a table that uses pseudo-calculus to model a series of values.

`calcWeeklyTable()` - Using the clearance value derived from the calcClearanceTable calculations, the Iterate loop searches for an initial urea concentration that roughly matches the ending concentration by continually bisecting the difference between the initial guess and the resulting final concentration.

```mermaid




graph TD
    subgraph HTML
       A 
    end
    subgraph Javascript
        A[Web Page] -- Solve! --> B("calcClearanceTable()")
        B -- ClearanceValue --> D("calcWeeklyTable()")
        D -- "Iterate(start, end)" -->D
        D --  t,cext --> E(Chart)
        E --> A
        B -- "goalSeek(Cd)" --> B
    end







```

Created with CodeSandbox
