# RTO DRS Closure prototype

Clickable prototype of the RTO DRS Closure flow for first mile operations in Valmo Console. It reuses the POD DRS Closure designs (Undelivered Inward Scan, FE validated, Enter OTP modal) from the Ops-tech Integration Figma file and adapts them for RTO.

Open `index.html` in a browser. It is one self-contained file and only loads the Figtree font from Google Fonts.

## Flow

1. Click **RTO** in the left pane, then open the **DRS Closure** tab.
2. Select a Delivery Executive. The page shows the Lost in field card, the scan bar, summary cards and the pending table.
3. Use the scan type dropdown to switch between:
   - **Scan RTO Undel Shipments**, which shows "RTO Undelivered shipments Inward Scan Pending"
   - **Scan Picked up Shipments**, which shows "Picked up shipments Inscan Pending"
4. Scan a waybill (click a waybill number to fill the scan box) or use Mark Lost / Undo Lost on each row.
5. When nothing is left pending, **Enter OTP to close RTO DRS** opens straight away. There is no Cash Collected step.
6. The OTP modal shows only Lost in field counts for RTO Undel and Pickup (no COD collected). The button is **Close RTO DRS**.

## Product rules in the prototype

- Close RTO DRS stays locked until every RTO Undel and picked up shipment is inscanned or marked lost. The page also has a Close RTO DRS button in case the modal is dismissed.
- Scanning a waybill under the wrong scan type shows an error asking the user to switch the type.
- Lost in field on the page and in the OTP modal counts RTO Undel and Pickup separately.
- In the demo, OTP `000000` shows the wrong-OTP error. Any other 6 digits closes the DRS.

## Assumptions to confirm

- The **RTO Report** tab next to DRS Closure is a placeholder for RTO's existing sub-modules.
- Summary cards: RTO Delivered, RTO Undelivered, Picked up, Inscan Pending. The COD card is dropped.
- RTO Undel table has no NDR column. The picked up table shows Pickup ID, Seller, Picked up On and Qty.
- OTP label reads "Enter the OTP sent to <FE name>".

## Links

- Live artifact (private): https://claude.ai/artifact/Y5jkewuLwbGTvUykvUkCft
- Figma reference: Ops-tech Integration, page "POD ✅", section "POD_Final Designs"
