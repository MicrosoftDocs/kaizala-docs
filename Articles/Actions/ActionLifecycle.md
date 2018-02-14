# Action Lifecycle

An Action can have 5 states:

* **Draft** - Action is successfully uploaded. It is visible only to Action Creator and Organization Admin(s) on Kaizala Management Portal. It cannot be added to groups
* **Staged** - Action in Staged state can be tested (before deployment) in groups for which Action Creator is an admin. It is visible only to Action Creator and Organisation Admin(s) on Kaizala Management Portal
* **Active** - After a version of an Action is staged, it can be activated. In Active state, it is available for all members of the Organisation to add it in their groups on Kaizala Management Portal
* **Inactive** - Action in Active state can be made Inactive. In this state, concerned Action package is not available to other members in the organisation to add it to their groups. On Kaizala app, it can still be used by users in the groups in which this Action is already added
* **Removed** - If a version of an Action is either explicitly removed or replaced by other version, it moves to Removed state. On Kaizala apps, these packages will not be available for user to use
