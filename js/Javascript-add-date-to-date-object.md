#title: Javascript add date to date object

// Helper function to add dates to a date object.
function addDays(date, days) {
    var result = new Date(date);
    result.setDate(result.getDate() + days);
    return result;
}
