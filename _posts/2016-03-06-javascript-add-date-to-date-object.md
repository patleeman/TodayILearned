---
layout: post
title: Javascript add date to date object
date: 2016-03-06 23:43:23
category: 
---

// Helper function to add dates to a date object.
function addDays(date, days) {
    var result = new Date(date);
    result.setDate(result.getDate() + days);
    return result;
}
