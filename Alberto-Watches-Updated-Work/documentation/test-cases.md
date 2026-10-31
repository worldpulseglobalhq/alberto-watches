# Test Cases — Alberto Watch Company

| ID | Feature | Test | Expected result | Status |
|---|---|---|---|---|
| TC-01 | Home carousel | Move to next/previous slide | The three hero videos change per slide | Static markup checked; browser test pending |
| TC-02 | Product catalogue | Load Shop page | Product cards render from `js/products-data.js` (20 watches + 20 clocks) | Data/image mapping checked |
| TC-03 | Search and filters | Search a watch name; filter category/price; sort | Results and count update | Handler syntax checked; browser test pending |
| TC-04 | Add to Cart | Add one product, then increase/decrease quantity | Cart count and subtotal update | Code reviewed; browser test pending |
| TC-05 | Buy on WhatsApp | Click a product's Buy on WhatsApp button | Checkout opens with selected product preview | Route code checked; browser test pending |
| TC-06 | Coupon | Apply the configured active code | Discount appears in summary and total decreases | Config/logic checked; browser test pending |
| TC-07 | Invalid coupon | Apply a wrong or inactive code | Error shown and no coupon discount applied | Logic checked; browser test pending |
| TC-08 | Edit coupon | Change code/percent in `js/config.js` | Home voucher and checkout use new values | Shared configuration checked |
| TC-09 | Delivery address | Click Detect my location and allow permission | Address fields are filled where reverse lookup provides data | Permission/lookup requires browser test |
| TC-10 | Phone validation | Enter invalid mobile number | Checkout is blocked with validation feedback | Regex and form handler checked |
| TC-11 | Sign Up | Register a new email and matching password | Local account is created and login page opens | Handler syntax checked; browser test pending |
| TC-12 | Login | Try unknown email, wrong password, then correct details | Unknown/wrong credentials rejected; correct credentials accepted | Handler syntax checked; browser test pending |
| TC-13 | Page assets | Check HTML links and script order | All local targets exist; Bootstrap, jQuery, config and app scripts are linked | Automated static check |

**Important:** No full browser-based interactive test suite was run during packaging. This project is a front-end Aptech store and is not ready to process real payments or secure production accounts.
