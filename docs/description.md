## Detailed overview 
The AI integration uses several technologies:
1. **OpenAI/OpenRouter Language Models (LLMs)**
   1. **Pricing Information**
2. **Whisper Speech-to-Text (STT)**
3. **Text-to-Speech (TTS)**
4. **Vision Capabilities**
5. **Function Calling**
6. **Web Lookups for Detailed Information (EDSM)**
7. **Event-Driven Interaction**


### 1. OpenAI/OpenRouter/Local Language Models (LLMs)

LLMs hosted by e.g. OpenAI or OpenRouter process natural language commands, providing intelligent responses and actions, enabling the autopilot to understand complex instructions.

The program is designed to be used with its default model and OpenAI services. It's possible to use different OpenAI models or to connect to any OpenAI-compatible API which includes local setups.
You can change the LLM's name, endpoint and if required API key in the "AI Geeks Section" of the settings.

#### 1.1. Pricing Information

* **OpenAI**: Generally, access to OpenAI models requires a payment. For more information on pricing, please visit: https://openai.com/api/pricing/
* **OpenRouter**: OpenRouter offers a variety of models, some of which are **free** to use. Detailed pricing information for each model can be found here: https://openrouter.ai/docs/models
* **Local**: **Free** to use, although there are associated costs for hardware and electricity. Note that running larger models might require significant hardware resources, such as multi-GPU setups or dedicated machines.

### 2. Whisper Speech-to-Text (STT)

The STT functionality converts spoken language into text, allowing commanders to issue voice commands to the autopilot or engage in a conversation with high accuracy.

There also is a configurable push-to-talk button.

We use a small voice segmentation model to recognize chunks of audio that are then sent to either OpenAI API or a local model. You can change the STT model's name, endpoint and if required API key in the "AI Geeks Section" of the settings.
On default, the program will use OpenAI's services to transcribe your spoken words, or a local quantized, english whisper-medium if the local option was chosen.

### 3. Text-to-Speech (TTS)

The TTS functionality delivers auditory feedback based on the actions and responses from the LLM.

You can change the STT model's name, endpoint and if required API key in the "AI Geeks Section" of the settings.
On default, the program will use OpenAI's services to generate the AI's voice, or from the operating system if the local option was chosen.

### 4. Vision Capabilities

The AI can take screenshots and analyze their content to provide visual confirmations and insights based on the commander's queries. **This feature relies on enabled Function Calling.**

You can change the Vision model's name, endpoint and if required API key in the "AI Geeks Section" of the settings.  

### 5. Function Calling

The AI can call specific functions (e.g., firing weapons, adjusting speed, deploying heat sinks) using OpenAI models, enabling direct control over various ship operations.

The same technique is used to take screenshots or fetch internet data if the AI deems it relevant for the conversation, by either your inquiry or game events happening.

**This should be turned off when using non-OpenAI LLMs.** Not only are smaller models usually not able to use this feature, it also slows down their response time by a lot.

**If this feature is turned off the AI will no longer try to: emulate button presses, use internet tools, take screenshots**. It will still be able to chat normally and react to game events, so deactivating it might also be a valid option for commanders that prefer to have an AI that only talks.

These functions are currently callable:

- fire: Start firing primary weapons.
- holdFire: Stop firing primary weapons.
- fireSecondary: Start firing secondary weapons.
- holdFireSecondary: Stop firing secondary weapons.
- hyperSuperCombination: Initiate FSD Jump, required to jump to the next system or enter supercruise.
- setSpeedZero: Set speed to 0%.
- setSpeed50: Set speed to 50%.
- setSpeed100: Set speed to 100%.
- deployHeatSink: Deploy heat sink.
- deployHardpointToggle: Deploy or retract hardpoints.
- increaseEnginesPower: Increase engine power.
- increaseWeaponsPower: Increase weapon power.
- increaseSystemsPower: Increase systems power.
- galaxyMapOpen: Open or close the galaxy map.
- systemMapOpen: Open or close the system map.
- cycleNextTarget: Cycle to the next target.
- cycleFireGroupNext: Cycle to the next fire group.
- shipSpotLightToggle: Toggle ship spotlight.
- ejectAllCargo: Eject all cargo.
- landingGearToggle: Toggle landing gear.
- useShieldCell: Use a shield cell.
- fireChaffLauncher: Fire chaff launcher.
- nightVisionToggle: Toggle night vision.
- recallDismissShip: Recall or dismiss ship, available on foot and inside SRV.

![Function Calling](screen/function_calling.png?raw=true "Screen")

### 6. Web Lookups for Detailed Information (EDSM & Galnet)

The system performs web lookups using EDSM's API to fetch detailed information about the current and next star systems, enhancing situational awareness.
The AI is able to fetch station and faction data via function calling aswell, you simply have to ask about it.
Galnet news can be fetched to answer questions or inform about relevant news in the galaxy.

### 7. Event-Driven Interaction

The system dynamically responds to game events such as ship type changes, new jump destinations, shield status updates, attacks, and more, keeping the commander informed of critical events and statuses.

We support **every event** in the game that is written to the journal file. You can toggle which game events should be reacted to. Here is a list of the currently supported event types:

#### Startup Events:
- Cargo
- Materials
- Missions
- Progress
- Rank
- Reputation
- Statistics

