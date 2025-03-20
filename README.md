# Coupon API Testing with Postman

## Overview
This repository contains a Postman collection for testing the Coupon API. It includes requests for performing CRUD operations (Create, Read, Update, Delete) along with test scripts to validate responses.

## Prerequisites
- [Postman](https://www.postman.com/downloads/) installed on your system.
- The Coupon API should be running and accessible.
- Import the Postman collection from the following link:
  [Coupon API Collection](https://www.postman.com/dddd88-9159/workspace/d735abb7-7d01-46a5-b11d-c9f83c0d54ff/collection/37899226-0c5701c4-2521-4b4d-975d-006159f38459?action=share&source=collection_link&creator=37899226)

## Collection Structure
This Postman collection consists of the following API requests:

### 1. Get Coupons
- **Method:** `GET`
- **Endpoint:** `{{couponApi}}/api/coupon`
- **Description:** Fetches a list of available coupons.
- **Tests Included:**
  - Status code should be `200`.
  - Response should contain properties `couponId`, `couponCode`, `discountAmount`, and `minAmount`.

### 2. Get Deleted Coupon
- **Method:** `GET`
- **Endpoint:** `{{couponApi}}/api/coupon/8`
- **Description:** Attempts to fetch a deleted coupon.
- **Tests Included:**
  - Status code should be `404 Not Found`.

### 3. Create a Coupon
- **Method:** `POST`
- **Endpoint:** `{{couponApi}}/api/coupon`
- **Body:**
  ```json
  {
      "couponCode": "SAVE450",
      "discountAmount": 20,
      "minAmount": 100
  }
  ```
- **Description:** Adds a new coupon to the system.
- **Tests Included:**
  - Status code should be `201`.
  - Response should contain the created coupon details.

### 4. Update a Coupon
- **Method:** `PUT`
- **Endpoint:** `{{couponApi}}/api/coupon`
- **Body:**
  ```json
  {
      "couponId": 4349,
      "couponCode": "SAVE30",
      "discountAmount": 30,
      "minAmount": 150
  }
  ```
- **Description:** Updates an existing coupon.
- **Tests Included:**
  - Status code should be `200`.

### 5. Delete a Coupon
- **Method:** `DELETE`
- **Endpoint:** `{{couponApi}}/api/coupon/8`
- **Description:** Deletes a coupon with ID `8`.
- **Tests Included:**
  - Status code should be `204 No Content`.

## How to Use
1. **Import Collection:**
   - Click `Import` in Postman.
   - Paste the shared collection link or upload the JSON file.
2. **Set Up Environment Variables:**
   - Add a new environment in Postman.
   - Set `couponApi` to your API base URL.
3. **Run Requests:**
   - Open the desired request.
   - Click `Send` to execute the API call.
4. **View Results:**
   - Check the response body.
   - Look at the `Test Results` tab to verify test assertions.

## Contributing
Feel free to contribute by adding new test cases or improving existing scripts. Fork the repository and submit a pull request with your changes.

## License
This project is open-source under the MIT License.


