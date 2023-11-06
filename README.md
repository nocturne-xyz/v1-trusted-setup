## Nocturne V1 Trusted Setup


This repo serves as a record of all contributions to Nocturne V1's trusted setup. All zkeys and transcripts are made available in a public S3 bucket, so that anyone may independently verify them.

Parameters for the following three circuits were made for the trusted setup:

| Circuit | # of Contributions | Full Transcript | Final zkey |
|------|--------------------|----------------|
| canonaddrsigcheck | 259 | [view](canonaddrsigcheck.md) | [download](https://nocturne-v1-ph2-ceremony.s3.amazonaws.com/circuits/canonaddrsigcheck/contributions/canonaddrsigcheck_final.zkey) |
| joinsplit | 251 | [view](joinsplit.md) | [download](https://nocturne-v1-ph2-ceremony.s3.amazonaws.com/circuits/joinsplit/contributions/joinsplit_final.zkey) |
| subtreeupdate | 57 | [view](subtreeupdate) | [download](https://nocturne-v1-ph2-ceremony.s3.amazonaws.com/circuits/subtreeupdate/contributions/subtreeupdate_final.zkey) |

For our randomness beacon used to finalize the circuit, we used the output from drand mainnet at round `3461729`:
- network: mainnet (chainhash `8990e7a9aaed2ffed73dbd7092123d6f289930540d7651336225dc172e51b2ce`)
- round: `3461729`
- value: `6efaf5842d729297ca61990527787db63d48187aed52135ac169b4d87d091847`

This can be independently verified by making the following `GET` request to their public API: [https://drand.cloudflare.com/8990e7a9aaed2ffed73dbd7092123d6f289930540d7651336225dc172e51b2ce/public/3461729](https://drand.cloudflare.com/8990e7a9aaed2ffed73dbd7092123d6f289930540d7651336225dc172e51b2ce/public/3461729). It should give the following response:
```
{
	"round": 3461729,
	"randomness": "6efaf5842d729297ca61990527787db63d48187aed52135ac169b4d87d091847",
	"signature": "b266c2d1877b82122de5eb265e752982669faf69dbc861ebcedd67ce78e9f82d67154b5385f0fa600ac00dd492fd3afd13799603ca4d8f01b89d9da8b23a611d2b89d91afd6763ffc85a13af07b0956ac24f6eb993a498e62db81e3b9a8cb153",
	"previous_signature": "8bdf9c2c2d7582a46fccd8f861c4b92620019241f99d3f79fc3291bd077b02f6abe1bcc9ca78fab9048b9f7f4287a05319435e89ff2d4658cfaa2bf0c29ef831dae50c13e6ec9817105c4f68e621af20ff28b230c0859ffcc238d491765b7590"
}
```
