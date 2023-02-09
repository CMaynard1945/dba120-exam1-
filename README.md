Database 120 OA1 Exam 1 

1) Exercise 1 asked to write an Insert statement that added a row with a terms_id of 6, terms_description of "Net due 120 days" and terms_due_days of 120 into the Terms table in the AP database.

INSERT INTO terms (terms_id, terms_description, terms_due_days) 
VALUES (6, 'Net due 120 days', 120)

![image](https://user-images.githubusercontent.com/122292816/217953316-d580d450-bf10-4451-8b75-43796763aa45.png)

2) Exercise 2 asked to write an Update statement that would change an existing row, that was made in the previous exercise to change the terms_description column to "Net due 125 days" and the terms_due_column to 125.

UPDATE terms
SET terms_description = 'Net due 125 days', terms_due_days = '125'
WHERE terms_id = '6';

![image](https://user-images.githubusercontent.com/122292816/217953697-130a2876-ab96-4163-9166-d87f19c65d53.png)

3) Exercise 3 asked to write a DELETE statement that would remove the row added in Exercise one from the Terms table.

  DELETE terms
  WHERE terms_id = 6

 ![image](https://user-images.githubusercontent.com/122292816/217953969-f0aeaa87-7ff2-4fc9-a411-16d19be1df34.png)

4) Exercise 4 asked to write an Insert statement that would add a new row to the Invoices Table.

INSERT INTO invoices VALUES
	(DEFAULT, 32, 'AX-014-027', '2018-08-01', 434.58, 0.00, 0.00, 2, '2018-08-31', NULL)

![image](https://user-images.githubusercontent.com/122292816/217954161-058bc713-ef01-4cf1-b18f-4790d0e9f244.png)


5) Exercise 5 asked to wrie an Insert statement that would add two row sto the Invoice_Line_Items table

![image](https://user-images.githubusercontent.com/122292816/217954307-a75f4559-1fc6-4160-9ec4-597c9ae59118.png)

INSERT INTO invoice_line_items
	(invoice_id, invoice_sequence, account_number, line_item_amount, line_item_description)
VALUES
	(115, 1, 160, 180.23, 'Hard Drive'),
  (115, 2, 527, 254.35, 'Exchange Server update')

6) Exercise 6 asked to write an Update statement that would change the credit_total column to the be 10% of the invoice_total column. Also to modify the payment_total column so that it and the credit_total column would equal the invoice_total.

UPDATE invoices
SET credit_total = invoice_total * .1, payment_total = invoice_total - credit_total
WHERE invoice_id = 115

![image](https://user-images.githubusercontent.com/122292816/217954608-24cfbff9-48e0-4a68-bae2-8170104f3180.png)


7) Exercise 7 asked to write an Update statement that would change the Invoice table, specifically the terms_id column. It said to change the column to a value of 2 for each invoice with a default_terms_id of 2.

UPDATE vendors
SET default_account_number = 403
WHERE vendor_id = 44

![image](https://user-images.githubusercontent.com/122292816/217955591-caefc2f2-2fd3-4dbf-b33a-54b5427c2df3.png)

8) Exercise 8 asked to write that Update statement that would change rows in the terms_id column for each invoice with a vendor who has a default_terms_id of 2.

UPDATE invoices
SET terms_id = 2
WHERE vendor_id IN
  (SELECT vendor_id
  FROM vendors
  WHERE default_terms_id = 2);

![image](https://user-images.githubusercontent.com/122292816/217955820-4d69643f-04b5-4d09-8468-8e1d41277f37.png)

9) Exercise 9 asked to write a Delete statement that would remove the rows made the previous exercises uses two back to back statements.

DELETE FROM invoice_line_items
WHERE invoice_id = 115;
DELETE FROM invoices
WHERE invoice_id = 115;

![image](https://user-images.githubusercontent.com/122292816/217955947-e5eccfdb-a640-4e3f-89c5-b415f68e926e.png)
