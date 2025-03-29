<script>
    import * as d3 from 'd3';
    import {onMount} from "svelte";

    let data = [];

    // loading data
    onMount(async () => {
        data = await d3.csv("/2015-2019_ACS_Household_Income2.csv", row => ({
            ...row,
            location: row["Location"],
            income: +row["Median Income"].replace("$", "").replace(',', '') // fixing formatting to remove $ or ,
        }));
        console.log(data);
    });
</script>

<h1>
    Testing 1,2,3...
</h1>