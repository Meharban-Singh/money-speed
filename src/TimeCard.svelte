<script>
    // Export these variables so they can be accessed from outside world
    export let name;
    export let age;
    export let sources;
    export let yearToDate;

    // Convert YTD to dollars earned in 10 milliseconds
    let dollarsPerTenMilliseconds = parseInt(Math.round((yearToDate) / (4 * 30 * 24 * 60 * 60 * 100)));
    
    let dollarAmount = 0;
    let displayAmount;

    // Every 10 milliseconds, update the dollar amount
    setInterval(() => {
        dollarAmount += dollarsPerTenMilliseconds;
        displayAmount = dollarAmount.toLocaleString('en-US', { style: 'currency', currency: 'USD' });
    }, 10);
</script>
 
<div class="timecard">
    <span class="timecard__name">{name} ({age} years)</span>
    <span class="timecard__sources">{sources}</span>
    <span class="timecard__money">{displayAmount}</span>
</div>

<style>
    .timecard {
        display: flex;
        flex-direction: column;
        align-items: center;

        width: 600px;

        padding: 30px 0;
        font-size: larger;
        background-image: linear-gradient( 94.3deg,  rgba(26,33,64,1) 10.9%, rgba(81,84,115,1) 87.1% );
    }

    .timecard__name {
        font-size: 2em;
        padding: 8px;
        font-weight: 900;
        background: linear-gradient(45deg, #f3ec78, #af4261);
        background-clip: text;
        -webkit-background-clip: text;
        -moz-background-clip: text;
        -moz-text-fill-color: transparent;
        -webkit-text-fill-color: transparent;
    }
    
    .timecard__sources {
        font-size: 1.8em;
        background-image: linear-gradient( 109.6deg,  rgba(238,58,136,1) 11.2%, rgba(128,162,245,1) 91.1% );
        background-clip: text;
        -webkit-background-clip: text;
        -moz-background-clip: text;
        -moz-text-fill-color: transparent;
        -webkit-text-fill-color: transparent;
    }

    .timecard__money {
        font-weight: 450;
        font-size: 2.5em;
        color: #C1B4AE;
        margin-top: 1em;
        letter-spacing: 8px;
    }

    @media screen and (max-width: 650px) {
        .timecard {
            width: auto;
            padding: 10px;
        }

        .timecard__name {
            font-size: 1.2em;
            padding: 8px;
            font-weight: 900;
        }

        .timecard__sources {
            font-size: 1em;
        }

        .timecard__money {
            font-weight: 450;
            font-size: 1.8em;
            margin-top: 1em;
            letter-spacing: 8px;
        }
    }
</style>