var month = date.getMonth() + 1; // getMonth() returns 0-based index (0 for January)
    
    // Determine fiscal year
    var fiscalYear = year;
    if (month < 4) { // Fiscal year starts from January
        fiscalYear = year - 1;
    }
    
    // Determine fiscal quarter
    var quarter;
    if (month >= 1 && month <= 3) {
        quarter = 4; // Q4 of previous fiscal year
    } else if (month >= 4 && month <= 6) {
        quarter = 1; // Q1
    } else if (month >= 7 && month <= 9) {
        quarter = 2; // Q2
    } else if (month >= 10 && month <= 12) {
        quarter = 3; // Q3
    }
    
    return {
        fiscalYear: fiscalYear,
        quarter: quarter
    };
}
