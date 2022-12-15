## Implemented Macros

`declare_id!`

This functions exactly like the `declare_id!` macro in the `solana_program` package. Call it at the top of your program to create a global variable called `ID`. Note: you must import `Pubkey` from either `solana_program` or `solana_sdk` for this to work.

```rust
use ellipsis_macros::declare_id;
use solana_sdk::pubkey::Pubkey;
declare_id!("9BoN4yBYwH63LFM9fDamaHK62YjM56hWYZqok7MnAakJ");
```

`declare_pda!`

This macro takes in a base58-encoded PDA, a base-58 encoded program id, and a string literal representing the seed of the PDA. The macro will check that the supplied PDA is indeed the output of calling `find_program_address` on the program id and seed. If this succeeds, then the bump seed will be written to a variable called `BUMP` and the PDA will be written to a variable called `ID`. Note: you must import `Pubkey` from either `solana_program` or `solana_sdk` for this to work.

```rust
use ellipsis_macros::declare_pda;
use solana_sdk::pubkey::Pubkey;
declare_pda!(
  "F46iAvcTENE8BBpSaQnumRw868p9o37AFhFvBkfKqu1e",
  "9BoN4yBYwH63LFM9fDamaHK62YjM56hWYZqok7MnAakJ",
  "hello"
);
```