#### Powerplay Events:
- PowerplayCollect
- PowerplayDefect
- PowerplayDeliver
- PowerplayFastTrack
- PowerplayJoin
- PowerplayLeave
- PowerplaySalary
- PowerplayVote
- PowerplayVoucher

#### Squadron Events:
- AppliedToSquadron
- DisbandedSquadron
- InvitedToSquadron
- JoinedSquadron
- KickedFromSquadron
- LeftSquadron
- SharedBookmarkToSquadron
- SquadronCreated
- SquadronDemotion
- SquadronPromotion
- SquadronStartup
- WonATrophyForSquadron

#### Exploration Events:
- CodexEntry
- DiscoveryScan
- Scan

#### Trade Events:
- Trade
- AsteroidCracked
- BuyTradeData
- CollectCargo
- EjectCargo
- MarketBuy
- MarketSell
- MiningRefined

#### Station Services Events:
- StationServices
- BuyAmmo
- BuyDrones
- CargoDepot
- CommunityGoal
- CommunityGoalDiscard
- CommunityGoalJoin
- CommunityGoalReward
- CrewAssign
- CrewFire
- CrewHire
- EngineerContribution
- EngineerCraft
- EngineerLegacyConvert
- EngineerProgress
- FetchRemoteModule
- Market
- MassModuleStore
- MaterialTrade
- MissionAbandoned
- MissionAccepted
- MissionCompleted
- MissionFailed
- MissionRedirected
- ModuleBuy
- ModuleRetrieve
- ModuleSell
- ModuleSellRemote
- ModuleStore
- ModuleSwap
- Outfitting
- PayBounties
- PayFines
- PayLegacyFines
- RedeemVoucher
- RefuelAll
- RefuelPartial
- Repair
- RepairAll
- RestockVehicle
- ScientificResearch
- Shipyard
- ShipyardBuy
- ShipyardNew
- ShipyardSell
- ShipyardTransfer
- ShipyardSwap
- StoredModules
- StoredShips
- TechnologyBroker
- ClearImpound

#### Fleet Carrier Events:
- CarrierJump
- CarrierBuy
- CarrierStats
- CarrierJumpRequest
- CarrierDecommission
- CarrierCancelDecommission
- CarrierBankTransfer
- CarrierDepositFuel
- CarrierCrewServices
- CarrierFinance
- CarrierShipPack
- CarrierModulePack
- CarrierTradeOrder
- CarrierDockingPermission
- CarrierNameChanged
- CarrierJumpCancelled

#### Odyssey Events:
- Backpack
- BackpackChange
- BookDropship
- BookTaxi
- BuyMicroResources
- BuySuit
- BuyWeapon
- CancelDropship
- CancelTaxi
- CollectItems
- CreateSuitLoadout
- DeleteSuitLoadout
- Disembark
- DropItems
- DropShipDeploy
- Embark
- FCMaterials
- LoadoutEquipModule
- LoadoutRemoveModule
- RenameSuitLoadout
- ScanOrganic
- SellMicroResources
- SellOrganicData
- SellWeapon
- SwitchSuitLoadout
- TransferMicroResources
- TradeMicroResources
- UpgradeSuit
- UpgradeWeapon
- UseConsumable

#### Other Events:
- AfmuRepairs
- ApproachSettlement
- ChangeCrewRole
- CockpitBreached
- CommitCrime
- Continued
- CrewLaunchFighter
- CrewMemberJoins
- CrewMemberQuits
- CrewMemberRoleChange
- CrimeVictim
- DatalinkScan
- DatalinkVoucher
- DataScanned
- DockFighter
- DockSRV
- EndCrewSession
- FighterRebuilt
- FuelScoop
- Friends
- JetConeBoost
- JetConeDamage
- JoinACrew
- KickCrewMember
- LaunchDrone
- LaunchFighter
- LaunchSRV
- ModuleInfo
- NpcCrewPaidWage
- NpcCrewRank
- Promotion
- ProspectedAsteroid
- QuitACrew
- RebootRepair
- ReceiveText
- RepairDrone
- ReservoirReplenished
- Resurrect
- Scanned
- SelfDestruct
- SendText
- Shutdown
- Synthesis
- SystemsShutdown
- USSDrop
- VehicleSwitch
- WingAdd
- WingInvite
- WingJoin
- WingLeave
- CargoTransfer
- SupercruiseDestinationDrop

These event-driven interactions are designed to enhance safety, decision-making, and overall user engagement throughout the journey in Elite Dangerous.

![Event-driven](screen/event_driven.png?raw=true "Screen")

## Troubleshooting

1.  You can remove `config.json` to reset the GUI to its default values.
2.  You need to set certain key bindings so the AI is able to trigger the corresponding action. In case you forgot a key the integration the AI will tell you to register the missing keybinding. The integration will also list a warning at the top of the output window for each missing key.

# Contact
* Discord Server: https://discord.gg/9c58jxVuAT

# Credits
* [SumZer0](https://github.com/SumZer0-git) *For teaching me a thing or two about python programming, and giving me the idea to build a game event-driven RAG system!*

# @ToDos
* Installation video guide
* Add an auto-updater
* Add more APIs (atleast road-to-riches, neutron plotter and trader planner)