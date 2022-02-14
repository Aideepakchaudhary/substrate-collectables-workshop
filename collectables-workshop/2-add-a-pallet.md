# Project structure

Using the node template the easiest way to get your Substrate blockchain up and running.
You should have that already installed and compiled. 
Compilation time takes a while at first but subsequent builds won't take as long.

When you run: 
```bash
./target/release/node-template --dev
```

.. you've just launched a single node, proof of authority local network with basic account and balances capabilities, transaction payment functionality and Sudo governance. 👊

To kill your node, hit `Ctrl + c`.

Now, let's take a closer look at the structure of the node template we'll be working with. 👀

1. Open up your code editor with your compiled node template.
(Or, if you're using the Substrate Playground, go to a Node Template instance and hit `Ctrl + c` to stop the chain).
1. Notice the `node`, `pallets` and `runtime` folders
1. Go to `runtime/src/lib.rs` and `Ctrl + f` "construct_runtime!(".
This should take you to line 290.

The `construct_runtime` macro compiles externally published pallets to generates the state transition function of our chain. 
These are the pallets in the runtime of our node template:

* 🛠 `System: frame_system`: core system level functionality.
* 🎲 `RandomnessCollectiveFlip: pallet_randomness_collective_flip`: provides on-chain pseudo-randomness.
* ⌚️ `Timestamp: pallet_timestamp`: provides on-chain timestamping utilities.
* 👮 `Aura: pallet_aura`: proof of authority consensus.
* 👴 `Grandpa: pallet_grandpa`: block finalization utility.
* 💰 `Balances: pallet_balances`: the underlying currency system for our chain.
* 💳 `TransactionPayment: pallet_transaction_payment`: transaction fee system.
* 🕹 `Sudo: pallet_sudo`: most basic on-chain goverance.
* 📄 `TemplateModule: pallet_template`: an dummy pallet to make it easy to start hacking with.


<!-- slide:break-40 -->
![project](assets/structure.png)


