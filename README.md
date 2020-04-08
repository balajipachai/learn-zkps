# learn-zkps
Let us learn Zero Knowledge Proofs (zk-SNARK)

# Steps

1. Install zokrates 

      `curl -LSfs get.zokrat.es | sh`

2. To get started, create a file test.zok and add the following lines to it

    ```
      def main (private field a, private field b) -> (field) :
      field result = if a * a == b then 1 else 0 fi
      return result
    ```

`This program checks whether a is a square of b.`

3. Further steps are compiling, creating a trusted setup, computing witness, generating proof and exporting the verifier.
  - All the steps can be performed by using zokrates which we have installed above
    - compile: `zokrates compile -i test.zok`
    - setup: `zokrates setup`
    - compute-witness: `zokrates compute-witness -a 11 121`
    - generate-proof: `zokrates generate-proof`

      - This creates a proof.json file, which contains the inputs for the verifier.sol's verifyTx() function. The verifier contract will be generated in the next step.

    - export-verifier: `zokrates export-verifier`

4. Go to remix online compiler, paste in the verifier.sol contact in the browser and once that is done invoke the verifyTx() with the inputs from the proof.json file

# References:

  1. [zk-SNARK's using ZoKrates](https://blog.gnosis.pm/getting-started-with-zksnarks-zokrates-61e4f8e66bcc)

  2. [Zokrates Documentation](https://zokrates.github.io/gettingstarted.html)


# Note

  - The steps are being laid down in a learn and implement phase, if you find something is not correct, please raise an issue, this would benefit us all.