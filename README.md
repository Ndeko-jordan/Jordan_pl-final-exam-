PROJECT NAME: STOCK MANAGEMENNT SYSTEM
NAMES: NDEKO KADULI JORDAN
ID: 25243

📘 III. Phase: Logical Model Design
This phase outlines the detailed logical data model for the Stock Management System. It aligns with the initial problem statement and business processes defined in earlier phases, ensuring a robust foundation for database implementation.

1. Entity-Relationship (ER) Model
🧩 Identified Entities and Attributes:
Entity	Attributes
Product	product_id (PK, INT), name (VARCHAR), category (VARCHAR), price (DECIMAL), quantity (INT)
Supplier	supplier_id (PK, INT), name (VARCHAR), contact_info (VARCHAR)
Purchase	purchase_id (PK, INT), product_id (FK), supplier_id (FK), quantity (INT), purchase_date (DATE)
Sale	sale_id (PK, INT), product_id (FK), quantity (INT), sale_date (DATE)
User	user_id (PK, INT), username (VARCHAR), password (VARCHAR), role (VARCHAR)

✅ All foreign keys establish referential integrity across related entities.

2. Relationships & Constraints
🔗 Relationships:
One Supplier → Many Purchases

One Product → Many Purchases and Many Sales

One User → Can Record Many Sales and Purchases

⚠ Constraints:
product_id, supplier_id, purchase_id, sale_id, and user_id are Primary Keys (PK).

product_id in Purchase and Sale are Foreign Keys (FK) referencing Product.

supplier_id in Purchase is a Foreign Key referencing Supplier.

quantity fields: CHECK (quantity >= 0)

username: UNIQUE, NOT NULL

role: DEFAULT 'employee', CHECK (role IN ('admin', 'employee'))

3. Normalization
The logical model adheres to the Third Normal Form (3NF):

1NF: All attributes are atomic (no repeating groups).

2NF: All non-key attributes are fully functionally dependent on the PK.

3NF: No transitive dependencies between non-key attributes.

This ensures minimal redundancy and efficient data storage.

4. Handling Real-World Data Scenarios
The logical model supports:

Recording sales and purchases across different suppliers and dates.

Managing stock levels by updating quantities on each transaction.

Differentiating user access levels (e.g., Admins vs. Employees).

Adding new products/suppliers without affecting the existing structure.

Edge case handling includes:

Preventing negative inventory via CHECK constraints.

Ensuring only valid roles are assigned to users.

![patient_record_bpm](https://github.com/user-attachments/assets/2a3dd153-07c9-4198-8dab-c7b385f8a3ac)





📊 II. Phase: Business Process Modeling (Related to MIS)
1. Define the Scope
Business Process Modeled: Inventory Management and Sales Flow in a Stock Management System

Relevance to MIS:

Supports real-time decision-making by tracking stock levels.

Improves operational efficiency by automating purchase and sale tracking.

Enables forecasting by providing accurate reports to managers.

Objectives:

Automate inventory updates upon product purchase and sale.

Prevent stockouts and overstocking by monitoring product levels.

Enhance transparency and accountability among users (admin vs. staff).

Enable data-driven reporting for managerial decisions.

Expected Outcomes:

Timely restocking of inventory.

Accurate inventory records.

Simplified workflow for employees.

Actionable insights for the management team.

2. Identify Key Entities
Entity	Description
Admin/User	Employees who manage inventory operations—add products, record sales/purchases, generate reports.
Supplier	External providers who deliver products.
Customer	End-users buying products from the system.
System (MIS)	The backend that manages data flow, stock calculations, notifications, and reporting.
Database	Stores all data: product info, users, transactions, suppliers.
Manager	Reviews performance reports and decides on restocking or strategic changes.

3. Swimlanes Structure Suggestion
Use tools like Lucidchart or draw.io and organize swimlanes like this:

Swimlane 1: User (Employee/Admin)

Login

Add new product

Record purchase/sale

View stock

Swimlane 2: System (MIS)

Validate input

Update database

Generate alerts if stock low

Generate daily/weekly reports

Swimlane 3: Supplier

Receives order

Ships goods

Swimlane 4: Manager

Reviews reports

Approves restocking

4. Use of UML/BPMN Notation
Notation Recommendations:

Start Event (Circle): Triggered by user login or product purchase.

Tasks (Rectangle): Actions like “Add Product”, “Update Stock”.

Decision Gateways (Diamond): e.g., “Is stock below threshold?”

End Event (Bold Circle): e.g., “Generate Report”, “Notify Manager”.

Data Stores (Cylinder): e.g., Database updates.

Make sure each actor’s actions are clearly laid out in their swimlane.

5. Logical Flow Highlights
The system follows a logical sequence:

Admin logs in.

Adds a product or views stock.

When a sale is made, quantity is reduced.

If stock < minimum, system notifies manager.

Manager reviews and orders from supplier.

Supplier processes and delivers goods.

System updates stock and logs the transaction.

Reports are generated for analysis.

Each step maintains MIS principles of accuracy, traceability, and support for decision-making.

6. Explanation of Diagram (One Page Summary)
This business process diagram models the flow of inventory and decision-making in the stock management system. It outlines how employees interact with the system to manage product inventory, how sales and purchases are recorded, and how the system automatically updates data and alerts relevant stakeholders.

The MIS supports decision-making by:

Tracking inventory in real-time

Alerting for restocking

Providing sales/purchase trends

Generating reports for strategic oversight

This process improves organizational efficiency by automating tasks, reducing manual errors, and enabling timely interventions based on accurate data.

✅ Tools Recommendation:
Use Lucidchart or draw.io to create a BPMN-compliant diagram using swimlanes.

Export as PNG/SVG to attach in reports or presentations.
![stock_management_er_diagram](https://github.com/user-attachments/assets/234388b9-4582-4510-a01c-7e96d3245372)


IV. 	Phase: Database (Pluggable Database) Creation and Naming :

![WhatsApp Image 2025-05-25 at 16 18 57_8920f0dd](https://github.com/user-attachments/assets/0bace1eb-1654-4bbb-9aba-840007983fdf)
![WhatsApp Image 2025-05-25 at 15 17 15_cfcaba19](https://github.com/user-attachments/assets/42c69f95-1e96-4e53-97ce-5d929ec1c67f)
![WhatsApp Image 2025-05-25 at 15 24 20_d3edad1b](https://github.com/user-attachments/assets/85eea565-4623-44bd-9535-9be6c373bc3a)

	 	V. TABLE IMPLEMENTATION AND DATA INTERGRATION

   ![image](https://github.com/user-attachments/assets/b3eb82f2-81d7-49d1-9175-1e42bf0b92d2)
![image](https://github.com/user-attachments/assets/e80082c2-3fb6-41cb-b045-0a8127cf503b)
![image](https://github.com/user-attachments/assets/9d4e7a83-6a6f-400f-8acb-9859d356e4de)
![image](https://github.com/user-attachments/assets/2f0f3d62-73b9-427f-95b4-82aeee8e8083)
![image](https://github.com/user-attachments/assets/43f90afe-e875-463f-8df5-2d6d3d972532)

![image](https://github.com/user-attachments/assets/e69b2e02-85ae-4c81-a389-0ea194c5d5c4)

