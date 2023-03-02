<!-- This file is called Learn instead of More (As the route) because calling this file More.Svelte fucked with something for some reason -->
<div class="container"> 
    <div class="section-0">
        <h2>What is Communis?</h2>
        <p>
            Communis is an ERC20 token on the Ethereum network that is distributed to Hex Stakers as an incentive to behave better as a staker. Anyone who has shares from an active stake can mint their own Communis.
        </p>
    </div>
    
    <div class="section-0">
        <h2>Why is Communis important?</h2>
        <p>
            Not only is Communis minted based on the shares of your stakes but it is also done exclusively to long term stakers and to those who actually fulfill their staking commitment. 
        </p>
    </div>

    <div class="section-0">
        <h2>How is Communis distributed?</h2>
        <p>
            Communis is introduced through five methods: 
            Start Bonus
            End Bonus
            Good Accounting Bonus
            Restake Bonus
            Staking Communis Bonus
            Any currently active stake may qualify to mint these bonuses
            (explained further below.)
        </p>
    </div>
</div>

<div class="section-1">

    <h1>There are 5 ways to qualify for minting via the following methods:</h1>

    <br>

    <h3 class="h3-title">Mint Start Bonus</h3>
    <h3 class="h3-title">Mint End Bonus</h3>
    <h3 class="h3-title">Mint Good Accounting Bonus</h3>
    <h3 class="h3-title">Mint Restake Bonus</h3>
    <h3 class="h3-title">Mint Staking Communis Bonus</h3>
    
</div>

<style>
.container {
    background-color: var(--blue);
    padding: 2rem;
    margin-bottom: 2rem;
    margin-top: 2rem;
    display: flex;
    align-items: center;
    justify-content: center;
}

.section-0 {
    margin-right: 5rem;
    min-height: -15vw;
    max-height: -15vw;
    padding: 1rem;
}

.section-1 {
    margin-bottom: 2rem;
    margin-top: 2rem;
    background-color: var(--blue);
    padding: 2rem;
}

p {
    text-align: center;
    font-size: 1.2rem;
    resize: none;
}

h1 {
    text-align: center;
    line-height: 1;
}

h2 {
    text-align: center;
    line-height: 1;
}

.h3-title {
    text-align: center;
    background-color: var(--blue);
}

@media only screen and (max-width: 1000px) {
    .container {
        display: grid;
    }

}
</style>