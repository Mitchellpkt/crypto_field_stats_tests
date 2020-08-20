# Empirical uniformity analysis 

## Scope

Every field in a transaction falls into one of four buckets:
1. Signer-selected, expected to be non-uniform across transactions (e.g. unlock time)
2. Descriptive, expected to be non-uniform acrosss all transactions (e.g. transaction version)
3. Signer-selected, expected to be uniform across transactions (e.g. MLSAG/CLSAG scalars)
4. Function output, expected to be uniform across all transactions (e.g. public keys)

**In this repository, we will analyze the on-chain data for non-uniformity in types #3 and #4.** This repository is _not_ exploring non-uniformity in types #1 and #2 (see [Noncesense](https://github.com/noncesense-research-lab/) for those studies)

## Notes
Things to look for:
- Unexpectedly frequent collisions
- Nonuniformity
- Low entropy
- (what else ??)

## Example
Consider a random 1-in/2-out transaction: [https://xmrchain.net/tx/fd903232053a5ac6d8cf99ce494da2ec73488c94c33ee587523ae356b59b5579](https://xmrchain.net/tx/fd903232053a5ac6d8cf99ce494da2ec73488c94c33ee587523ae356b59b5579)

Our expectations, labeled by the buckets described above, are:

```
--- {
[2] version: 2,
[1] unlock_time: 0,
--- vin: [ {
--- key: {
[2] amount: 0,
[1] key_offsets: [ 19599438, 5461, 186398, 87294, 17982, 38089, 2853, 3260, 8816, 6649, 1249
--- ],
[4] k_image: "1a01d8440f022d0b0760ba3fbc8afc4a12924135a33442730384672d7b83fc4e"
--- }
--- }
--- ],
--- vout: [ {
[2] amount: 0,
--- target: {
[4] key: "94125a4ac1171a57f908b532dda050bac0791adeee855e7ce4696835953ac45c"
--- }
--- }, {
[2] amount: 0,
--- target: {
[4] key: "9cb62212b9daaadf050d6e140b3d94f49ef122113b090e05c4b0cc501c1044b1"
--- }
--- }
--- ],
[1] extra: [ 2, 9, 1, 130, 106, 178, 102, 250, 94, 37, 132, 1, 214, 14, 153, 33, 132, 235, 13, 138, 29, 96, 104, 34, 168, 207, 152, 197, 22, 125, 150, 202, 47, 36, 9, 78, 41, 189, 146, 248, 143, 178, 186, 109
--- ],
--- rct_signatures: {
[2] type: 4,
[1] txnFee: 136770000,
--- ecdhInfo: [ {
[4] amount: "8cd29109454982ad"
--- }, {
[4] amount: "f2ead60bc24eb1aa"
--- }],
[4] outPk: [ "6a97cea40d6763f1cd68c966ec9ee827a7841faf70fa82e95491fe1b668d3e40", "7868bf57da6d5f48054179da06509bd80b5dec4214bb7acb69dec11d422686ff"]
--- },
--- rctsig_prunable: {
[2] nbp: 1,
--- bp: [ {
[?] A: "ee1a86b7d570628cbda5458623f5d300fc9e178cefc0fa6f8ba3772b2f85d63c",
[?] S: "517f04819c405ccf89309bf3c6c2d4ad86059fd877851c1d752593529265b50f",
[?] T1: "a4466b683f4299cc88550a94d562ee2b6c8c4e77ce6fe17e51be88c0b0289927",
[?] T2: "7f7396420c64f5dfab1e82f06caa7bc408d4cec4cc4dd3249a2dc905aa12942f",
[?] taux: "7b886a9c8642ce258ab7eed4fd57aecd6ffe264e7b6fb0dd53e9395c7cf22902",
[?] mu: "6db7ec71b23d9b4141309848338f697f63bed31bf6e29d4eb00cfbae6838ba0b",
[?] L: [ "aeee6d21c477b6420d42eaf0cbf79e925205d9bcff60e107da77004535227cdb", "4dba03a74bd2196f65e789a5aa6df4e194cbae91ab174ae1c9ae91710a06694b", "873bacddcee7038f7868790e721c5137d7f949cc87e598444b02aa3ed5930069", "c5faebda6f518f1df09ff2f7cb7cb7bb8f64e0bfe6bf0aa207a7d540477381b2", "27a85151ed68566ee68c2532c517c367e1f572a60af176eb0f755d6b1af1d328", "2d702d1b501d59f90016162f2f5e2f63f5cfecc62cfa7d18962736baa9fa207e", "22672fd234b0f79baff67991b20fa2d3c4fd2933b6468b06ef4fe2c24b00cd00"
--- ],
[?] R: [ "b5cdc4fba8caeae03da889404275c52507ac7707f60e59205134b6562eb82bbe", "ab60dad957e7aace82b64a3fdda46d03bd955862b7a2498b281868aa9a87f18f", "caf05132253b2d87e2004cf5d7b62dfe471ee542cd0e642ba1021fa10f725649", "9f487459a8b86a40ca59f1ad524cbe7e492fd6c98293b74ffa6212593ea8f1a9", "cab23fd7714acb105c1a1bb18711048cdd198b9393abcdbe185828d6b2b5ccd5", "013e132947965962a2ba209ff4ba858fba6e0dc9d0dd736e4a67205210c09c84", "8e4b2d985986399c33ec9ea3b6c6846e1dd2f4cde7cbb058fc45e05636f0d540"
--- ],
[?] a: "b44cefe5c19b485dfde10bc63280db5bedd39b53427b7f9abecfde70e78dc50f",
[?] b: "061bf7695eb15bae7b868369dfad1a11c8726aa653f819ebb33071fc04b3f706",
[?] t: "f4386476bb24e1cf5c228643d3c97e526f155f5375c0a7b688c32ff40a2e7f01"
--- }
--- ],
--- MGs: [ {
[3] ss: [ [ "22f88f4f232a8e02f93dc17f8b250fcc449b0373819e2aa7b9bcc54f51b6e905", "b1e23b676d95d944d66a18be5ec2221d5faeeafcd149f6cff3adb868fe94800c"], [ "93450d60e81e644f1476805cfeac4d9e2a6ff8f76af0038f0da2b25ae9e50609", "20139ad874ac91cbb76d619791418bfd0ad0b255c561bf9bb97f21bd9a13fd0d"], [ "462bd9ffadb4c6641f8b95408d4a3baacb58d36dcbd8030b51806bc695f73a0f", "ca525025c720244fefa9ea5c7c503f0c25678ee8436fd99bc5d0efaeb9e08606"], [ "c751354f2e745c28d643a78161a5ce1a305c332163a318b412775e0e3e4a960d", "f7f60d7ebf0bb112339e9753a0ed4bd1e861846e6e54733da79ece57561de108"], [ "d5a4e5f105dc45282bdda98beef875d34c200ac03b7ffafa902ac9b3c46fb209", "cd3cf768c82dc06b08d76e5f23376c0359de9f1de8134ef47ff8866c8faf0307"], [ "2cc0af60f5983bb92169eb701a2f62bc0ee668b152c7853e3c4b93e85f008f05", "b4933541a396d7ff52c3dda808cf9b19c67e556731b76053073b50dae8c09e0a"], [ "b87c9f95167107b0addf632ed7349ad492deda5e65e6af6adb2511f32ad01b07", "c9fde18e960db554e607851c5d467309bc7d6413a242c3337018e19a22c4a802"], [ "a1abcbb9b6df98c5538c58aad4bf025276c5d9b79f256d7120d751c93e7d7d0a", "a70b00110be253fbbcc6c533514ca4adbd43457b36f9d35ca62b716df8a52206"], [ "fbbb50ce4b0c63764b7dff8e2183253d16a7e73f9a5c45b8ef4a2f8ccda1e102", "0a197a839459e41b27cd361095dde1df0a1d3a93ed3b8770afe9563b883abd0e"], [ "60767b882e2d645211094117b3de8f1587bf761fa947689ce87e843c3f2c7900", "4baebd5ce76b3752575ec6411af90314c9c654702dfada6a79665ad55d69800c"], [ "7ffabc31e3b301d2fbe15e5def7c52ef23ff324355f6bfb96e9eb93d158b7308", "13ff32593304fa18020ecfbcc50fb0c8512d8b99061616f4b9a5179bee289204"]],
[?] cc: "fc2593c669652ec1a144a1bba8e5acd4990e7d552dd106cb32798096a48c0608"
--- }],
[4] pseudoOuts: [ "b289c2ebd5f5aff23c5c426fc7fefce0339fb1658dffe76648c37aa5fe743fd3"]
--- }
--- }                

```
