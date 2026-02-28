РОЗДІЛ 7. МОДЕЛЬ ДАНИХ
7.1 Загальна характеристика

Модель даних реалізується у вигляді реляційної бази даних.

Основні сутності системи:
User (Користувач)
Role (Роль)
Client (Клієнт)
InsurancePolicy (Договір)
InsuranceCase (Страховий випадок)
Payment (Виплата)

7.2 Опис сутностей
1. User
user_id (PK)
username
password
role_id (FK)

2. Role
role_id (PK)
role_name
Зв’язок: одна роль може мати багато користувачів (1:M)

3. Client
client_id (PK)
full_name
passport_data
phone
email
address

4. InsurancePolicy
policy_id (PK)
client_id (FK)
start_date
end_date
insurance_type
premium_amount
Зв’язок: один клієнт може мати багато договорів (1:M)

5. InsuranceCase
case_id (PK)
policy_id (FK)
case_date
description
status
Зв’язок: один договір може мати багато страхових випадків (1:M)

6. Payment
payment_id (PK)
case_id (FK)
payment_date
payment_amount
Зв’язок: один страховий випадок може мати одну або декілька виплат (1:M)

7.3 Основні зв’язки між сутностями
Role → User (1:M)
Client → InsurancePolicy (1:M)
InsurancePolicy → InsuranceCase (1:M)
InsuranceCase → Payment (1:M)

7.4 ER-логіка моделі
Модель даних забезпечує:
цілісність даних (через первинні та зовнішні ключі);
уникнення дублювання інформації;
можливість масштабування системи.