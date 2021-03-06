# Testing Cloud Firestore
Writing Cloud Firestore functions and security rules is relatively well documented and understood. Testing them, however, is not.

This repository is companion code to the [following article](https://medium.com/@danahartweg/testing-guide-for-cloud-firestore-functions-and-security-rules-39d9f3c92d99).

## Quick setup
```bash
yarn global add firebase-tools@7.3.0

cd server
yarn install
yarn lint && yarn validate
```

## Running the tests
If you want to run the cloud function tests, you **must** set a local firebase project that corresponds to the [project id found here](./server/test-helpers/firestore-helpers.ts#L19)

If you don't both use and specify an actual project id, cloud functions won't trigger in response to database writes. This tidbit slowed me down for the longest time, and I've confirmed it as expected behavior with firestore support.

```bash
yarn test
```
