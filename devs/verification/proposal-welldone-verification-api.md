## Importance of Smart Contract Verification

Smart contract verification is crucial for enhancing transparency and security. We aim to contribute to the Ethereum ecosystem's verification culture by providing an API to Blockscout, facilitating the sharing of verified contract information.

## Support for Layer 2 Languages in the Ethereum Ecosystem

Recently, various languages have been supported in the Ethereum ecosystem, particularly in Layer 2 solutions. For example, Arbitrum Stylus supports the Rust language, and Starknet supports the Cairo language. Due to these characteristics, developing web-based verification services beyond Solidity poses a significant challenge. Therefore, we aim to offer verification request APIs for these languages to Blockscout and to popularize verification by sharing verified contract information within the Ethereum ecosystem.

---

## Arbitrum Verification API Endpoints

### GET `/arbitrum/verifications` Endpoint

A GET request to retrieve Arbitrum verification data.

### Parameters

- **network** (string, required)
    - Description: Available values are `ARBITRUM_ONE`, `ARBITRUM_SEPOLIA`.
    - Example: `ARBITRUM_SEPOLIA`
- **contractAddress** (string, required)
    - Description: Enter the address of the contract to be verified.
    - Example: `0x69a65a225890a0ff91515f0bd017b8c7fdd62353`

### Responses

- **Code**: 200
    - **Description**: A successful response is returned in JSON format.
    - **Example Response**:
        
        ```json
        
        {
          "network": "ARBITRUM_SEPOLIA",
          "contractAddress": "0x69a65a225890a0ff91515f0bd017b8c7fdd62353",
          "deploymentTxHash": "0xb2fe062f53e66acf2208d387ee39f7e346e616d84161eeb04a7187b4b34a",
          "deployedCLIVersion": "0.4.2",
          "verifiedCLIVersion": "0.5.1",
          "isRemixSrcUploaded": true,
          "verifiedSrcUrl": "<https://verification-storage.com/arbitrum/mainnet/0xc948e62bc2e632d710717d23ff05872e7c847ec78851af37885c4f54bef0c0/1694984081666/1694984081666.zip>",
          "outFileUrl": "<https://verification-storage.com/arbitrum/mainnet/0xc948e62bc2e632d710717d23ff05872e7c847ec78851af37885c4f54bef0c0/1694984081666/out_1694984081666.ns.zip>",
          "verifyRequestAddress": "0x0ED5572E8D64826A0F3F55217A80a4C9448a6af",
          "errMsg": "Source code was not uploaded."
        }
        
        ```
        

---

### POST `/arbitrum/verifications` Endpoint

A POST request to process Arbitrum verification requests.

### Request Body (Required)

```json

{
  "network": "ARBITRUM_SEPOLIA",
  "contractAddress": "0x69a65a225890a0ff91515f0bd017b8c7fdd62353",
  "cliVersion": "0.5.5",
  "verifyRequestAddress": "0x0ED5572E8D64826A0F3F55217A80a4C9448a6af",
  "srcFileId": "1695022436873"
}

```

### Responses

- **Code**: 201
    - **Description**: A successful response is returned in JSON format.
    - **Example Response**:
        
        ```json
        
        {
          "network": "ARBITRUM_SEPOLIA",
          "contractAddress": "0x69a65a225890a0ff91515f0bd017b8c7fdd62353",
          "deploymentTxHash": "0xb2fe062f53e66acf2208d387ee39f7e346e616d84161eeb04a7187b4b34a",
          "deployedCLIVersion": "0.4.2",
          "verifiedCLIVersion": "0.5.1",
          "verifiedSrcUrl": "<https://verification-storage.com/arbitrum/sepolia/0xc948e62bc2e632d710717d23ff05872e7c847ec78851af37885c4f54bef0c0/1694984081666/1694984081666.zip>",
          "verifyRequestAddress": "0x0ED5572E8D64826A0F3F55217A80a4C9448a6af",
          "errMsg": null}
        
        ```
        

---

## POST `/arbitrum/verifications/sources` Endpoint

A POST request to upload Arbitrum verification sources.

### Request Body (Required)

- **contractAddress** (string, required)
Description: Enter the address of the contract to be verified.
- **chainId** (string, required)
Description: Specify the chain ID.
- **srcZipFile** (string(binary), required)
Description: Upload the Cairo contract ZIP file.

### Responses

- **Code**: 200
    - **Description**: Response returned when the Cairo contract ZIP file is successfully uploaded.
    - **Example Response**:
        
        ```json
        
        {
          "contractAddress": "0x69a65a225890a0ff91515f0bd017b8c7fdd62353",
          "chainId": "0x534e5f41494e",
          "srcZipFile": "string"
        }
        
        ```
        

---

## Additional Information

By providing an API for source code uploads and verification requests targeting Arbitrum Stylus and sharing verified APIs with Blockscout, we aim to create synergy. In particular, users can compile, deploy, and verify contract code in one process via our Arbitrum Stylus Plugin.

<img width="1105" alt="스크린샷 2567-11-16 13 26 25" src="https://github.com/user-attachments/assets/66de5ada-d6d5-4254-874b-f8a5518433b2">
<img width="1191" alt="스크린샷 2567-11-16 13 27 15" src="https://github.com/user-attachments/assets/c23378a4-ec08-4805-96a1-9e52a9169c9b">

---

Our roadmap is to promote the culture of verification in the Ethereum ecosystem, join the Verifier Alliance, and become a key public goods development team within the Ethereum ecosystem in collaboration with the Blockscout team.
