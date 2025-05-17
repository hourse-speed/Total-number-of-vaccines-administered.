module MyModule::VaccinationTracker {

    use aptos_framework::signer;

    /// Struct representing a vaccination campaign
    struct Campaign has store, key {
        total_vaccinated: u64, // Total vaccinations recorded
        target: u64,           // Target number of vaccinations
    }

    /// Initialize a new vaccination campaign with a target
    public fun start_campaign(admin: &signer, target: u64) {
        let campaign = Campaign {
            total_vaccinated: 0,
            target,
        };
        move_to(admin, campaign);
    }

    /// Record one vaccination event
    public fun record_vaccination(admin: &signer) acquires Campaign {
        let campaign = borrow_global_mut<Campaign>(signer::address_of(admin));
        campaign.total_vaccinated = campaign.total_vaccinated + 1;
    }
}
